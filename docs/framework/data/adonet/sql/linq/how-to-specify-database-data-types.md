---
title: 'Gewusst wie: Angeben von Datenbankdatentypen'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2228fdad-7e6a-4b1b-b4d1-79d0198b7c28
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 17ac588a8cf6815b244cf0b515603263f41b53ad
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-specify-database-data-types"></a><span data-ttu-id="5f99a-102">Gewusst wie: Angeben von Datenbankdatentypen</span><span class="sxs-lookup"><span data-stu-id="5f99a-102">How to: Specify Database Data Types</span></span>
<span data-ttu-id="5f99a-103">Verwenden der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> Eigenschaft auf einen <xref:System.Data.Linq.Mapping.ColumnAttribute> Attribut, um den genauen Text anzugeben, die die Spalte in einer T-SQL-Tabellendeklaration definiert.</span><span class="sxs-lookup"><span data-stu-id="5f99a-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> property on a <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to specify the exact text that defines the column in a T-SQL table declaration.</span></span>  
  
 <span data-ttu-id="5f99a-104">Sie müssen die <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>-Eigenschaft nur dann angeben, wenn Sie planen, <xref:System.Data.Linq.DataContext.CreateDatabase%2A> zur Erstellung einer Datenbankinstanz einzusetzen.</span><span class="sxs-lookup"><span data-stu-id="5f99a-104">You must specify the <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> property only if you plan to use <xref:System.Data.Linq.DataContext.CreateDatabase%2A> to create an instance of the database.</span></span>  
  
 <span data-ttu-id="5f99a-105">Codebeispiele finden Sie unter <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>.</span><span class="sxs-lookup"><span data-stu-id="5f99a-105">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>.</span></span>  
  
### <a name="to-specify-text-to-define-a-data-type-in-a-t-sql-table"></a><span data-ttu-id="5f99a-106">So geben Sie Text an, um einen Datentyp in einer T-SQL-Tabelle zu definieren</span><span class="sxs-lookup"><span data-stu-id="5f99a-106">To specify text to define a data type in a T-SQL table</span></span>  
  
1.  <span data-ttu-id="5f99a-107">Fügen Sie die <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>-Eigenschaft dem <xref:System.Data.Linq.Mapping.ColumnAttribute>-Attribut hinzu.</span><span class="sxs-lookup"><span data-stu-id="5f99a-107">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2.  <span data-ttu-id="5f99a-108">Legen Sie den Wert der <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>-Eigenschaft auf den genauen Text fest, der von T-SQL verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5f99a-108">Set the value of the <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> property to the exact text that is used by T-SQL.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f99a-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5f99a-109">See Also</span></span>  
 [<span data-ttu-id="5f99a-110">Das LINQ to SQL-Objektmodell</span><span class="sxs-lookup"><span data-stu-id="5f99a-110">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [<span data-ttu-id="5f99a-111">Vorgehensweise: Anpassen von Entitätsklassen mit dem Code-Editor</span><span class="sxs-lookup"><span data-stu-id="5f99a-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
