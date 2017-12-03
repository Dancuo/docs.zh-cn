---
title: "ICorDebugThread 接口 1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread
helpviewer_keywords: ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 3930fd9b-2bc3-4b72-80a0-b6eeb94d60c6
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 25b5c8f0720402cce56c69394c6fbe2fb70a6177
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugthread-interface1"></a><span data-ttu-id="50ee3-102">ICorDebugThread 接口 1</span><span class="sxs-lookup"><span data-stu-id="50ee3-102">ICorDebugThread Interface1</span></span>
<span data-ttu-id="50ee3-103">表示进程中的线程。</span><span class="sxs-lookup"><span data-stu-id="50ee3-103">Represents a thread in a process.</span></span> <span data-ttu-id="50ee3-104">`ICorDebugThread` 实例的生存期与它表示的线程的生存期相同。</span><span class="sxs-lookup"><span data-stu-id="50ee3-104">The lifetime of an `ICorDebugThread` instance is the same as the lifetime of the thread it represents.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="50ee3-105">方法</span><span class="sxs-lookup"><span data-stu-id="50ee3-105">Methods</span></span>  
  
|<span data-ttu-id="50ee3-106">方法</span><span class="sxs-lookup"><span data-stu-id="50ee3-106">Method</span></span>|<span data-ttu-id="50ee3-107">描述</span><span class="sxs-lookup"><span data-stu-id="50ee3-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="50ee3-108">ClearCurrentException 方法</span><span class="sxs-lookup"><span data-stu-id="50ee3-108">ClearCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-clearcurrentexception-method.md)|<span data-ttu-id="50ee3-109">未实现此方法。</span><span class="sxs-lookup"><span data-stu-id="50ee3-109">This method is not implemented.</span></span> <span data-ttu-id="50ee3-110">请勿使用。</span><span class="sxs-lookup"><span data-stu-id="50ee3-110">Do not use it.</span></span>|  
|[<span data-ttu-id="50ee3-111">CreateEval 方法</span><span class="sxs-lookup"><span data-stu-id="50ee3-111">CreateEval Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createeval-method.md)|<span data-ttu-id="50ee3-112">在此创建操作的 ICorDebugEval 对象`ICorDebugThread`。</span><span class="sxs-lookup"><span data-stu-id="50ee3-112">Creates an ICorDebugEval object that operates on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="50ee3-113">CreateStepper 方法</span><span class="sxs-lookup"><span data-stu-id="50ee3-113">CreateStepper Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createstepper-method.md)|<span data-ttu-id="50ee3-114">创建允许逐句通过在此活动帧的 ICorDebugStepper 对象`ICorDebugThread`。</span><span class="sxs-lookup"><span data-stu-id="50ee3-114">Creates an ICorDebugStepper object that allows stepping through the active frame in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="50ee3-115">EnumerateChains 方法</span><span class="sxs-lookup"><span data-stu-id="50ee3-115">EnumerateChains Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-enumeratechains-method.md)|<span data-ttu-id="50ee3-116">为包含在此的所有堆栈链 ICorDebugChainEnum 枚举器获取的接口指针`ICorDebugThread`。</span><span class="sxs-lookup"><span data-stu-id="50ee3-116">Gets an interface pointer to an ICorDebugChainEnum enumerator that contains all the stack chains in this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="50ee3-117">GetActiveChain 方法</span><span class="sxs-lookup"><span data-stu-id="50ee3-117">GetActiveChain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactivechain-method.md)|<span data-ttu-id="50ee3-118">获取的接口指针到活动 ICorDebugChain 此`ICorDebugThread`。</span><span class="sxs-lookup"><span data-stu-id="50ee3-118">Gets an interface pointer to the active ICorDebugChain on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="50ee3-119">GetActiveFrame 方法</span><span class="sxs-lookup"><span data-stu-id="50ee3-119">GetActiveFrame Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactiveframe-method.md)|<span data-ttu-id="50ee3-120">获取的接口指针到活动 ICorDebugFrame 此`ICorDebugThread`。</span><span class="sxs-lookup"><span data-stu-id="50ee3-120">Gets an interface pointer to the active ICorDebugFrame on this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="50ee3-121">GetAppDomain 方法</span><span class="sxs-lookup"><span data-stu-id="50ee3-121">GetAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getappdomain-method.md)|<span data-ttu-id="50ee3-122">用于应用程序域中获取的接口指针，此`ICorDebugThread`当前正在执行。</span><span class="sxs-lookup"><span data-stu-id="50ee3-122">Gets an interface pointer to the application domain in which this `ICorDebugThread` is currently executing.</span></span>|  
|[<span data-ttu-id="50ee3-123">GetCurrentException 方法</span><span class="sxs-lookup"><span data-stu-id="50ee3-123">GetCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md)|<span data-ttu-id="50ee3-124">获取一个表示当前由托管代码引发的异常的 ICorDebugValue 对象的接口指针。</span><span class="sxs-lookup"><span data-stu-id="50ee3-124">Gets an interface pointer to an ICorDebugValue object that represents an exception currently being thrown by managed code.</span></span>|  
|[<span data-ttu-id="50ee3-125">GetDebugState 方法</span><span class="sxs-lookup"><span data-stu-id="50ee3-125">GetDebugState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getdebugstate-method.md)|<span data-ttu-id="50ee3-126">获取描述当前的调试状态的这一个 CorDebugThreadState 值`ICorDebugThread`。</span><span class="sxs-lookup"><span data-stu-id="50ee3-126">Gets a CorDebugThreadState value that describes the current debug state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="50ee3-127">GetHandle 方法</span><span class="sxs-lookup"><span data-stu-id="50ee3-127">GetHandle Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-gethandle-method.md)|<span data-ttu-id="50ee3-128">获取当前句柄的活动部分`ICorDebugThread`。</span><span class="sxs-lookup"><span data-stu-id="50ee3-128">Gets the current handle for the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="50ee3-129">GetID 方法</span><span class="sxs-lookup"><span data-stu-id="50ee3-129">GetID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getid-method.md)|<span data-ttu-id="50ee3-130">获取此活动的部分的当前操作系统标识符`ICorDebugThread`。</span><span class="sxs-lookup"><span data-stu-id="50ee3-130">Gets the current operating system identifier of the active part of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="50ee3-131">GetObject 方法</span><span class="sxs-lookup"><span data-stu-id="50ee3-131">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getobject-method.md)|<span data-ttu-id="50ee3-132">获取公共语言运行时 (CLR) 线程的接口指针。</span><span class="sxs-lookup"><span data-stu-id="50ee3-132">Gets an interface pointer to the common language runtime (CLR) thread.</span></span>|  
|[<span data-ttu-id="50ee3-133">GetProcess 方法</span><span class="sxs-lookup"><span data-stu-id="50ee3-133">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getprocess-method.md)|<span data-ttu-id="50ee3-134">此过程中获取的接口指针`ICorDebugThread`窗体一部分。</span><span class="sxs-lookup"><span data-stu-id="50ee3-134">Gets an interface pointer to the process of which this `ICorDebugThread` forms a part.</span></span>|  
|[<span data-ttu-id="50ee3-135">GetRegisterSet 方法</span><span class="sxs-lookup"><span data-stu-id="50ee3-135">GetRegisterSet Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getregisterset-method.md)|<span data-ttu-id="50ee3-136">获取与此关联的寄存器集的接口指针`ICorDebugThread`。</span><span class="sxs-lookup"><span data-stu-id="50ee3-136">Gets an interface pointer to the register set associated with this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="50ee3-137">GetUserState 方法</span><span class="sxs-lookup"><span data-stu-id="50ee3-137">GetUserState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md)|<span data-ttu-id="50ee3-138">获取描述此的当前状态的 CorDebugUserState 值的按位组合`ICorDebugThread`。</span><span class="sxs-lookup"><span data-stu-id="50ee3-138">Gets a bitwise combination of CorDebugUserState values that describe the current state of this `ICorDebugThread`.</span></span>|  
|[<span data-ttu-id="50ee3-139">SetDebugState 方法</span><span class="sxs-lookup"><span data-stu-id="50ee3-139">SetDebugState Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md)|<span data-ttu-id="50ee3-140">设置的按位组合`CorDebugThreadState`值，用于描述此的调试状态`ICorDebugThread`。</span><span class="sxs-lookup"><span data-stu-id="50ee3-140">Sets a bitwise combination of `CorDebugThreadState` values that describe the debugging state of this `ICorDebugThread`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="50ee3-141">备注</span><span class="sxs-lookup"><span data-stu-id="50ee3-141">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="50ee3-142">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="50ee3-142">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50ee3-143">要求</span><span class="sxs-lookup"><span data-stu-id="50ee3-143">Requirements</span></span>  
 <span data-ttu-id="50ee3-144">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="50ee3-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50ee3-145">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="50ee3-145">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="50ee3-146">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="50ee3-146">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="50ee3-147">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50ee3-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50ee3-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="50ee3-148">See Also</span></span>  
 [<span data-ttu-id="50ee3-149">调试接口</span><span class="sxs-lookup"><span data-stu-id="50ee3-149">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)