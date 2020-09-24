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
# <a name="how-to-represent-columns-as-class-members"></a>Vorgehensweise: Darstellen von Spalten als Klassenmember

Verwenden Sie das- [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute> Attribut, um einer Daten Bank Spalte ein Feld oder eine Eigenschaft zuzuordnen.  
  
### <a name="to-map-a-field-or-property-to-a-database-column"></a>So ordnen Sie einer Datenbankspalte ein Feld oder eine Eigenschaft zu  
  
- Fügen Sie das <xref:System.Data.Linq.Mapping.ColumnAttribute>-Attribut der Eigenschaft oder Felddeklaration hinzu.  
  
## <a name="example"></a>Beispiel  

 Der folgende Code weist das `CustomerID`-Feld in der `Customer`-Klasse der `CustomerID`-Spalte in der `Customers`-Datenbanktabelle zu.  
  
 [!code-csharp[DLinqCustomize#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#2)]
 [!code-vb[DLinqCustomize#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#2)]  
  
 Sie müssen die <xref:System.Data.Linq.Mapping.DataAttribute.Name%2A>-Eigenschaft nicht angeben, wenn der Name abgeleitet werden kann. Wenn Sie keinen Namen angeben, wird für diesen der Name der Eigenschaft oder des Felds angenommen.  
  
## <a name="see-also"></a>Weitere Informationen

- [Das LINQ to SQL-Objektmodell](the-linq-to-sql-object-model.md)
- [Vorgehensweise: Anpassen von Entitätsklassen mit dem Code-Editor](how-to-customize-entity-classes-by-using-the-code-editor.md)
