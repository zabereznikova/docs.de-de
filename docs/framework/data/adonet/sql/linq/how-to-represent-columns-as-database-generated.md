---
title: 'Vorgehensweise: Darstellen von Spalten als datenbankgeneriert'
ms.date: 03/30/2017
ms.assetid: 6524b8a6-e5d2-4a3b-8e08-beafc4a84fd2
ms.openlocfilehash: bb9510986581ad6d3bcd0711aed681ef3a7c4e45
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781786"
---
# <a name="how-to-represent-columns-as-database-generated"></a><span data-ttu-id="4b8ec-102">Vorgehensweise: Darstellen von Spalten als datenbankgeneriert</span><span class="sxs-lookup"><span data-stu-id="4b8ec-102">How to: Represent Columns as Database-Generated</span></span>
<span data-ttu-id="4b8ec-103">Verwenden Sie [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] die <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> -Eigenschaft <xref:System.Data.Linq.Mapping.ColumnAttribute> des-Attributs, um ein Feld oder eine Eigenschaft als Darstellung einer Daten Bank generierten Spalte festzulegen.</span><span class="sxs-lookup"><span data-stu-id="4b8ec-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate a field or property as representing a database-generated column.</span></span>  
  
 <span data-ttu-id="4b8ec-104">Codebeispiele finden Sie unter <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span><span class="sxs-lookup"><span data-stu-id="4b8ec-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span></span>  
  
### <a name="to-designate-a-field-or-property-as-representing-a-database-generated-column"></a><span data-ttu-id="4b8ec-105">So kennzeichnen Sie ein Feld oder eine Eigenschaft für die Darstellung einer datenbankgenerierten Spalte</span><span class="sxs-lookup"><span data-stu-id="4b8ec-105">To designate a field or property as representing a database-generated column</span></span>  
  
1. <span data-ttu-id="4b8ec-106">Fügen Sie die <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>-Eigenschaft dem <xref:System.Data.Linq.Mapping.ColumnAttribute>-Attribut hinzu.</span><span class="sxs-lookup"><span data-stu-id="4b8ec-106">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="4b8ec-107">Legen Sie den Wert der Eigenschaft auf `true` fest.</span><span class="sxs-lookup"><span data-stu-id="4b8ec-107">Set the property value to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b8ec-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4b8ec-108">See also</span></span>

- [<span data-ttu-id="4b8ec-109">Das LINQ to SQL-Objektmodell</span><span class="sxs-lookup"><span data-stu-id="4b8ec-109">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="4b8ec-110">Vorgehensweise: Anpassen von Entitäts Klassen mit dem Code-Editor</span><span class="sxs-lookup"><span data-stu-id="4b8ec-110">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
