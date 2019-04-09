---
title: 'Vorgehensweise: Darstellen von Primärschlüsseln'
ms.date: 03/30/2017
ms.assetid: 63c65289-6539-42b2-8493-891c232018fa
ms.openlocfilehash: 714211046afcafab4c2b67bf9318cfbede314476
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59173211"
---
# <a name="how-to-represent-primary-keys"></a>Vorgehensweise: Darstellen von Primärschlüsseln
Verwenden der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A> Eigenschaft für die <xref:System.Data.Linq.Mapping.ColumnAttribute> Attribut, um eine Eigenschaft oder ein Feld zur Darstellung des primären Schlüssels für eine Datenbankspalte zu kennzeichnen.  
  
 Codebeispiele finden Sie unter <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>.  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] unterstützt keine berechnete Spalten als Primärschlüssel verwendet werden.  
  
### <a name="to-designate-a-property-or-field-as-a-primary-key"></a>So legen Sie eine Eigenschaft oder ein Feld als Primärschlüssel fest  
  
1.  Fügen Sie die <xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>-Eigenschaft dem <xref:System.Data.Linq.Mapping.ColumnAttribute>-Attribut hinzu.  
  
2.  Geben Sie den Wert als `true` an.  
  
## <a name="see-also"></a>Siehe auch

- [Das LINQ to SQL-Objektmodell](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [Vorgehensweise: Anpassen von Entitätsklassen mit dem Code-Editor](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
