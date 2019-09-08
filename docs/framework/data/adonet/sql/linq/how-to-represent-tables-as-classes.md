---
title: 'Vorgehensweise: Darstellen von Tabellen als Klassen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 84dda12b-88a2-4cd2-92b3-8db87b28d14c
ms.openlocfilehash: 1169def4e0180b1d14103d4a968ff3ed56f63d0c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781756"
---
# <a name="how-to-represent-tables-as-classes"></a><span data-ttu-id="3f21a-102">Vorgehensweise: Darstellen von Tabellen als Klassen</span><span class="sxs-lookup"><span data-stu-id="3f21a-102">How to: Represent Tables as Classes</span></span>
<span data-ttu-id="3f21a-103">Verwenden Sie [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] das-Attribut, um eine Klasse als Entitäts Klasse festzulegen, die <xref:System.Data.Linq.Mapping.TableAttribute> einer Datenbanktabelle zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="3f21a-103">Use the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.TableAttribute> attribute to designate a class as an entity class associated with a database table.</span></span>  
  
### <a name="to-map-a-class-to-a-database-table"></a><span data-ttu-id="3f21a-104">So ordnen Sie einer Datenbanktabelle eine Klasse zu</span><span class="sxs-lookup"><span data-stu-id="3f21a-104">To map a class to a database table</span></span>  
  
- <span data-ttu-id="3f21a-105">Fügen Sie das <xref:System.Data.Linq.Mapping.TableAttribute>-Attribut der Klassendeklaration hinzu.</span><span class="sxs-lookup"><span data-stu-id="3f21a-105">Add the <xref:System.Data.Linq.Mapping.TableAttribute> attribute to the class declaration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3f21a-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3f21a-106">Example</span></span>  
 <span data-ttu-id="3f21a-107">Der folgende Code etabliert die `Customer`-Klasse als eine Entitätsklasse, die der `Customers`-Datenbanktabelle zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="3f21a-107">The following code establishes the `Customer` class as an entity class that is associated with the `Customers` database table.</span></span>  
  
 [!code-csharp[DLinqCustomize#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#1)]
 [!code-vb[DLinqCustomize#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#1)]  
  
 <span data-ttu-id="3f21a-108">Sie müssen die <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A>-Eigenschaft nicht angeben, wenn der Name abgeleitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="3f21a-108">You do not have to specify the <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> property if the name can be inferred.</span></span> <span data-ttu-id="3f21a-109">Wenn Sie keinen Namen angeben, wird für diesen der Name der Eigenschaft oder des Felds angenommen.</span><span class="sxs-lookup"><span data-stu-id="3f21a-109">If you do not specify a name, the name is presumed to be the same name as that of the property or field.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f21a-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3f21a-110">See also</span></span>

- [<span data-ttu-id="3f21a-111">Das LINQ to SQL-Objektmodell</span><span class="sxs-lookup"><span data-stu-id="3f21a-111">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="3f21a-112">Vorgehensweise: Anpassen von Entitäts Klassen mit dem Code-Editor</span><span class="sxs-lookup"><span data-stu-id="3f21a-112">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
