---
title: 'Vorgehensweise: Darstellen von Primärschlüsseln'
ms.date: 03/30/2017
ms.assetid: 63c65289-6539-42b2-8493-891c232018fa
ms.openlocfilehash: 714211046afcafab4c2b67bf9318cfbede314476
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59173211"
---
# <a name="how-to-represent-primary-keys"></a><span data-ttu-id="a4be8-102">Vorgehensweise: Darstellen von Primärschlüsseln</span><span class="sxs-lookup"><span data-stu-id="a4be8-102">How to: Represent Primary Keys</span></span>
<span data-ttu-id="a4be8-103">Verwenden der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> Eigenschaft für die <xref:System.Data.Linq.Mapping.ColumnAttribute> Attribut, um eine Eigenschaft oder ein Feld zur Darstellung des primären Schlüssels für eine Datenbankspalte zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="a4be8-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate a property or field to represent the primary key for a database column.</span></span>  
  
 <span data-ttu-id="a4be8-104">Codebeispiele finden Sie unter <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span><span class="sxs-lookup"><span data-stu-id="a4be8-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="a4be8-105">unterstützt keine berechnete Spalten als Primärschlüssel verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a4be8-105">does not support computed columns as primary keys.</span></span>  
  
### <a name="to-designate-a-property-or-field-as-a-primary-key"></a><span data-ttu-id="a4be8-106">So legen Sie eine Eigenschaft oder ein Feld als Primärschlüssel fest</span><span class="sxs-lookup"><span data-stu-id="a4be8-106">To designate a property or field as a primary key</span></span>  
  
1.  <span data-ttu-id="a4be8-107">Fügen Sie die <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>-Eigenschaft dem <xref:System.Data.Linq.Mapping.ColumnAttribute>-Attribut hinzu.</span><span class="sxs-lookup"><span data-stu-id="a4be8-107">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2.  <span data-ttu-id="a4be8-108">Geben Sie den Wert als `true` an.</span><span class="sxs-lookup"><span data-stu-id="a4be8-108">Specify the value as `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4be8-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a4be8-109">See also</span></span>

- [<span data-ttu-id="a4be8-110">Das LINQ to SQL-Objektmodell</span><span class="sxs-lookup"><span data-stu-id="a4be8-110">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="a4be8-111">Vorgehensweise: Anpassen von Entitätsklassen mit dem Code-Editor</span><span class="sxs-lookup"><span data-stu-id="a4be8-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
