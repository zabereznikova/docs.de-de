---
title: 'Vorgehensweise: Darstellen von Spalten als Zeitstempel- oder Versionsspalten'
ms.date: 03/30/2017
ms.assetid: 5afd5ce8-1d20-4bc3-a34f-49d95449f493
ms.openlocfilehash: ef99e0420b328f94686e08256ecf229000467810
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793504"
---
# <a name="how-to-represent-columns-as-timestamp-or-version-columns"></a>Vorgehensweise: Darstellen von Spalten als Zeitstempel- oder Versionsspalten
Verwenden Sie [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] die <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> -Eigenschaft <xref:System.Data.Linq.Mapping.ColumnAttribute> des-Attributs, um ein Feld oder eine Eigenschaft anzugeben, das eine Daten Bank Spalte darstellt, die Daten Bank Zeitstempel oder Versionsnummern enthält.  
  
 Codebeispiele finden Sie unter <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.  
  
### <a name="to-designate-a-field-or-property-as-representing-a-timestamp-or-version-column"></a>So kennzeichnen Sie ein Feld oder eine Eigenschaft für die Darstellung einer Timestamp- oder Versionsspalte  
  
1. Fügen Sie die <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>-Eigenschaft dem <xref:System.Data.Linq.Mapping.ColumnAttribute>-Attribut hinzu.  
  
2. Legen Sie den <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>-Eigenschaftswert auf `true` fest.  
  
## <a name="see-also"></a>Siehe auch

- [Das LINQ to SQL-Objektmodell](the-linq-to-sql-object-model.md)
- [Vorgehensweise: Geben Sie an, welche Member auf Parallelitäts Konflikte getestet werden.](how-to-specify-which-members-are-tested-for-concurrency-conflicts.md)
- [Vorgehensweise: Anpassen von Entitäts Klassen mit dem Code-Editor](how-to-customize-entity-classes-by-using-the-code-editor.md)
