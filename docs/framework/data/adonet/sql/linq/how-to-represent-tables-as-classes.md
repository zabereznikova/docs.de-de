---
title: 'Vorgehensweise: Darstellen von Tabellen als Klassen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 84dda12b-88a2-4cd2-92b3-8db87b28d14c
ms.openlocfilehash: c02922351909b097dc06085eefbcc0f131350505
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166221"
---
# <a name="how-to-represent-tables-as-classes"></a>Vorgehensweise: Darstellen von Tabellen als Klassen

Verwenden Sie das- [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.TableAttribute> Attribut, um eine Klasse als Entitäts Klasse festzulegen, die einer Datenbanktabelle zugeordnet ist.  
  
### <a name="to-map-a-class-to-a-database-table"></a>So ordnen Sie einer Datenbanktabelle eine Klasse zu  
  
- Fügen Sie das <xref:System.Data.Linq.Mapping.TableAttribute>-Attribut der Klassendeklaration hinzu.  
  
## <a name="example"></a>Beispiel  

 Der folgende Code etabliert die `Customer`-Klasse als eine Entitätsklasse, die der `Customers`-Datenbanktabelle zugeordnet ist.  
  
 [!code-csharp[DLinqCustomize#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#1)]
 [!code-vb[DLinqCustomize#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#1)]  
  
 Sie müssen die <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A>-Eigenschaft nicht angeben, wenn der Name abgeleitet werden kann. Wenn Sie keinen Namen angeben, wird für diesen der Name der Eigenschaft oder des Felds angenommen.  
  
## <a name="see-also"></a>Weitere Informationen

- [Das LINQ to SQL-Objektmodell](the-linq-to-sql-object-model.md)
- [Vorgehensweise: Anpassen von Entitätsklassen mit dem Code-Editor](how-to-customize-entity-classes-by-using-the-code-editor.md)
