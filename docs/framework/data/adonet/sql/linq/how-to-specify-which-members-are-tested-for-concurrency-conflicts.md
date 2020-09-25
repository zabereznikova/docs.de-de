---
title: 'Vorgehensweise: Angeben, welche Member auf Parallelitätskonflikte getestet werden'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d2cda293-1e2f-4878-af0e-5aaf0d092120
ms.openlocfilehash: e774935827934ae73873247def049b4045535272
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197143"
---
# <a name="how-to-specify-which-members-are-tested-for-concurrency-conflicts"></a>Vorgehensweise: Angeben, welche Member auf Parallelitätskonflikte getestet werden

Wenden Sie eine von drei Enumerationselementen auf die- [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A> Eigenschaft eines- <xref:System.Data.Linq.Mapping.ColumnAttribute> Attributs an, um anzugeben, welche Member in Update Überprüfungen zur Erkennung von Konflikten bei der vollständigen Parallelität eingeschlossen werden sollen.  
  
 Die <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>-Eigenschaft (zugeordnet zur Entwurfszeit) wird zusammen mit Funktionen für Laufzeitparallelität in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] verwendet. Weitere Informationen finden Sie unter vollständige Parallelität [: Übersicht](optimistic-concurrency-overview.md).  
  
> [!NOTE]
> Die ursprünglichen Memberwerte werden mit dem aktuellen Datenbankstatus verglichen, sofern kein Member als `IsVersion=true` gekennzeichnet ist. Weitere Informationen finden Sie unter <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>.  
  
 Codebeispiele finden Sie unter <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.  
  
### <a name="to-always-use-this-member-for-detecting-conflicts"></a>So verwenden Sie immer diesen Member zum Erkennen von Konflikten  
  
1. Fügen Sie die <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>-Eigenschaft dem <xref:System.Data.Linq.Mapping.ColumnAttribute>-Attribut hinzu.  
  
2. Legen Sie den <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>-Eigenschaftswert auf `Always` fest.  
  
### <a name="to-never-use-this-member-for-detecting-conflicts"></a>So verwenden Sie niemals diesen Member zum Erkennen von Konflikten  
  
1. Fügen Sie die <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>-Eigenschaft dem <xref:System.Data.Linq.Mapping.ColumnAttribute>-Attribut hinzu.  
  
2. Legen Sie den <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>-Eigenschaftswert auf `Never` fest.  
  
### <a name="to-use-this-member-for-detecting-conflicts-only-when-the-application-has-changed-the-value-of-the-member"></a>So verwenden Sie diesen Member nur dann zum Erkennen von Konflikten, wenn die Anwendung den Memberwert geändert hat  
  
1. Fügen Sie die <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>-Eigenschaft dem <xref:System.Data.Linq.Mapping.ColumnAttribute>-Attribut hinzu.  
  
2. Legen Sie den <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>-Eigenschaftswert auf `WhenChanged` fest.  
  
## <a name="example"></a>Beispiel  

 Das folgende Beispiel zeigt, dass diese `HomePage`-Objekte nie während der Updateprüfungen getestet werden sollten. Weitere Informationen finden Sie unter <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.  
  
 [!code-csharp[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.mapping.updatecheck/cs/northwind.cs#1)]
 [!code-vb[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.mapping.updatecheck/vb/northwind.vb#1)]  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Verwalten von Änderungskonflikten](how-to-manage-change-conflicts.md)
- [Vornehmen und Übergeben von Datenänderungen](making-and-submitting-data-changes.md)
