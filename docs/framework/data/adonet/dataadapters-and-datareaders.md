---
title: "DataAdapter 和 DataReader"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cc952ca2-ec19-46ab-9189-15174b52cb74
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 6d071622862a645d11ea8228574f81d5f8c3e6e2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="dataadapters-and-datareaders"></a>DataAdapter 和 DataReader
你可以使用 ADO.NET **DataReader**以从数据库中检索数据的只读、 只进流。 查询执行，以及存储在客户端上的网络缓冲区，直到你请求时，这些结果将返回使用**读取**方法**DataReader**。 使用**DataReader**可以提高应用程序性能，检索数据，只要它不可用，并且 （默认） 存储在内存，从而减少系统开销中一次只有一个行。  
  
 <xref:System.Data.Common.DataAdapter> 用于从数据源检索数据并填充 <xref:System.Data.DataSet> 中的表。 `DataAdapter` 还可将对 `DataSet` 所做的更改解析回数据源。 `DataAdapter` 使用 .NET Framework 数据提供程序的 `Connection` 对象连接到数据源，并使用 `Command` 对象从数据源检索数据以及将更改解析回数据源。  
  
 随 .NET Framework 提供的每个 .NET Framework 数据提供程序都具有一个 <xref:System.Data.Common.DbDataReader> 和一个 <xref:System.Data.Common.DbDataAdapter> 对象：用于 OLE DB 的 .NET Framework 数据提供程序包括一个 <xref:System.Data.OleDb.OleDbDataReader> 和一个 <xref:System.Data.OleDb.OleDbDataAdapter> 对象，用于 SQL Server 的 .NET Framework 数据提供程序包括一个 <xref:System.Data.SqlClient.SqlDataReader> 和一个 <xref:System.Data.SqlClient.SqlDataAdapter> 对象，用于 ODBC 的 .NET Framework 数据提供程序包括一个 <xref:System.Data.Odbc.OdbcDataReader> 和一个 <xref:System.Data.Odbc.OdbcDataAdapter> 对象，用于 Oracle 的 .NET Framework 数据提供程序包括一个 <xref:System.Data.OracleClient.OracleDataReader> 和一个 <xref:System.Data.OracleClient.OracleDataAdapter> 对象。  
  
## <a name="in-this-section"></a>本节内容  
 [使用 DataReader 检索 ADO 数据](../../../../docs/framework/data/adonet/retrieving-data-using-a-datareader.md)  
 描述 ADO.NET **DataReader**对象以及如何使用它从数据源返回结果流。  
  
 [从 DataAdapter 填充数据集](../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)  
 说明如何通过 `DataSet` 使用表、列和行填充 `DataAdapter`。  
  
 [DataAdapter 参数](../../../../docs/framework/data/adonet/dataadapter-parameters.md)  
 说明如何与 `DataAdapter` 的命令属性一起使用参数，包括如何将 `DataSet` 的列内容映射到命令参数。  
  
 [将现有约束添加到数据集](../../../../docs/framework/data/adonet/adding-existing-constraints-to-a-dataset.md)  
 说明如何将现有约束添加到 `DataSet`。  
  
 [DataAdapter 数据表和 DataColumn 映射](../../../../docs/framework/data/adonet/dataadapter-datatable-and-datacolumn-mappings.md)  
 说明如何为 `DataTableMappings` 设置 `ColumnMappings` 和 `DataAdapter`。  
  
 [通过查询结果分页](../../../../docs/framework/data/adonet/paging-through-a-query-result.md)  
 提供一个以数据页形式查看查询结果的示例。  
  
 [使用 DataAdapter 更新数据源](../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)  
 说明如何使用 `DataAdapter` 将 `DataSet` 中的更改解析回数据库。  
  
 [处理 DataAdapter 事件](../../../../docs/framework/data/adonet/handling-dataadapter-events.md)  
 说明 `DataAdapter` 事件以及如何使用这些事件。  
  
 [使用 DataAdapter 执行批处理操作](../../../../docs/framework/data/adonet/performing-batch-operations-using-dataadapters.md)  
 说明在从 `DataSet` 应用更新时，如何通过减少与 SQL Server 之间的往返次数来提高应用程序的性能。  
  
## <a name="see-also"></a>请参阅  
 [连接到数据源](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 [命令和参数](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [事务和并发性](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)  
 [数据集、数据表和数据视图](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [ADO.NET 托管提供程序和数据集开发人员中心](http://go.microsoft.com/fwlink/?LinkId=217917)
