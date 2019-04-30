---
title: 'Vorgehensweise: Darstellen von berechneten Spalten'
ms.date: 03/30/2017
ms.assetid: 4025f1fd-9dfa-46c0-b04f-34e8bc7957a2
ms.openlocfilehash: df72562b303e5b9a7c31334df06926f157b59b05
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61903871"
---
# <a name="how-to-represent-computed-columns"></a><span data-ttu-id="7a7cd-102">Vorgehensweise: Darstellen von berechneten Spalten</span><span class="sxs-lookup"><span data-stu-id="7a7cd-102">How to: Represent Computed Columns</span></span>
<span data-ttu-id="7a7cd-103">Verwenden der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> Eigenschaft für eine <xref:System.Data.Linq.Mapping.ColumnAttribute> Attribut für die Darstellung einer Spalteninhalts, deren Inhalt das Ergebnis der Berechnung sind.</span><span class="sxs-lookup"><span data-stu-id="7a7cd-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> property on a <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to represent a column whose contents are the result of calculation.</span></span>  
  
 <span data-ttu-id="7a7cd-104">Codebeispiele finden Sie unter <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.</span><span class="sxs-lookup"><span data-stu-id="7a7cd-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="7a7cd-105">unterstützt keine berechneten Spalten als Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="7a7cd-105">does not support computed columns as primary keys.</span></span>  
  
### <a name="to-represent-a-computed-column"></a><span data-ttu-id="7a7cd-106">So stellen Sie eine berechnete Spalte dar</span><span class="sxs-lookup"><span data-stu-id="7a7cd-106">To represent a computed column</span></span>  
  
1. <span data-ttu-id="7a7cd-107">Fügen Sie die <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>-Eigenschaft dem <xref:System.Data.Linq.Mapping.ColumnAttribute>-Attribut hinzu.</span><span class="sxs-lookup"><span data-stu-id="7a7cd-107">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="7a7cd-108">Weisen Sie der <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>-Eigenschaft eine Zeichenfolgendarstellung der Formel zu.</span><span class="sxs-lookup"><span data-stu-id="7a7cd-108">Assign a string representation of the formula to the <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a7cd-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7a7cd-109">See also</span></span>

- [<span data-ttu-id="7a7cd-110">Das LINQ to SQL-Objektmodell</span><span class="sxs-lookup"><span data-stu-id="7a7cd-110">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="7a7cd-111">Vorgehensweise: Anpassen von Entitätsklassen mit dem Code-Editor</span><span class="sxs-lookup"><span data-stu-id="7a7cd-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
