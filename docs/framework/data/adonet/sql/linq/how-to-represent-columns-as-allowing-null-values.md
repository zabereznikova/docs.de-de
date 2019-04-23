---
title: 'Vorgehensweise: Darstellen von Spalten für die Zulassung von NULL-Werten'
ms.date: 03/30/2017
ms.assetid: ebb71a37-1f4c-4fa7-b2d2-d903f13c4af1
ms.openlocfilehash: ef8fa87963b91ef7140fbaefb657fc7904604b5b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59331155"
---
# <a name="how-to-represent-columns-as-allowing-null-values"></a><span data-ttu-id="f1b78-102">Vorgehensweise: Darstellen von Spalten für die Zulassung von NULL-Werten</span><span class="sxs-lookup"><span data-stu-id="f1b78-102">How to: Represent Columns as Allowing Null Values</span></span>
<span data-ttu-id="f1b78-103">Verwenden der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> Eigenschaft für die <xref:System.Data.Linq.Mapping.ColumnAttribute> Attribut, um anzugeben, dass die zugehörige Datenbankspalte null-Werte aufnehmen kann.</span><span class="sxs-lookup"><span data-stu-id="f1b78-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to specify that the associated database column can hold null values.</span></span>  
  
 <span data-ttu-id="f1b78-104">Codebeispiele finden Sie unter <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.</span><span class="sxs-lookup"><span data-stu-id="f1b78-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.</span></span>  
  
### <a name="to-designate-a-column-as-allowing-null-values"></a><span data-ttu-id="f1b78-105">So kennzeichnen Sie eine Spalte für die Zulassung von NULL-Werten</span><span class="sxs-lookup"><span data-stu-id="f1b78-105">To designate a column as allowing null values</span></span>  
  
1. <span data-ttu-id="f1b78-106">Fügen Sie die <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>-Eigenschaft dem <xref:System.Data.Linq.Mapping.ColumnAttribute>-Attribut hinzu.</span><span class="sxs-lookup"><span data-stu-id="f1b78-106">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="f1b78-107">Legen Sie den <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>-Eigenschaftswert auf `true` fest.</span><span class="sxs-lookup"><span data-stu-id="f1b78-107">Set the <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> property value to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1b78-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f1b78-108">See also</span></span>

- [<span data-ttu-id="f1b78-109">Das LINQ to SQL-Objektmodell</span><span class="sxs-lookup"><span data-stu-id="f1b78-109">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="f1b78-110">Vorgehensweise: Anpassen von Entitätsklassen mit dem Code-Editor</span><span class="sxs-lookup"><span data-stu-id="f1b78-110">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
