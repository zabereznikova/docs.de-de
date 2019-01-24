---
title: 'Vorgehensweise: Darstellen von Spalten als Zeitstempel oder Versionsspalten'
ms.date: 03/30/2017
ms.assetid: 5afd5ce8-1d20-4bc3-a34f-49d95449f493
ms.openlocfilehash: fa9ffe01c45df3ce0342b62e12007ddf88ee412d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54674569"
---
# <a name="how-to-represent-columns-as-timestamp-or-version-columns"></a><span data-ttu-id="10ab0-102">Vorgehensweise: Darstellen von Spalten als Zeitstempel oder Versionsspalten</span><span class="sxs-lookup"><span data-stu-id="10ab0-102">How to: Represent Columns as Timestamp or Version Columns</span></span>
<span data-ttu-id="10ab0-103">Verwenden der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> Eigenschaft der <xref:System.Data.Linq.Mapping.ColumnAttribute> Attribut so kennzeichnen Sie ein Feld oder Eigenschaft Darstellung einer Datenbankspalte, die Datenbank-Timestamps oder-Versionsnummern enthält.</span><span class="sxs-lookup"><span data-stu-id="10ab0-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> property of the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate a field or property as representing a database column that holds database timestamps or version numbers.</span></span>  
  
 <span data-ttu-id="10ab0-104">Codebeispiele finden Sie unter <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span><span class="sxs-lookup"><span data-stu-id="10ab0-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span></span>  
  
### <a name="to-designate-a-field-or-property-as-representing-a-timestamp-or-version-column"></a><span data-ttu-id="10ab0-105">So kennzeichnen Sie ein Feld oder eine Eigenschaft für die Darstellung einer Timestamp- oder Versionsspalte</span><span class="sxs-lookup"><span data-stu-id="10ab0-105">To designate a field or property as representing a timestamp or version column</span></span>  
  
1.  <span data-ttu-id="10ab0-106">Fügen Sie die <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>-Eigenschaft dem <xref:System.Data.Linq.Mapping.ColumnAttribute>-Attribut hinzu.</span><span class="sxs-lookup"><span data-stu-id="10ab0-106">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2.  <span data-ttu-id="10ab0-107">Legen Sie den <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>-Eigenschaftswert auf `true` fest.</span><span class="sxs-lookup"><span data-stu-id="10ab0-107">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> property value to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10ab0-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="10ab0-108">See also</span></span>
- [<span data-ttu-id="10ab0-109">Das LINQ to SQL-Objektmodell</span><span class="sxs-lookup"><span data-stu-id="10ab0-109">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="10ab0-110">Vorgehensweise: Geben Sie die-Member auf Parallelitätskonflikte getestet werden</span><span class="sxs-lookup"><span data-stu-id="10ab0-110">How to: Specify Which Members are Tested for Concurrency Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-which-members-are-tested-for-concurrency-conflicts.md)
- [<span data-ttu-id="10ab0-111">Vorgehensweise: Anpassen von Entitätsklassen mit dem Code-Editor</span><span class="sxs-lookup"><span data-stu-id="10ab0-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
