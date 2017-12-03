---
title: "设置分析环境"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- environment variables, profiling API
- profiling API [.NET Framework], setting up environment
- COR_PROFILER environment variable
- Windows Service applications, profiling
- profiling API [.NET Framework], Windows Service applications
- COR_ENABLE_PROFILING environment variable
- profiling API [.NET Framework], enabling
ms.assetid: fefca07f-7555-4e77-be86-3c542e928312
caps.latest.revision: "29"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7ff2c57be82166ecf5eb8a012491044eb2cb79d4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="setting-up-a-profiling-environment"></a><span data-ttu-id="2e630-102">设置分析环境</span><span class="sxs-lookup"><span data-stu-id="2e630-102">Setting Up a Profiling Environment</span></span>
> [!NOTE]
>  <span data-ttu-id="2e630-103">对 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] 中的分析进行了重大更改。</span><span class="sxs-lookup"><span data-stu-id="2e630-103">There have been substantial changes to profiling in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
 <span data-ttu-id="2e630-104">托管进程（应用程序或服务）启动时，将加载公共语言运行时 (CLR)。</span><span class="sxs-lookup"><span data-stu-id="2e630-104">When a managed process (application or service) starts, it loads the common language runtime (CLR).</span></span> <span data-ttu-id="2e630-105">初始化 CLR 时，将评估以下两个环境变量以决定进程是否应连接到探查器：</span><span class="sxs-lookup"><span data-stu-id="2e630-105">When the CLR is initialized, it evaluates the following two environmental variables to decide whether the process should connect to a profiler:</span></span>  
  
-   <span data-ttu-id="2e630-106">COR_ENABLE_PROFILING：仅当此环境变量存在并设置为 1 时，CLR 连接到探查器。</span><span class="sxs-lookup"><span data-stu-id="2e630-106">COR_ENABLE_PROFILING: The CLR connects to a profiler only if this environment variable exists and is set to 1.</span></span>  
  
-   <span data-ttu-id="2e630-107">COR_PROFILER：如果 COR_ENABLE_PROFILING 检查通过，CLR 将连接到具有此 CLSID 或 ProgID 的探查器（已事先存储在注册表中）。</span><span class="sxs-lookup"><span data-stu-id="2e630-107">COR_PROFILER: If the COR_ENABLE_PROFILING check passes, the CLR connects to the profiler that has this CLSID or ProgID, which must have been stored previously in the registry.</span></span> <span data-ttu-id="2e630-108">COR_PROFILER 环境变量被定义为字符串，如以下两个示例中所示。</span><span class="sxs-lookup"><span data-stu-id="2e630-108">The COR_PROFILER environment variable is defined as a string, as shown in the following two examples.</span></span>  
  
    ```  
    set COR_PROFILER={32E2F4DA-1BEA-47ea-88F9-C5DAF691C94A}  
    set COR_PROFILER="MyProfiler"  
    ```  
  
 <span data-ttu-id="2e630-109">若要分析 CLR 应用程序，必须在运行该应用程序之前设置 COR_ENABLE_PROFILING 和 COR_PROFILER 环境变量。</span><span class="sxs-lookup"><span data-stu-id="2e630-109">To profile a CLR application, you must set the COR_ENABLE_PROFILING and COR_PROFILER environment variables before you run the application.</span></span> <span data-ttu-id="2e630-110">还必须确保已注册探查器 DLL。</span><span class="sxs-lookup"><span data-stu-id="2e630-110">You must also make sure that the profiler DLL is registered.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2e630-111">从 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] 开始，不一定要注册探查器。</span><span class="sxs-lookup"><span data-stu-id="2e630-111">Starting with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)], profilers do not have to be registered.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2e630-112">若要使用.NET Framework 版本 2.0、 3.0 和 3.5 探查器在[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]和更高版本，你必须设置 COMPLUS_ProfAPI_ProfilerCompatibilitySetting 环境变量。</span><span class="sxs-lookup"><span data-stu-id="2e630-112">To use .NET Framework versions 2.0, 3.0, and 3.5 profilers in the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] and later versions, you must set the COMPLUS_ProfAPI_ProfilerCompatibilitySetting environment variable.</span></span>  
  
## <a name="environment-variable-scope"></a><span data-ttu-id="2e630-113">环境变量范围</span><span class="sxs-lookup"><span data-stu-id="2e630-113">Environment Variable Scope</span></span>  
 <span data-ttu-id="2e630-114">设置 COR_ENABLE_PROFILING 和 COR_PROFILER 环境变量的方式将决定其影响范围。</span><span class="sxs-lookup"><span data-stu-id="2e630-114">How you set the COR_ENABLE_PROFILING and COR_PROFILER environment variables will determine their scope of influence.</span></span> <span data-ttu-id="2e630-115">可以通过下列方式之一设置这些变量：</span><span class="sxs-lookup"><span data-stu-id="2e630-115">You can set these variables in one of the following ways:</span></span>  
  
-   <span data-ttu-id="2e630-116">如果设置中的变量[icordebug:: Createprocess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md)调用，它们将仅应用于的应用程序时运行。</span><span class="sxs-lookup"><span data-stu-id="2e630-116">If you set the variables in an [ICorDebug::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) call, they will apply only to the application that you are running at the time.</span></span> <span data-ttu-id="2e630-117">（它们将也应用于由继承环境的应用程序启动的其他应用程序。）</span><span class="sxs-lookup"><span data-stu-id="2e630-117">(They will also apply to other applications started by that application that inherit the environment.)</span></span>  
  
-   <span data-ttu-id="2e630-118">如果在“命令提示符”窗口中设置变量，则它们将应用于从该窗口中启动的所有应用程序。</span><span class="sxs-lookup"><span data-stu-id="2e630-118">If you set the variables in a Command Prompt window, they will apply to all applications that are started from that window.</span></span>  
  
-   <span data-ttu-id="2e630-119">如果在用户级别设置变量，它们将应用于用文件资源管理器启动的所有应用程序。</span><span class="sxs-lookup"><span data-stu-id="2e630-119">If you set the variables at the user level, they will apply to all applications that you start with File Explorer.</span></span> <span data-ttu-id="2e630-120">在设置变量后打开的“命令提示符”窗口将具有这些环境设置，从该窗口中启动的任何应用程序也将如此。</span><span class="sxs-lookup"><span data-stu-id="2e630-120">A Command Prompt window that you open after you set the variables will have these environment settings, and so will any application that you start from that window.</span></span> <span data-ttu-id="2e630-121">若要在用户级别设置环境变量，右键单击**我的电脑**，单击**属性**，单击**高级**选项卡上，单击**环境变量**，并添加到变量**用户变量**列表。</span><span class="sxs-lookup"><span data-stu-id="2e630-121">To set environment variables at the user level, right-click **My Computer**, click **Properties**, click the **Advanced** tab, click **Environment Variables**, and add the variables to the **User variables** list.</span></span>  
  
-   <span data-ttu-id="2e630-122">如果在计算机级别设置变量，它们将应用于在该计算机上启动的所有应用程序。</span><span class="sxs-lookup"><span data-stu-id="2e630-122">If you set the variables at the computer level, they will apply to all applications that are started on that computer.</span></span> <span data-ttu-id="2e630-123">在该计算机上打开的“命令提示符”窗口将具有这些环境设置，从该窗口中启动的任何应用程序也将如此。</span><span class="sxs-lookup"><span data-stu-id="2e630-123">A Command Prompt window that you open on that computer will have these environment settings, and so will any application that you start from that window.</span></span> <span data-ttu-id="2e630-124">这表示该计算机上的每个托管进程都将通过你的探查器启动。</span><span class="sxs-lookup"><span data-stu-id="2e630-124">This means that every managed process on that computer will start with your profiler.</span></span> <span data-ttu-id="2e630-125">若要在计算机级别设置环境变量，右键单击**我的电脑**，单击**属性**，单击**高级**选项卡上，单击**环境变量**，将变量添加到**系统变量**列表，，然后重新启动你的计算机。</span><span class="sxs-lookup"><span data-stu-id="2e630-125">To set environment variables at the computer level, right-click **My Computer**, click **Properties**, click the **Advanced** tab, click **Environment Variables**, add the variables to the **System variables** list, and then restart your computer.</span></span> <span data-ttu-id="2e630-126">重启后，变量将在系统范围内可用。</span><span class="sxs-lookup"><span data-stu-id="2e630-126">After restarting, the variables will be available system-wide.</span></span>  
  
 <span data-ttu-id="2e630-127">如果要分析 Windows 服务，必须在设置环境变量并注册探查器 DLL 之后重启计算机。</span><span class="sxs-lookup"><span data-stu-id="2e630-127">If you are profiling a Windows Service, you must restart your computer after you set the environment variables and register the profiler DLL.</span></span> <span data-ttu-id="2e630-128">有关这些注意事项的详细信息，请参阅明[分析 Windows 服务](#windows_service)。</span><span class="sxs-lookup"><span data-stu-id="2e630-128">For more information about these considerations, see the section [Profiling a Windows Service](#windows_service).</span></span>  
  
## <a name="additional-considerations"></a><span data-ttu-id="2e630-129">其他注意事项</span><span class="sxs-lookup"><span data-stu-id="2e630-129">Additional Considerations</span></span>  
  
-   <span data-ttu-id="2e630-130">探查器类实现[ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)和[ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="2e630-130">The profiler class implements the [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) and [ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md) interfaces.</span></span> <span data-ttu-id="2e630-131">在 .NET Framework 2.0 版中，探查器必须实现 `ICorProfilerCallback2`。</span><span class="sxs-lookup"><span data-stu-id="2e630-131">In the .NET Framework version 2.0, a profiler must implement `ICorProfilerCallback2`.</span></span> <span data-ttu-id="2e630-132">否则，将不会加载 `ICorProfilerCallback2`。</span><span class="sxs-lookup"><span data-stu-id="2e630-132">If it does not, `ICorProfilerCallback2` will not be loaded.</span></span>  
  
-   <span data-ttu-id="2e630-133">在给定环境中一次只能由一个事件探查器分析进程。</span><span class="sxs-lookup"><span data-stu-id="2e630-133">Only one profiler can profile a process at one time in a given environment.</span></span> <span data-ttu-id="2e630-134">可以在不同环境中注册两个不同的探查器，但每个探查器必须分析单独的进程。</span><span class="sxs-lookup"><span data-stu-id="2e630-134">You can register two different profilers in different environments, but each must profile separate processes.</span></span> <span data-ttu-id="2e630-135">必须将探查器作为进程内 COM 服务器 DLL 实现，后者被映射到与正在被分析的进程相同的地址空间。</span><span class="sxs-lookup"><span data-stu-id="2e630-135">The profiler must be implemented as an in-process COM server DLL, which is mapped into the same address space as the process that is being profiled.</span></span> <span data-ttu-id="2e630-136">这表示探查器在进程内运行。</span><span class="sxs-lookup"><span data-stu-id="2e630-136">This means that the profiler runs in-process.</span></span> <span data-ttu-id="2e630-137">.NET Framework 不支持任何其他类型的 COM 服务器。</span><span class="sxs-lookup"><span data-stu-id="2e630-137">The .NET Framework does not support any other type of COM server.</span></span> <span data-ttu-id="2e630-138">例如，如果探查器要监视远程计算机上的应用程序，则它必须在每台计算机上实现收集器代理。</span><span class="sxs-lookup"><span data-stu-id="2e630-138">For example, if a profiler wants to monitor applications from a remote computer, it must implement collector agents on each computer.</span></span> <span data-ttu-id="2e630-139">这些代理将批处理结果，并将它们传递给中央数据收集计算机。</span><span class="sxs-lookup"><span data-stu-id="2e630-139">These agents will batch results and communicate them to the central data collection computer.</span></span>  
  
-   <span data-ttu-id="2e630-140">由于探查器是在进程内实例化的 COM 对象，所以每个被分析的应用程序都将具有其自己的探查器副本。</span><span class="sxs-lookup"><span data-stu-id="2e630-140">Because the profiler is a COM object that is instantiated in-process, each profiled application will have its own copy of the profiler.</span></span> <span data-ttu-id="2e630-141">因此，单个探查器实例不一定要处理来自多个应用程序的数据。</span><span class="sxs-lookup"><span data-stu-id="2e630-141">Therefore, a single profiler instance does not have to handle data from multiple applications.</span></span> <span data-ttu-id="2e630-142">但是，必须向探查器的日志记录代码添加逻辑，以防日志文件从其他被分析的应用程序进行覆盖。</span><span class="sxs-lookup"><span data-stu-id="2e630-142">However, you will have to add logic to the profiler's logging code to prevent log file overwrites from other profiled applications.</span></span>  
  
## <a name="initializing-the-profiler"></a><span data-ttu-id="2e630-143">初始化探查器</span><span class="sxs-lookup"><span data-stu-id="2e630-143">Initializing the Profiler</span></span>  
 <span data-ttu-id="2e630-144">如果两次环境变量检查均通过，CLR 就会以与 COM `CoCreateInstance` 函数类似的方式创建探查器实例。</span><span class="sxs-lookup"><span data-stu-id="2e630-144">When both environment variable checks pass, the CLR creates an instance of the profiler in a similar manner to the COM `CoCreateInstance` function.</span></span> <span data-ttu-id="2e630-145">直接调用 `CoCreateInstance` 不会加载探查器。</span><span class="sxs-lookup"><span data-stu-id="2e630-145">The profiler is not loaded through a direct call to `CoCreateInstance`.</span></span> <span data-ttu-id="2e630-146">因此避免了调用 `CoInitialize`（需设置线程模型）。</span><span class="sxs-lookup"><span data-stu-id="2e630-146">Therefore, a call to `CoInitialize`, which requires setting the threading model, is avoided.</span></span> <span data-ttu-id="2e630-147">然后调用 CLR [icorprofilercallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)探查器中的方法。</span><span class="sxs-lookup"><span data-stu-id="2e630-147">The CLR then calls the [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) method in the profiler.</span></span> <span data-ttu-id="2e630-148">此方法的签名如下。</span><span class="sxs-lookup"><span data-stu-id="2e630-148">The signature of this method is as follows.</span></span>  
  
```  
HRESULT Initialize(IUnknown *pICorProfilerInfoUnk)  
```  
  
 <span data-ttu-id="2e630-149">探查器必须查询`pICorProfilerInfoUnk`为[ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)或[ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)接口指针，并将其保存，以便它可以请求更高版本在分析期间详细信息。</span><span class="sxs-lookup"><span data-stu-id="2e630-149">The profiler must query `pICorProfilerInfoUnk` for an [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) or [ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md) interface pointer and save it so that it can request more information later during profiling.</span></span>  
  
## <a name="setting-event-notifications"></a><span data-ttu-id="2e630-150">设置事件通知</span><span class="sxs-lookup"><span data-stu-id="2e630-150">Setting Event Notifications</span></span>  
 <span data-ttu-id="2e630-151">探查器然后调用[icorprofilerinfo:: Seteventmask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)方法，以指定它感兴趣的通知类别。</span><span class="sxs-lookup"><span data-stu-id="2e630-151">The profiler then calls the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method to specify which categories of notifications it is interested in.</span></span> <span data-ttu-id="2e630-152">例如，如果探查器只关注函数进入和离开通知以及垃圾回收通知，它将指定以下内容。</span><span class="sxs-lookup"><span data-stu-id="2e630-152">For example, if the profiler is interested only in function enter and leave notifications and garbage collection notifications, it specifies the following.</span></span>  
  
```  
ICorProfilerInfo* pInfo;  
pICorProfilerInfoUnk->QueryInterface(IID_ICorProfilerInfo, (void**)&pInfo);  
pInfo->SetEventMask(COR_PRF_MONITOR_ENTERLEAVE | COR_PRF_MONITOR_GC)  
```  
  
 <span data-ttu-id="2e630-153">通过以这种方式设置通知掩码，探查器可以限制它接收的通知。</span><span class="sxs-lookup"><span data-stu-id="2e630-153">By setting the notifications mask in this manner, the profiler can limit which notifications it receives.</span></span> <span data-ttu-id="2e630-154">此方法帮助用户构建简单探查器或具有特殊用途的探查器。</span><span class="sxs-lookup"><span data-stu-id="2e630-154">This approach helps the user build a simple or special-purpose profiler.</span></span> <span data-ttu-id="2e630-155">它还能减少发送探查器只会忽略的通知将浪费的 CPU 时间。</span><span class="sxs-lookup"><span data-stu-id="2e630-155">It also reduces CPU time that would be wasted sending notifications that the profiler would just ignore.</span></span>  
  
 <span data-ttu-id="2e630-156">某些探查器事件是不可变的。</span><span class="sxs-lookup"><span data-stu-id="2e630-156">Certain profiler events are immutable.</span></span> <span data-ttu-id="2e630-157">这表示，一旦在 `ICorProfilerCallback::Initialize` 回调中设置了这些事件，就不能将它们关闭，也不能打开新事件。</span><span class="sxs-lookup"><span data-stu-id="2e630-157">This means that as soon as these events are set in the `ICorProfilerCallback::Initialize` callback, they cannot be turned off and new events cannot be turned on.</span></span> <span data-ttu-id="2e630-158">试图更改不可变事件将导致 `ICorProfilerInfo::SetEventMask` 返回失败的 HRESULT。</span><span class="sxs-lookup"><span data-stu-id="2e630-158">Attempts to change an immutable event will result in `ICorProfilerInfo::SetEventMask` returning a failed HRESULT.</span></span>  
  
<a name="windows_service"></a>   
## <a name="profiling-a-windows-service"></a><span data-ttu-id="2e630-159">分析 Windows 服务</span><span class="sxs-lookup"><span data-stu-id="2e630-159">Profiling a Windows Service</span></span>  
 <span data-ttu-id="2e630-160">分析 Windows 服务与分析公共语言运行时应用程序相似。</span><span class="sxs-lookup"><span data-stu-id="2e630-160">Profiling a Windows Service is like profiling a common language runtime application.</span></span> <span data-ttu-id="2e630-161">两种分析操作都通过环境变量启用。</span><span class="sxs-lookup"><span data-stu-id="2e630-161">Both profiling operations are enabled through environment variables.</span></span> <span data-ttu-id="2e630-162">由于 Windows 服务已于操作系统启动时启动，本主题中之前所述的环境变量必须在系统启动前就已经存在并设置为所需的值。</span><span class="sxs-lookup"><span data-stu-id="2e630-162">Because a Windows Service is started when the operating system starts, the environment variables discussed previously in this topic must already be present and set to the required values before the system starts.</span></span> <span data-ttu-id="2e630-163">此外，必须已在系统上注册了分析 DLL。</span><span class="sxs-lookup"><span data-stu-id="2e630-163">In addition, the profiling DLL must already be registered on the system.</span></span>  
  
 <span data-ttu-id="2e630-164">设置 COR_ENABLE_PROFILING 和 COR_PROFILER 环境变量并注册探查器 DLL 后，应重启目标计算机，以便 Windows 服务能够检测这些更改。</span><span class="sxs-lookup"><span data-stu-id="2e630-164">After you set the COR_ENABLE_PROFILING and COR_PROFILER environment variables and register the profiler DLL, you should restart the target computer so that the Windows Service can detect those changes.</span></span>  
  
 <span data-ttu-id="2e630-165">请注意，这些更改将在整个系统范围内启用分析。</span><span class="sxs-lookup"><span data-stu-id="2e630-165">Note that these changes will enable profiling on a system-wide basis.</span></span> <span data-ttu-id="2e630-166">若要防止对随后运行的每个托管应用程序进行分析，应在重启目标计算机后删除系统环境变量。</span><span class="sxs-lookup"><span data-stu-id="2e630-166">To prevent every managed application that subsequently runs from being profiled, you should delete the system environment variables after you restart the target computer.</span></span>  
  
 <span data-ttu-id="2e630-167">此技术也会导致对每个 CLR 进程进行分析。</span><span class="sxs-lookup"><span data-stu-id="2e630-167">This technique also leads to every CLR process getting profiled.</span></span> <span data-ttu-id="2e630-168">探查器应将逻辑添加到其[icorprofilercallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)回调以检测当前进程是否感兴趣。</span><span class="sxs-lookup"><span data-stu-id="2e630-168">The profiler should add logic to its [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback to detect whether the current process is of interest.</span></span> <span data-ttu-id="2e630-169">如果不相关，探查器可使回调失败而不执行初始化。</span><span class="sxs-lookup"><span data-stu-id="2e630-169">If it is not, the profiler can fail the callback without performing the initialization.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e630-170">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2e630-170">See Also</span></span>  
 [<span data-ttu-id="2e630-171">分析概述</span><span class="sxs-lookup"><span data-stu-id="2e630-171">Profiling Overview</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)