---
title: 'Vorgehensweise: Darstellen von berechneten Spalten'
ms.date: 03/30/2017
ms.assetid: 4025f1fd-9dfa-46c0-b04f-34e8bc7957a2
ms.openlocfilehash: df72562b303e5b9a7c31334df06926f157b59b05
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59324738"
---
# <a name="how-to-represent-computed-columns"></a>Vorgehensweise: Darstellen von berechneten Spalten
Verwenden der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> Eigenschaft für eine <xref:System.Data.Linq.Mapping.ColumnAttribute> Attribut für die Darstellung einer Spalteninhalts, deren Inhalt das Ergebnis der Berechnung sind.  
  
 Codebeispiele finden Sie unter <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.  
  
> [!NOTE]
>  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] unterstützt keine berechneten Spalten als Primärschlüssel.  
  
### <a name="to-represent-a-computed-column"></a>So stellen Sie eine berechnete Spalte dar  
  
1. Fügen Sie die <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>-Eigenschaft dem <xref:System.Data.Linq.Mapping.ColumnAttribute>-Attribut hinzu.  
  
2. Weisen Sie der <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>-Eigenschaft eine Zeichenfolgendarstellung der Formel zu.  
  
## <a name="see-also"></a>Siehe auch

- [Das LINQ to SQL-Objektmodell](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [Vorgehensweise: Anpassen von Entitätsklassen mit dem Code-Editor](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
