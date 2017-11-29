---
title: 'Gewusst wie: Darstellen von Spalten als Zeitstempel- oder Versionsspalten'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5afd5ce8-1d20-4bc3-a34f-49d95449f493
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 88e30b947f18afd4ba93f816d9205c13d32fce82
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-represent-columns-as-timestamp-or-version-columns"></a><span data-ttu-id="174da-102">Gewusst wie: Darstellen von Spalten als Zeitstempel- oder Versionsspalten</span><span class="sxs-lookup"><span data-stu-id="174da-102">How to: Represent Columns as Timestamp or Version Columns</span></span>
<span data-ttu-id="174da-103">Verwenden der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> Eigenschaft von der <xref:System.Data.Linq.Mapping.ColumnAttribute> Attribut so kennzeichnen Sie ein Feld oder eine Eigenschaft, die eine Datenbankspalte, die Datenbank-Timestamps oder-Versionsnummern enthält darstellt.</span><span class="sxs-lookup"><span data-stu-id="174da-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> property of the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate a field or property as representing a database column that holds database timestamps or version numbers.</span></span>  
  
 <span data-ttu-id="174da-104">Codebeispiele finden Sie unter <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span><span class="sxs-lookup"><span data-stu-id="174da-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span></span>  
  
### <a name="to-designate-a-field-or-property-as-representing-a-timestamp-or-version-column"></a><span data-ttu-id="174da-105">So kennzeichnen Sie ein Feld oder eine Eigenschaft für die Darstellung einer Timestamp- oder Versionsspalte</span><span class="sxs-lookup"><span data-stu-id="174da-105">To designate a field or property as representing a timestamp or version column</span></span>  
  
1.  <span data-ttu-id="174da-106">Fügen Sie die <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>-Eigenschaft dem <xref:System.Data.Linq.Mapping.ColumnAttribute>-Attribut hinzu.</span><span class="sxs-lookup"><span data-stu-id="174da-106">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2.  <span data-ttu-id="174da-107">Legen Sie den <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>-Eigenschaftswert auf `true` fest.</span><span class="sxs-lookup"><span data-stu-id="174da-107">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> property value to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="174da-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="174da-108">See Also</span></span>  
 [<span data-ttu-id="174da-109">Die LINQ to SQL-Objektmodell</span><span class="sxs-lookup"><span data-stu-id="174da-109">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [<span data-ttu-id="174da-110">Vorgehensweise: angeben, welche Member auf Parallelitätskonflikte getestet werden</span><span class="sxs-lookup"><span data-stu-id="174da-110">How to: Specify Which Members are Tested for Concurrency Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-which-members-are-tested-for-concurrency-conflicts.md)  
 [<span data-ttu-id="174da-111">Vorgehensweise: Anpassen von Entitätsklassen mithilfe des Code-Editors</span><span class="sxs-lookup"><span data-stu-id="174da-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
