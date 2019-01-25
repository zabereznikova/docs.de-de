---
title: 'Vorgehensweise: Darstellen von berechneten Spalten'
ms.date: 03/30/2017
ms.assetid: 4025f1fd-9dfa-46c0-b04f-34e8bc7957a2
ms.openlocfilehash: 97db5d69cd97922acefb0b1f3b10f69cf99e3583
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54608335"
---
# <a name="how-to-represent-computed-columns"></a><span data-ttu-id="b3ef2-102">Vorgehensweise: Darstellen von berechneten Spalten</span><span class="sxs-lookup"><span data-stu-id="b3ef2-102">How to: Represent Computed Columns</span></span>
<span data-ttu-id="b3ef2-103">Verwenden der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> Eigenschaft für eine <xref:System.Data.Linq.Mapping.ColumnAttribute> Attribut für die Darstellung einer Spalteninhalts, deren Inhalt das Ergebnis der Berechnung sind.</span><span class="sxs-lookup"><span data-stu-id="b3ef2-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> property on a <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to represent a column whose contents are the result of calculation.</span></span>  
  
 <span data-ttu-id="b3ef2-104">Codebeispiele finden Sie unter <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.</span><span class="sxs-lookup"><span data-stu-id="b3ef2-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="b3ef2-105">unterstützt keine berechneten Spalten als Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="b3ef2-105">does not support computed columns as primary keys.</span></span>  
  
### <a name="to-represent-a-computed-column"></a><span data-ttu-id="b3ef2-106">So stellen Sie eine berechnete Spalte dar</span><span class="sxs-lookup"><span data-stu-id="b3ef2-106">To represent a computed column</span></span>  
  
1.  <span data-ttu-id="b3ef2-107">Fügen Sie die <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>-Eigenschaft dem <xref:System.Data.Linq.Mapping.ColumnAttribute>-Attribut hinzu.</span><span class="sxs-lookup"><span data-stu-id="b3ef2-107">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2.  <span data-ttu-id="b3ef2-108">Weisen Sie der <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>-Eigenschaft eine Zeichenfolgendarstellung der Formel zu.</span><span class="sxs-lookup"><span data-stu-id="b3ef2-108">Assign a string representation of the formula to the <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3ef2-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b3ef2-109">See also</span></span>
- [<span data-ttu-id="b3ef2-110">Das LINQ to SQL-Objektmodell</span><span class="sxs-lookup"><span data-stu-id="b3ef2-110">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="b3ef2-111">Vorgehensweise: Anpassen von Entitätsklassen mit dem Code-Editor</span><span class="sxs-lookup"><span data-stu-id="b3ef2-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
