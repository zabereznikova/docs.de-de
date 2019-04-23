---
title: 'Vorgehensweise: Darstellen von Spalten als datenbankgeneriert'
ms.date: 03/30/2017
ms.assetid: 6524b8a6-e5d2-4a3b-8e08-beafc4a84fd2
ms.openlocfilehash: 2803697c668a8e1dbbeb426ea41b64878f70c145
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59307911"
---
# <a name="how-to-represent-columns-as-database-generated"></a><span data-ttu-id="a3ab8-102">Vorgehensweise: Darstellen von Spalten als datenbankgeneriert</span><span class="sxs-lookup"><span data-stu-id="a3ab8-102">How to: Represent Columns as Database-Generated</span></span>
<span data-ttu-id="a3ab8-103">Verwenden der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> Eigenschaft für die <xref:System.Data.Linq.Mapping.ColumnAttribute> Attribut, um ein Feld oder eine Eigenschaft als Darstellung einer datenbankgenerierten Spalte zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="a3ab8-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> property on the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate a field or property as representing a database-generated column.</span></span>  
  
 <span data-ttu-id="a3ab8-104">Codebeispiele finden Sie unter <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span><span class="sxs-lookup"><span data-stu-id="a3ab8-104">For code examples, see <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.</span></span>  
  
### <a name="to-designate-a-field-or-property-as-representing-a-database-generated-column"></a><span data-ttu-id="a3ab8-105">So kennzeichnen Sie ein Feld oder eine Eigenschaft für die Darstellung einer datenbankgenerierten Spalte</span><span class="sxs-lookup"><span data-stu-id="a3ab8-105">To designate a field or property as representing a database-generated column</span></span>  
  
1. <span data-ttu-id="a3ab8-106">Fügen Sie die <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>-Eigenschaft dem <xref:System.Data.Linq.Mapping.ColumnAttribute>-Attribut hinzu.</span><span class="sxs-lookup"><span data-stu-id="a3ab8-106">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> property to the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute.</span></span>  
  
2. <span data-ttu-id="a3ab8-107">Legen Sie den Wert der Eigenschaft auf `true` fest.</span><span class="sxs-lookup"><span data-stu-id="a3ab8-107">Set the property value to `true`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3ab8-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a3ab8-108">See also</span></span>

- [<span data-ttu-id="a3ab8-109">Das LINQ to SQL-Objektmodell</span><span class="sxs-lookup"><span data-stu-id="a3ab8-109">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="a3ab8-110">Vorgehensweise: Anpassen von Entitätsklassen mit dem Code-Editor</span><span class="sxs-lookup"><span data-stu-id="a3ab8-110">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
