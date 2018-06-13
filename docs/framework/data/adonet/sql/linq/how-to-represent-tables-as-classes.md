---
title: 'Gewusst wie: Darstellen von Tabellen als Klassen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 84dda12b-88a2-4cd2-92b3-8db87b28d14c
ms.openlocfilehash: 363efa4e4a6e3e7cfb757ee554e24a7963882278
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33362976"
---
# <a name="how-to-represent-tables-as-classes"></a><span data-ttu-id="c14f6-102">Gewusst wie: Darstellen von Tabellen als Klassen</span><span class="sxs-lookup"><span data-stu-id="c14f6-102">How to: Represent Tables as Classes</span></span>
<span data-ttu-id="c14f6-103">Verwenden der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.TableAttribute> Attribut um eine Klasse als Entitätsklasse, die einer Datenbanktabelle zugeordnet zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="c14f6-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.TableAttribute> attribute to designate a class as an entity class associated with a database table.</span></span>  
  
### <a name="to-map-a-class-to-a-database-table"></a><span data-ttu-id="c14f6-104">So ordnen Sie einer Datenbanktabelle eine Klasse zu</span><span class="sxs-lookup"><span data-stu-id="c14f6-104">To map a class to a database table</span></span>  
  
-   <span data-ttu-id="c14f6-105">Fügen Sie das <xref:System.Data.Linq.Mapping.TableAttribute>-Attribut der Klassendeklaration hinzu.</span><span class="sxs-lookup"><span data-stu-id="c14f6-105">Add the <xref:System.Data.Linq.Mapping.TableAttribute> attribute to the class declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c14f6-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c14f6-106">Example</span></span>  
 <span data-ttu-id="c14f6-107">Der folgende Code etabliert die `Customer`-Klasse als eine Entitätsklasse, die der `Customers`-Datenbanktabelle zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="c14f6-107">The following code establishes the `Customer` class as an entity class that is associated with the `Customers` database table.</span></span>  
  
 [!code-csharp[DLinqCustomize#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#1)]
 [!code-vb[DLinqCustomize#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#1)]  
  
 <span data-ttu-id="c14f6-108">Sie müssen die <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A>-Eigenschaft nicht angeben, wenn der Name abgeleitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="c14f6-108">You do not have to specify the <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> property if the name can be inferred.</span></span> <span data-ttu-id="c14f6-109">Wenn Sie keinen Namen angeben, wird für diesen der Name der Eigenschaft oder des Felds angenommen.</span><span class="sxs-lookup"><span data-stu-id="c14f6-109">If you do not specify a name, the name is presumed to be the same name as that of the property or field.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c14f6-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c14f6-110">See Also</span></span>  
 [<span data-ttu-id="c14f6-111">Das LINQ to SQL-Objektmodell</span><span class="sxs-lookup"><span data-stu-id="c14f6-111">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [<span data-ttu-id="c14f6-112">Vorgehensweise: Anpassen von Entitätsklassen mit dem Code-Editor</span><span class="sxs-lookup"><span data-stu-id="c14f6-112">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
