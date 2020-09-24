---
title: 'Vorgehensweise: Darstellen von Spalten als datenbankgeneriert'
ms.date: 03/30/2017
ms.assetid: 6524b8a6-e5d2-4a3b-8e08-beafc4a84fd2
ms.openlocfilehash: 914fdcb78efbaaddf08330e32e1d7f7c4e62436e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166312"
---
# <a name="how-to-represent-columns-as-database-generated"></a>Vorgehensweise: Darstellen von Spalten als datenbankgeneriert

Verwenden Sie die- [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A> Eigenschaft des- <xref:System.Data.Linq.Mapping.ColumnAttribute> Attributs, um ein Feld oder eine Eigenschaft als Darstellung einer Daten Bank generierten Spalte festzulegen.  
  
 Codebeispiele finden Sie unter <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>.  
  
### <a name="to-designate-a-field-or-property-as-representing-a-database-generated-column"></a>So kennzeichnen Sie ein Feld oder eine Eigenschaft für die Darstellung einer datenbankgenerierten Spalte  
  
1. Fügen Sie die <xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>-Eigenschaft dem <xref:System.Data.Linq.Mapping.ColumnAttribute>-Attribut hinzu.  
  
2. Legen Sie den Eigenschaftswert auf `true` fest.  
  
## <a name="see-also"></a>Weitere Informationen

- [Das LINQ to SQL-Objektmodell](the-linq-to-sql-object-model.md)
- [Vorgehensweise: Anpassen von Entitätsklassen mit dem Code-Editor](how-to-customize-entity-classes-by-using-the-code-editor.md)
