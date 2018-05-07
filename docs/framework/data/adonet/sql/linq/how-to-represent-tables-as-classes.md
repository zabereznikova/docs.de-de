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
---
# <a name="how-to-represent-tables-as-classes"></a>Gewusst wie: Darstellen von Tabellen als Klassen
Verwenden der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.TableAttribute> Attribut um eine Klasse als Entitätsklasse, die einer Datenbanktabelle zugeordnet zu kennzeichnen.  
  
### <a name="to-map-a-class-to-a-database-table"></a>So ordnen Sie einer Datenbanktabelle eine Klasse zu  
  
-   Fügen Sie das <xref:System.Data.Linq.Mapping.TableAttribute>-Attribut der Klassendeklaration hinzu.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code etabliert die `Customer`-Klasse als eine Entitätsklasse, die der `Customers`-Datenbanktabelle zugeordnet ist.  
  
 [!code-csharp[DLinqCustomize#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#1)]
 [!code-vb[DLinqCustomize#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#1)]  
  
 Sie müssen die <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A>-Eigenschaft nicht angeben, wenn der Name abgeleitet werden kann. Wenn Sie keinen Namen angeben, wird für diesen der Name der Eigenschaft oder des Felds angenommen.  
  
## <a name="see-also"></a>Siehe auch  
 [Das LINQ to SQL-Objektmodell](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [Vorgehensweise: Anpassen von Entitätsklassen mit dem Code-Editor](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
