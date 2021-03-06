---
title: "如何：对 Windows 窗体 ListView 控件中的项进行分组"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], grouping items
- lists [Windows Forms], grouping items
- grouping
- list views [Windows Forms], grouping items
- groups
- groups [Windows Forms], in Windows Forms controls
ms.assetid: 610416a1-8da4-436c-af19-5f19e654769b
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b12b7126e03f6a6c8363c69a607f4961f13120ce
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control"></a>如何：对 Windows 窗体 ListView 控件中的项进行分组
使用的分组功能<xref:System.Windows.Forms.ListView>控件，你可以在组中显示的项的相关的集。 在屏幕上分隔这些组由包含组标题的水平组标题。 你可以使用<xref:System.Windows.Forms.ListView>组以使大型列表对项进行分组按字母顺序，按日期，或任何其他逻辑分组的导航。 下图显示一些分组的项。  
  
 ![ListView 组](../../../../docs/framework/winforms/controls/media/listviewgroups.gif "ListViewGroups")  
ListView 的分组项  
  
 若要启用分组，您必须首先创建一个或多个组设计器中或以编程方式。 定义的组之后，你可以分配<xref:System.Windows.Forms.ListView>项目到组。 你还可以移动项从一个组到另一个以编程方式。  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ListView>组是仅适用于[!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)]在你的应用程序调用<xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>方法。 在早期的操作系统上与组相关的任何代码有影响，并且组将不会出现。 有关详细信息，请参阅<xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>。  
  
### <a name="to-add-groups"></a>若要添加组  
  
1.  使用 <xref:System.Windows.Forms.ListView.Groups%2A> 集合的 <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> 方法。  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#21)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#21)]  
  
### <a name="to-remove-groups"></a>要删除组  
  
1.  使用<xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A>或<xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A>方法<xref:System.Windows.Forms.ListView.Groups%2A>集合。  
  
     <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A>方法中删除单个组;<xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A>方法从列表中删除所有组。  
  
    > [!NOTE]
    >  删除组不会删除该组中的项。  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#22)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#22)]  
  
### <a name="to-assign-items-to-groups-or-move-items-between-groups"></a>若要将项分配给组或组之间移动项  
  
1.  设置<xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType>的各项的属性。  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#23)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#23)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.ListView>  
 <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.ListViewGroup>  
 [ListView 控件](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)  
 [ListView 控件概述](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 [Windows XP 功能和 Windows 窗体控件](http://msdn.microsoft.com/en-us/bc7fab94-fce9-4bf1-a8ad-a5837c91c3c0)  
 [如何：使用 Windows 窗体 ListView 控件添加和删除项](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
