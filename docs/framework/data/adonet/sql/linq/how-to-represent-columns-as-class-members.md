---
title: 'Vorgehensweise: Darstellen von Spalten als Klassenmember'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7ab28021-4d15-4d9c-bf2e-6ccc0daa7d1a
ms.openlocfilehash: e73b017b5a500a8c48b3fe22557f6c6619f3b227
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166351"
---
# <a name="how-to-represent-columns-as-class-members"></a><span data-ttu-id="46ead-102">Vorgehensweise: Darstellen von Spalten als Klassenmember</span><span class="sxs-lookup"><span data-stu-id="46ead-102">How to: Represent Columns as Class Members</span></span>

<span data-ttu-id="46ead-103">Verwenden Sie das- [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute> Attribut, um einer Daten Bank Spalte ein Feld oder eine Eigenschaft zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="46ead-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to associate a field or property with a database column.</span></span>  
  
### <a name="to-map-a-field-or-property-to-a-database-column"></a><span data-ttu-id="46ead-104">So ordnen Sie einer Datenbankspalte ein Feld oder eine Eigenschaft zu</span><span class="sxs-lookup"><span data-stu-id="46ead-104">To map a field or property to a database column</span></span>  
  
- <span data-ttu-id="46ead-105">Fügen Sie das <xref:System.Data.Linq.Mapping.ColumnAttribute>-Attribut der Eigenschaft oder Felddeklaration hinzu.</span><span class="sxs-lookup"><span data-stu-id="46ead-105">Add the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to the property or field declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="46ead-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="46ead-106">Example</span></span>  

 <span data-ttu-id="46ead-107">Der folgende Code weist das `CustomerID`-Feld in der `Customer`-Klasse der `CustomerID`-Spalte in der `Customers`-Datenbanktabelle zu.</span><span class="sxs-lookup"><span data-stu-id="46ead-107">The following code maps the `CustomerID` field in the `Customer` class to the `CustomerID` column in the `Customers` database table.</span></span>  
  
 [!code-csharp[DLinqCustomize#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#2)]
 [!code-vb[DLinqCustomize#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#2)]  
  
 <span data-ttu-id="46ead-108">Sie müssen die <xref:System.Data.Linq.Mapping.DataAttribute.Name%2A>-Eigenschaft nicht angeben, wenn der Name abgeleitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="46ead-108">You do not have to specify the <xref:System.Data.Linq.Mapping.DataAttribute.Name%2A> property if the name can be inferred.</span></span> <span data-ttu-id="46ead-109">Wenn Sie keinen Namen angeben, wird für diesen der Name der Eigenschaft oder des Felds angenommen.</span><span class="sxs-lookup"><span data-stu-id="46ead-109">If you do not specify a name, the name is presumed to be the same name as that of the property or field.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46ead-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="46ead-110">See also</span></span>

- [<span data-ttu-id="46ead-111">Das LINQ to SQL-Objektmodell</span><span class="sxs-lookup"><span data-stu-id="46ead-111">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="46ead-112">Vorgehensweise: Anpassen von Entitätsklassen mit dem Code-Editor</span><span class="sxs-lookup"><span data-stu-id="46ead-112">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
