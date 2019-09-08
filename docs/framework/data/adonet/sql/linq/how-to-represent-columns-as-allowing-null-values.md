---
title: 'Vorgehensweise: Darstellen von Spalten für die Zulassung von NULL-Werten'
ms.date: 03/30/2017
ms.assetid: ebb71a37-1f4c-4fa7-b2d2-d903f13c4af1
ms.openlocfilehash: 00a837467010c2d8a9f0ca16d6aba2fc5f4c973f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781806"
---
# <a name="how-to-represent-columns-as-allowing-null-values"></a>Vorgehensweise: Darstellen von Spalten für die Zulassung von NULL-Werten
Mit der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A> -Eigenschaft des <xref:System.Data.Linq.Mapping.ColumnAttribute> -Attributs können Sie angeben, dass die zugeordnete Daten Bank Spalte NULL-Werte enthalten kann.  
  
 Codebeispiele finden Sie unter <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>.  
  
### <a name="to-designate-a-column-as-allowing-null-values"></a>So kennzeichnen Sie eine Spalte für die Zulassung von NULL-Werten  
  
1. Fügen Sie die <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>-Eigenschaft dem <xref:System.Data.Linq.Mapping.ColumnAttribute>-Attribut hinzu.  
  
2. Legen Sie den <xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>-Eigenschaftswert auf `true` fest.  
  
## <a name="see-also"></a>Siehe auch

- [Das LINQ to SQL-Objektmodell](the-linq-to-sql-object-model.md)
- [Vorgehensweise: Anpassen von Entitäts Klassen mit dem Code-Editor](how-to-customize-entity-classes-by-using-the-code-editor.md)
