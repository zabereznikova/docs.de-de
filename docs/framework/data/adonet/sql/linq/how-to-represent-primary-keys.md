---
title: 'Vorgehensweise: Darstellen von Primärschlüsseln'
ms.date: 03/30/2017
ms.assetid: 63c65289-6539-42b2-8493-891c232018fa
ms.openlocfilehash: 02570176c8aef5cfdc7ba09fd6976f430900e8df
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166234"
---
# <a name="how-to-represent-primary-keys"></a><span data-ttu-id="8739c-102">Vorgehensweise: Darstellen von Primärschlüsseln</span><span class="sxs-lookup"><span data-stu-id="8739c-102">How to: Represent Primary Keys</span></span>

<span data-ttu-id="8739c-103">Verwenden Sie die- [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> Eigenschaft des- <xref:System.Data.Linq.Mapping.ColumnAttribute> Attributs, um eine Eigenschaft oder ein Feld anzugeben, die den Primärschlüssel für eine Daten Bank Spalte darstellen soll.</span><span class="sxs-lookup"><span data-stu-id="8739c-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate a property or field to represent the primary key for a database column.</span></span>  
  
 <span data-ttu-id="8739c-104">Codebeispiele finden Sie unter <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span><span class="sxs-lookup"><span data-stu-id="8739c-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.</span></span>  
  
> [!NOTE]
> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="8739c-105">unterstützt keine berechneten Spalten als Primärschlüssel.</span><span class="sxs-lookup"><span data-stu-id="8739c-105">does not support computed columns as primary keys.</span></span>  
  
### <a name="to-designate-a-property-or-field-as-a-primary-key"></a><span data-ttu-id="8739c-106">So legen Sie eine Eigenschaft oder ein Feld als Primärschlüssel fest</span><span class="sxs-lookup"><span data-stu-id="8739c-106">To designate a property or field as a primary key</span></span>  
  
1. <span data-ttu-id="8739c-107">Fügen Sie die <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>-Eigenschaft dem <xref:System.Data.Linq.Mapping.ColumnAttribute>-Attribut hinzu.</span><span class="sxs-lookup"><span data-stu-id="8739c-107">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="8739c-108">Geben Sie den Wert als `true` an.</span><span class="sxs-lookup"><span data-stu-id="8739c-108">Specify the value as `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8739c-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8739c-109">See also</span></span>

- [<span data-ttu-id="8739c-110">Das LINQ to SQL-Objektmodell</span><span class="sxs-lookup"><span data-stu-id="8739c-110">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="8739c-111">Vorgehensweise: Anpassen von Entitätsklassen mit dem Code-Editor</span><span class="sxs-lookup"><span data-stu-id="8739c-111">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
