---
title: "Gewusst wie: Darstellen von Spalten für die Zulassung von NULL-Werten"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ebb71a37-1f4c-4fa7-b2d2-d903f13c4af1
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: efa6f9d453940151dfe01d27827760521359ab67
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-represent-columns-as-allowing-null-values"></a><span data-ttu-id="40ed1-102">Gewusst wie: Darstellen von Spalten für die Zulassung von NULL-Werten</span><span class="sxs-lookup"><span data-stu-id="40ed1-102">How to: Represent Columns as Allowing Null Values</span></span>
<span data-ttu-id="40ed1-103">Verwenden der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> Eigenschaft auf die <xref:System.Data.Linq.Mapping.ColumnAttribute> Attribut, um anzugeben, dass die zugehörige Datenbankspalte null-Werte aufnehmen kann.</span><span class="sxs-lookup"><span data-stu-id="40ed1-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to specify that the associated database column can hold null values.</span></span>  
  
 <span data-ttu-id="40ed1-104">Codebeispiele finden Sie unter <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.</span><span class="sxs-lookup"><span data-stu-id="40ed1-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.</span></span>  
  
### <a name="to-designate-a-column-as-allowing-null-values"></a><span data-ttu-id="40ed1-105">So kennzeichnen Sie eine Spalte für die Zulassung von NULL-Werten</span><span class="sxs-lookup"><span data-stu-id="40ed1-105">To designate a column as allowing null values</span></span>  
  
1.  <span data-ttu-id="40ed1-106">Fügen Sie die <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>-Eigenschaft dem <xref:System.Data.Linq.Mapping.ColumnAttribute>-Attribut hinzu.</span><span class="sxs-lookup"><span data-stu-id="40ed1-106">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2.  <span data-ttu-id="40ed1-107">Legen Sie den <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>-Eigenschaftswert auf `true` fest.</span><span class="sxs-lookup"><span data-stu-id="40ed1-107">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> property value to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40ed1-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="40ed1-108">See Also</span></span>  
 [<span data-ttu-id="40ed1-109">Die LINQ to SQL-Objektmodell</span><span class="sxs-lookup"><span data-stu-id="40ed1-109">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [<span data-ttu-id="40ed1-110">Vorgehensweise: Anpassen von Entitätsklassen mithilfe des Code-Editors</span><span class="sxs-lookup"><span data-stu-id="40ed1-110">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
