---
title: "查询示例"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 137f8677-494c-4d49-95ce-c17742f2d01f
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 91ff476ed8f6060975c6adc1fe01a6db9c199969
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="query-examples"></a>查询示例
本节提供典型的 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] 查询的 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 和 C# 示例。 使用 [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] 的开发人员可以在“示例”一节中提供的示例解决方案中找到许多其他示例。 有关详细信息，请参阅[示例](../../../../../../docs/framework/data/adonet/sql/linq/samples.md)。  
  
> [!IMPORTANT]
>  *db*中的代码示例中经常会使用[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]文档。 *db*被假定为实例*Northwind*类，该类继承自<xref:System.Data.Linq.DataContext>。  
  
## <a name="in-this-section"></a>本节内容  
 [聚合查询](../../../../../../docs/framework/data/adonet/sql/linq/aggregate-queries.md)  
 介绍如何使用 <xref:System.Linq.Enumerable.Average%2A>、<xref:System.Linq.Enumerable.Count%2A> 等。  
  
 [返回序列中的第一个元素](../../../../../../docs/framework/data/adonet/sql/linq/return-the-first-element-in-a-sequence.md)  
 提供使用 <xref:System.Linq.Enumerable.First%2A> 的示例。  
  
 [返回或跳过序列中的元素](../../../../../../docs/framework/data/adonet/sql/linq/return-or-skip-elements-in-a-sequence.md)  
 提供使用 <xref:System.Linq.Enumerable.Take%2A> 和 <xref:System.Linq.Enumerable.Skip%2A> 的示例。  
  
 [在序列中对元素进行排序](../../../../../../docs/framework/data/adonet/sql/linq/sort-elements-in-a-sequence.md)  
 提供使用 <xref:System.Linq.Enumerable.OrderBy%2A> 的示例。  
  
 [对序列中的元素进行分组](../../../../../../docs/framework/data/adonet/sql/linq/group-elements-in-a-sequence.md)  
 提供使用 <xref:System.Linq.Enumerable.GroupBy%2A> 的示例。  
  
 [从序列中消除重复的元素](../../../../../../docs/framework/data/adonet/sql/linq/eliminate-duplicate-elements-from-a-sequence.md)  
 提供使用 <xref:System.Linq.Enumerable.Distinct%2A> 的示例。  
  
 [确定序列中任何或所有元素是否满足某一条件](../../../../../../docs/framework/data/adonet/sql/linq/determine-if-any-or-all-elements-in-a-sequence-satisfy-a-condition.md)  
 提供使用 <xref:System.Linq.Enumerable.All%2A> 和 <xref:System.Linq.Enumerable.Any%2A> 的示例。  
  
 [连接两个序列](../../../../../../docs/framework/data/adonet/sql/linq/concatenate-two-sequences.md)  
 提供使用 <xref:System.Linq.Enumerable.Concat%2A> 的示例。  
  
 [返回两个序列之间的差集](../../../../../../docs/framework/data/adonet/sql/linq/return-the-set-difference-between-two-sequences.md)  
 提供使用 <xref:System.Linq.Enumerable.Except%2A> 的示例。  
  
 [返回两个序列的交集](../../../../../../docs/framework/data/adonet/sql/linq/return-the-set-intersection-of-two-sequences.md)  
 提供使用 <xref:System.Linq.Enumerable.Intersect%2A> 的示例。  
  
 [返回两个序列的并集](../../../../../../docs/framework/data/adonet/sql/linq/return-the-set-union-of-two-sequences.md)  
 提供使用 <xref:System.Linq.Enumerable.Union%2A> 的示例。  
  
 [将序列转换为数组](../../../../../../docs/framework/data/adonet/sql/linq/convert-a-sequence-to-an-array.md)  
 提供使用 <xref:System.Linq.Enumerable.ToArray%2A> 的示例。  
  
 [将某一序列转换为泛型列表](../../../../../../docs/framework/data/adonet/sql/linq/convert-a-sequence-to-a-generic-list.md)  
 提供使用 <xref:System.Linq.Enumerable.ToList%2A> 的示例。  
  
 [将某一类型转换为泛型 IEnumerable](../../../../../../docs/framework/data/adonet/sql/linq/convert-a-type-to-a-generic-ienumerable.md)  
 提供使用 <xref:System.Linq.Enumerable.AsEnumerable%2A> 的示例。  
  
 [构建联接和叉积查询](../../../../../../docs/framework/data/adonet/sql/linq/formulate-joins-and-cross-product-queries.md)  
 提供在 `from`、`where` 和 `select` 子句中使用外键导航的示例。  
  
 [构建投影](../../../../../../docs/framework/data/adonet/sql/linq/formulate-projections.md)  
 提供示例组合在一起的`select`与其他功能 (例如，*匿名类型*) 构建查询投影。  
  
## <a name="related-sections"></a>相关章节  
 [标准查询运算符概述](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)  
 解释标准查询运算符的概念。  
  
 [查询概念](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)  
 解释 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 如何使用适用于查询的概念。  
  
 [编程指南](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 提供用于访问一些主题的门户，这些主题解释了与 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 相关的编程概念。
