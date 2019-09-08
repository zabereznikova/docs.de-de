---
title: 'Vorgehensweise: Angeben von Datenbankdatentypen'
ms.date: 03/30/2017
ms.assetid: 2228fdad-7e6a-4b1b-b4d1-79d0198b7c28
ms.openlocfilehash: 09ca8dc6fa440138523bcd2905335a04517dd806
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793275"
---
# <a name="how-to-specify-database-data-types"></a>Vorgehensweise: Angeben von Datenbankdatentypen
Verwenden Sie [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] die <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A> -Eigenschaft <xref:System.Data.Linq.Mapping.ColumnAttribute> für ein-Attribut, um den genauen Text anzugeben, der die Spalte in einer T-SQL-Tabellen Deklaration definiert.  
  
 Sie müssen die <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>-Eigenschaft nur dann angeben, wenn Sie planen, <xref:System.Data.Linq.DataContext.CreateDatabase%2A> zur Erstellung einer Datenbankinstanz einzusetzen.  
  
 Codebeispiele finden Sie unter <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>.  
  
### <a name="to-specify-text-to-define-a-data-type-in-a-t-sql-table"></a>So geben Sie Text an, um einen Datentyp in einer T-SQL-Tabelle zu definieren  
  
1. Fügen Sie die <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>-Eigenschaft dem <xref:System.Data.Linq.Mapping.ColumnAttribute>-Attribut hinzu.  
  
2. Legen Sie den Wert der <xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>-Eigenschaft auf den genauen Text fest, der von T-SQL verwendet wird.  
  
## <a name="see-also"></a>Siehe auch

- [Das LINQ to SQL-Objektmodell](the-linq-to-sql-object-model.md)
- [Vorgehensweise: Anpassen von Entitäts Klassen mit dem Code-Editor](how-to-customize-entity-classes-by-using-the-code-editor.md)
