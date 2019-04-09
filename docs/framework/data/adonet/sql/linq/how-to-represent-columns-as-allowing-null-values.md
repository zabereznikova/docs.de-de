---
title: 'Vorgehensweise: Darstellen von Spalten für die Zulassung von NULL-Werten'
ms.date: 03/30/2017
ms.assetid: ebb71a37-1f4c-4fa7-b2d2-d903f13c4af1
ms.openlocfilehash: e3bab3f307bcba77e0d311b96fa79d5a0d01e937
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59169636"
---
# <a name="how-to-represent-columns-as-allowing-null-values"></a>Vorgehensweise: Darstellen von Spalten für die Zulassung von NULL-Werten
Verwenden der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> Eigenschaft für die <xref:System.Data.Linq.Mapping.ColumnAttribute> Attribut, um anzugeben, dass die zugehörige Datenbankspalte null-Werte aufnehmen kann.  
  
 Codebeispiele finden Sie unter <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.  
  
### <a name="to-designate-a-column-as-allowing-null-values"></a>So kennzeichnen Sie eine Spalte für die Zulassung von NULL-Werten  
  
1.  Fügen Sie die <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>-Eigenschaft dem <xref:System.Data.Linq.Mapping.ColumnAttribute>-Attribut hinzu.  
  
2.  Legen Sie den <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>-Eigenschaftswert auf `true` fest.  
  
## <a name="see-also"></a>Siehe auch

- [Das LINQ to SQL-Objektmodell](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [Vorgehensweise: Anpassen von Entitätsklassen mit dem Code-Editor](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
