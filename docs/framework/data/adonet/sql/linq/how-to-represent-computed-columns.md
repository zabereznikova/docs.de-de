---
title: 'Vorgehensweise: Darstellen von berechneten Spalten'
ms.date: 03/30/2017
ms.assetid: 4025f1fd-9dfa-46c0-b04f-34e8bc7957a2
ms.openlocfilehash: 01c3442448285893ebb476ed11889e073065d4d8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943547"
---
# <a name="how-to-represent-computed-columns"></a>Vorgehensweise: Darstellen von berechneten Spalten
Verwenden Sie [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] die <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> -Eigenschaft <xref:System.Data.Linq.Mapping.ColumnAttribute> für ein-Attribut, um eine Spalte darzustellen, deren Inhalt das Ergebnis der Berechnung ist.  
  
 Codebeispiele finden Sie unter <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>.  
  
> [!NOTE]
> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] unterstützt keine berechneten Spalten als Primärschlüssel.  
  
### <a name="to-represent-a-computed-column"></a>So stellen Sie eine berechnete Spalte dar  
  
1. Fügen Sie die <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>-Eigenschaft dem <xref:System.Data.Linq.Mapping.ColumnAttribute>-Attribut hinzu.  
  
2. Weisen Sie der <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>-Eigenschaft eine Zeichenfolgendarstellung der Formel zu.  
  
## <a name="see-also"></a>Siehe auch

- [Das LINQ to SQL-Objektmodell](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [Vorgehensweise: Anpassen von Entitäts Klassen mit dem Code-Editor](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
