---
title: '&lt;net.tcp&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8bc2f2be-11c1-4bab-9018-1d21ae568d94
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a3d22b6feef80dbff8c7f20b130ce2b0f9702c9e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltnettcpgt"></a>&lt;net.tcp&gt;
指定允许多个进程共享同一 TCP 端口的 NET.TCP 端口共享服务的配置设置。  
  
 \<system.serviceModel.activation >  
\<net.tcp >  
  
## <a name="syntax"></a>语法  
  
```xml  
<configuration>  
   <system.serviceModel.activation>  
       <net.tcp listenBacklog="Integer"  
          maxPendingAccepts="Integer"  
          maxPendingConnections="Integer"  
          receiveTimeout="TimeSpan"  
          teredoEnabled="Boolean">  
          <allowAccounts>  
             <!-- LocalSystem account -->   
             <add securityIdentifier="S-1-5-18"/>  
             <!-- LocalService account -->   
             <add securityIdentifier="S-1-5-19"/>  
             <!-- Administrators account -->   
             <add securityIdentifier="S-1-5-20"/>  
             <!-- Network Service account -->   
             <add securityIdentifier="S-1-5-32-544" />  
             <!-- IIS_IUSRS account (Vista only)-->   
             <add securityIdentifier="S-1-5-32-568"/>  
           </allowAccounts>  
       </net.tcp>  
   </system.serviceModel.activation>  
</configuration>  
```  
  
## <a name="type"></a>类型  
 `Type`  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|`listenBacklog`|一个整数，指定从共享连接接受但仍未调度给 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 服务的最大未完成连接数。 默认值为 10。|  
|`maxPendingAccepts`|一个整数，指定共享服务侦听终结点上的最大未完成并发接受线程数。 默认值为 2。|  
|`MaxPendingConnections`|侦听器可以拥有的正在等待应用程序接受的最大连接数。 超出此配额值时，新的传入连接会被丢弃而不是等待接受。 连接功能（如消息安全）可能会使客户端打开多个连接。 在设置此配额值时，服务管理员应该考虑这些额外的连接。 默认值为 10。|  
|`receiveTimeout`|`TimeSpan`，它将为读取组帧数据并执行来自基础连接的连接调度指定超时值。 默认值为“00:00:10”。|  
|`teredoEnabled`|一个布尔值，指示端口共享服务是否使用 Microsoft Teredo 服务代表 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 服务侦听 TCP 端口。 默认值为 `false`。|  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<allowAccounts >](../../../../../docs/framework/configure-apps/file-schema/wcf/allowaccounts.md)|一个配置元素集合，这些元素所包含的 `securityIdentifier` 属性用于指定进程的用户帐户，这些进程承载 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 服务并被授予了对该共享服务的连接访问权限。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<system.serviceModel.activation>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|包含侦听器进程 SMSvcHost.exe 的配置设置。|  
  
## <a name="remarks"></a>备注  
 端口共享的详细信息，请参阅[Net.TCP 端口共享](http://msdn.microsoft.com/en-us/f13692ee-a179-4439-ae72-50db9534eded)。 若要了解如何配置端口共享服务，请参阅[配置 Net.TCP Port Sharing Service](http://msdn.microsoft.com/en-us/b6dd81fa-68b7-4e1b-868e-88e5901b7ea0)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceModel.Activation.Configuration.NetTcpSection>  
 [Net.TCP 端口共享](http://msdn.microsoft.com/en-us/f13692ee-a179-4439-ae72-50db9534eded)  
 [配置 Net.TCP 端口共享服务](http://msdn.microsoft.com/en-us/b6dd81fa-68b7-4e1b-868e-88e5901b7ea0)
