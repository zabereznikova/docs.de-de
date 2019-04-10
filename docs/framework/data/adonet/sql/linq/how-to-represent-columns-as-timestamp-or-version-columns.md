---
title: 'Vorgehensweise: Darstellen von Spalten als Zeitstempel- oder Versionsspalten'
ms.date: 03/30/2017
ms.assetid: 5afd5ce8-1d20-4bc3-a34f-49d95449f493
ms.openlocfilehash: db73bf4880d8f5556247f7b037fca24b0ddc56d6
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59297888"
---
# <a name="how-to-represent-columns-as-timestamp-or-version-columns"></a><span data-ttu-id="38b25-102">Vorgehensweise: Darstellen von Spalten als Zeitstempel- oder Versionsspalten</span><span class="sxs-lookup"><span data-stu-id="38b25-102">How to: Represent Columns as Timestamp or Version Columns</span></span>
<span data-ttu-id="38b25-103">Verwenden der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> Eigenschaft der <xref:System.Data.Linq.Mapping.ColumnAttribute> Attribut so kennzeichnen Sie ein Feld oder Eigenschaft Darstellung einer Datenbankspalte, die Datenbank-Timestamps oder-Versionsnummern enthält.</span><span class="sxs-lookup"><span data-stu-id="38b25-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> property of the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate a field or property as representing a database column that holds database timestamps or version numbers.</span></span>  
  
 <span data-ttu-id="38b25-104">Codebeispiele finden Sie unter <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span><span class="sxs-lookup"><span data-stu-id="38b25-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.</span></span>  
  
### <a name="to-designate-a-field-or-property-as-representing-a-timestamp-or-version-column"></a><span data-ttu-id="38b25-105">So kennzeichnen Sie ein Feld oder eine Eigenschaft für die Darstellung einer Timestamp- oder Versionsspalte</span><span class="sxs-lookup"><span data-stu-id="38b25-105">To designate a field or property as representing a timestamp or version column</span></span>  
  
1. <span data-ttu-id="38b25-106">Fügen Sie die <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>-Eigenschaft dem <xref:System.Data.Linq.Mapping.ColumnAttribute>-Attribut hinzu.</span><span class="sxs-lookup"><span data-stu-id="38b25-106">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="38b25-107">Legen Sie den <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>-Eigenschaftswert auf `true` fest.</span><span class="sxs-lookup"><span data-stu-id="38b25-107">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> property value to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38b25-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="38b25-108">See also</span></span>

- [<span data-ttu-id="38b25-109">Das LINQ to SQL-Objektmodell</span><span class="sxs-lookup"><span data-stu-id="38b25-109">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="38b25-110">Vorgehensweise: Angeben, welche Member auf Parallelitätskonflikte getestet werden</span><span class="sxs-lookup"><span data-stu-id="38b25-110">How to: Specify Which Members are Tested for Concurrency Conflicts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-which-members-are-tested-for-concurrency-conflicts.md)
- [<span data-ttu-id="38b25-111">Vorgehensweise: Anpassen von Entitätsklassen mit dem Code-Editor</span><span class="sxs-lookup"><span data-stu-id="38b25-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
