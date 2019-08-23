---
title: 'Vorgehensweise: Darstellen von Primärschlüsseln'
ms.date: 03/30/2017
ms.assetid: 63c65289-6539-42b2-8493-891c232018fa
ms.openlocfilehash: 28c62798f965edfcffe1a156213c2481a8193b49
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943532"
---
# <a name="how-to-represent-primary-keys"></a><span data-ttu-id="a2447-102">Vorgehensweise: Darstellen von Primärschlüsseln</span><span class="sxs-lookup"><span data-stu-id="a2447-102">How to: Represent Primary Keys</span></span>
<span data-ttu-id="a2447-103">Verwenden Sie [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] die <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> -Eigenschaft <xref:System.Data.Linq.Mapping.ColumnAttribute> des-Attributs, um eine Eigenschaft oder ein Feld anzugeben, die den Primärschlüssel für eine Daten Bank Spalte darstellen soll.</span><span class="sxs-lookup"><span data-stu-id="a2447-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate a property or field to represent the primary key for a database column.</span></span>  
  
 <span data-ttu-id="a2447-104">Codebeispiele finden Sie unter <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span><span class="sxs-lookup"><span data-stu-id="a2447-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span></span>  
  
> [!NOTE]
> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="a2447-105">unterstützt keine berechneten Spalten als Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="a2447-105">does not support computed columns as primary keys.</span></span>  
  
### <a name="to-designate-a-property-or-field-as-a-primary-key"></a><span data-ttu-id="a2447-106">So legen Sie eine Eigenschaft oder ein Feld als Primärschlüssel fest</span><span class="sxs-lookup"><span data-stu-id="a2447-106">To designate a property or field as a primary key</span></span>  
  
1. <span data-ttu-id="a2447-107">Fügen Sie die <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>-Eigenschaft dem <xref:System.Data.Linq.Mapping.ColumnAttribute>-Attribut hinzu.</span><span class="sxs-lookup"><span data-stu-id="a2447-107">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="a2447-108">Geben Sie den Wert als `true` an.</span><span class="sxs-lookup"><span data-stu-id="a2447-108">Specify the value as `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2447-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a2447-109">See also</span></span>

- [<span data-ttu-id="a2447-110">Das LINQ to SQL-Objektmodell</span><span class="sxs-lookup"><span data-stu-id="a2447-110">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="a2447-111">Vorgehensweise: Anpassen von Entitäts Klassen mit dem Code-Editor</span><span class="sxs-lookup"><span data-stu-id="a2447-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
