---
title: 'Gewusst wie: Darstellen von Spalten als Klassenmember'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7ab28021-4d15-4d9c-bf2e-6ccc0daa7d1a
ms.openlocfilehash: 2de759d1b24ff1d5e354282e6299e7598f1698ae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-represent-columns-as-class-members"></a>Gewusst wie: Darstellen von Spalten als Klassenmember
Verwenden der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute> Attribut einer Datenbankspalte ein Feld oder eine Eigenschaft zugeordnet.  
  
### <a name="to-map-a-field-or-property-to-a-database-column"></a>So ordnen Sie einer Datenbankspalte ein Feld oder eine Eigenschaft zu  
  
-   Fügen Sie das <xref:System.Data.Linq.Mapping.ColumnAttribute>-Attribut der Eigenschaft oder Felddeklaration hinzu.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code weist das `CustomerID`-Feld in der `Customer`-Klasse der `CustomerID`-Spalte in der `Customers`-Datenbanktabelle zu.  
  
 [!code-csharp[DLinqCustomize#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#2)]
 [!code-vb[DLinqCustomize#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#2)]  
  
 Sie müssen die <xref:System.Data.Linq.Mapping.DataAttribute.Name%2A>-Eigenschaft nicht angeben, wenn der Name abgeleitet werden kann. Wenn Sie keinen Namen angeben, wird für diesen der Name der Eigenschaft oder des Felds angenommen.  
  
## <a name="see-also"></a>Siehe auch  
 [Das LINQ to SQL-Objektmodell](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [Vorgehensweise: Anpassen von Entitätsklassen mit dem Code-Editor](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
