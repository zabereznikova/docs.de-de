---
title: 'Vorgehensweise: Darstellen von Spalten als datenbankgeneriert'
ms.date: 03/30/2017
ms.assetid: 6524b8a6-e5d2-4a3b-8e08-beafc4a84fd2
ms.openlocfilehash: 914fdcb78efbaaddf08330e32e1d7f7c4e62436e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166312"
---
# <a name="how-to-represent-columns-as-database-generated"></a><span data-ttu-id="0193c-102">Vorgehensweise: Darstellen von Spalten als datenbankgeneriert</span><span class="sxs-lookup"><span data-stu-id="0193c-102">How to: Represent Columns as Database-Generated</span></span>

<span data-ttu-id="0193c-103">Verwenden Sie die- [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> Eigenschaft des- <xref:System.Data.Linq.Mapping.ColumnAttribute> Attributs, um ein Feld oder eine Eigenschaft als Darstellung einer Daten Bank generierten Spalte festzulegen.</span><span class="sxs-lookup"><span data-stu-id="0193c-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate a field or property as representing a database-generated column.</span></span>  
  
 <span data-ttu-id="0193c-104">Codebeispiele finden Sie unter <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span><span class="sxs-lookup"><span data-stu-id="0193c-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span></span>  
  
### <a name="to-designate-a-field-or-property-as-representing-a-database-generated-column"></a><span data-ttu-id="0193c-105">So kennzeichnen Sie ein Feld oder eine Eigenschaft für die Darstellung einer datenbankgenerierten Spalte</span><span class="sxs-lookup"><span data-stu-id="0193c-105">To designate a field or property as representing a database-generated column</span></span>  
  
1. <span data-ttu-id="0193c-106">Fügen Sie die <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>-Eigenschaft dem <xref:System.Data.Linq.Mapping.ColumnAttribute>-Attribut hinzu.</span><span class="sxs-lookup"><span data-stu-id="0193c-106">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="0193c-107">Legen Sie den Eigenschaftswert auf `true` fest.</span><span class="sxs-lookup"><span data-stu-id="0193c-107">Set the property value to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0193c-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0193c-108">See also</span></span>

- [<span data-ttu-id="0193c-109">Das LINQ to SQL-Objektmodell</span><span class="sxs-lookup"><span data-stu-id="0193c-109">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="0193c-110">Vorgehensweise: Anpassen von Entitätsklassen mit dem Code-Editor</span><span class="sxs-lookup"><span data-stu-id="0193c-110">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
