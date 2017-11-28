---
title: "_CorValidateImage 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: _CorValidateImage
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: _CorValidateImage
helpviewer_keywords: _CorValidateImage function [.NET Framework hosting]
ms.assetid: 0117e080-05f9-4772-885d-e1847230947c
topic_type: apiref
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e2396219a5e4bfd95a9dc7134e2e603ed7a15a3d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="corvalidateimage-function"></a><span data-ttu-id="0ec80-102">_CorValidateImage 函数</span><span class="sxs-lookup"><span data-stu-id="0ec80-102">_CorValidateImage Function</span></span>
<span data-ttu-id="0ec80-103">验证托管的模块映像，并通知操作系统加载程序后将其加载。</span><span class="sxs-lookup"><span data-stu-id="0ec80-103">Validates managed module images, and notifies the operating system loader after they have been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ec80-104">语法</span><span class="sxs-lookup"><span data-stu-id="0ec80-104">Syntax</span></span>  
  
```  
STDAPI _CorValidateImage (   
   [in] PVOID* ImageBase,  
   [in] LPCWSTR FileName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0ec80-105">参数</span><span class="sxs-lookup"><span data-stu-id="0ec80-105">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="0ec80-106">[in]指向要验证的图像的起始位置的托管代码。</span><span class="sxs-lookup"><span data-stu-id="0ec80-106">[in] A pointer to the starting location of the image to validate as managed code.</span></span> <span data-ttu-id="0ec80-107">该映像必须已加载到内存中。</span><span class="sxs-lookup"><span data-stu-id="0ec80-107">The image must already be loaded into memory.</span></span>  
  
 `FileName`  
 <span data-ttu-id="0ec80-108">[in]图像的文件名。</span><span class="sxs-lookup"><span data-stu-id="0ec80-108">[in] The file name of the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0ec80-109">返回值</span><span class="sxs-lookup"><span data-stu-id="0ec80-109">Return Value</span></span>  
 <span data-ttu-id="0ec80-110">此函数将返回的标准值`E_INVALIDARG`， `E_OUTOFMEMORY`， `E_UNEXPECTED`，和`E_FAIL`，以及以下值。</span><span class="sxs-lookup"><span data-stu-id="0ec80-110">This function returns the standard values `E_INVALIDARG`, `E_OUTOFMEMORY`, `E_UNEXPECTED`, and `E_FAIL`, as well as the following values.</span></span>  
  
|<span data-ttu-id="0ec80-111">返回值</span><span class="sxs-lookup"><span data-stu-id="0ec80-111">Return value</span></span>|<span data-ttu-id="0ec80-112">描述</span><span class="sxs-lookup"><span data-stu-id="0ec80-112">Description</span></span>|  
|------------------|-----------------|  
|`STATUS_INVALID_IMAGE_FORMAT`|<span data-ttu-id="0ec80-113">该映像已无效。</span><span class="sxs-lookup"><span data-stu-id="0ec80-113">The image is invalid.</span></span> <span data-ttu-id="0ec80-114">此值具有 HRESULT 0xC000007BL。</span><span class="sxs-lookup"><span data-stu-id="0ec80-114">This value has the HRESULT 0xC000007BL.</span></span>|  
|`STATUS_SUCCESS`|<span data-ttu-id="0ec80-115">映像是有效的。</span><span class="sxs-lookup"><span data-stu-id="0ec80-115">The image is valid.</span></span> <span data-ttu-id="0ec80-116">此值具有 HRESULT 0x00000000L。</span><span class="sxs-lookup"><span data-stu-id="0ec80-116">This value has the HRESULT 0x00000000L.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ec80-117">备注</span><span class="sxs-lookup"><span data-stu-id="0ec80-117">Remarks</span></span>  
 <span data-ttu-id="0ec80-118">在 Windows XP 和更高版本中，操作系统加载程序通过检查常见对象文件格式 (COFF) 标头中的 COM 描述符目录位检查托管模块。</span><span class="sxs-lookup"><span data-stu-id="0ec80-118">In Windows XP and later versions, the operating system loader checks for managed modules by examining the COM Descriptor Directory bit in the common object file format (COFF) header.</span></span> <span data-ttu-id="0ec80-119">一个设置位指示的托管的模块。</span><span class="sxs-lookup"><span data-stu-id="0ec80-119">A set bit indicates a managed module.</span></span> <span data-ttu-id="0ec80-120">如果加载程序检测到的托管的模块，它将加载 MsCorEE.dll 和调用`_CorValidateImage`，这将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0ec80-120">If the loader detects a managed module, it loads MsCorEE.dll and calls `_CorValidateImage`, which performs the following actions:</span></span>  
  
-   <span data-ttu-id="0ec80-121">确认该图像是有效的托管的模块。</span><span class="sxs-lookup"><span data-stu-id="0ec80-121">Confirms that the image is a valid managed module.</span></span>  
  
-   <span data-ttu-id="0ec80-122">更改为公共语言运行时 (CLR) 中的入口点的映像中的入口点。</span><span class="sxs-lookup"><span data-stu-id="0ec80-122">Changes the entry point in the image to an entry point in the common language runtime (CLR).</span></span>  
  
-   <span data-ttu-id="0ec80-123">对于 64 位版本的 Windows，修改通过将其从 PE32 转换为 PE32 + 格式是内存中的映像。</span><span class="sxs-lookup"><span data-stu-id="0ec80-123">For 64-bit versions of Windows, modifies the image that is in memory by transforming it from PE32 to PE32+ format.</span></span>  
  
-   <span data-ttu-id="0ec80-124">返回到加载程序加载托管的模块映像时。</span><span class="sxs-lookup"><span data-stu-id="0ec80-124">Returns to the loader when the managed module images are loaded.</span></span>  
  
 <span data-ttu-id="0ec80-125">对于可执行映像，操作系统加载程序然后调用[_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md)函数，而不考虑可执行文件中指定的入口点。</span><span class="sxs-lookup"><span data-stu-id="0ec80-125">For executable images, the operating system loader then calls the [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) function, regardless of the entry point specified in the executable.</span></span> <span data-ttu-id="0ec80-126">对于 DLL 的程序集图像，加载程序将调用[_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md)函数。</span><span class="sxs-lookup"><span data-stu-id="0ec80-126">For DLL assembly images, the loader calls the [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) function.</span></span>  
  
 <span data-ttu-id="0ec80-127">`_CorExeMain`或`_CorDllMain`执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="0ec80-127">`_CorExeMain` or `_CorDllMain` performs the following actions:</span></span>  
  
-   <span data-ttu-id="0ec80-128">初始化 CLR。</span><span class="sxs-lookup"><span data-stu-id="0ec80-128">Initializes the CLR.</span></span>  
  
-   <span data-ttu-id="0ec80-129">查找程序集的 CLR 标头中的托管的入口点。</span><span class="sxs-lookup"><span data-stu-id="0ec80-129">Locates the managed entry point from the assembly's CLR header.</span></span>  
  
-   <span data-ttu-id="0ec80-130">开始执行。</span><span class="sxs-lookup"><span data-stu-id="0ec80-130">Begins execution.</span></span>  
  
 <span data-ttu-id="0ec80-131">加载程序调用[_CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md)函数时托管模块映像将被卸载。</span><span class="sxs-lookup"><span data-stu-id="0ec80-131">The loader calls the [_CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md) function when managed module images are unloaded.</span></span> <span data-ttu-id="0ec80-132">但是，此函数不执行任何操作;它只返回。</span><span class="sxs-lookup"><span data-stu-id="0ec80-132">However, this function does not perform any action; it just returns.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ec80-133">要求</span><span class="sxs-lookup"><span data-stu-id="0ec80-133">Requirements</span></span>  
 <span data-ttu-id="0ec80-134">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0ec80-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ec80-135">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0ec80-135">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0ec80-136">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="0ec80-136">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0ec80-137">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ec80-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ec80-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0ec80-138">See Also</span></span>  
 [<span data-ttu-id="0ec80-139">元数据全局静态函数</span><span class="sxs-lookup"><span data-stu-id="0ec80-139">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)