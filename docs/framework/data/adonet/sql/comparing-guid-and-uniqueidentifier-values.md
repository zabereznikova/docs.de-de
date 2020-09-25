---
title: Vergleichen von GUID- und uniqueidentifier-Werten
description: Erfahren Sie, wie Sie GUID-Werte in den .NET Framework Datenanbieter für SQL Server erstellen und vergleichen, die durch den uniqueidentifier-Datentyp dargestellt werden.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: aababd75-2335-43e3-ace8-4b7ae84191a8
ms.openlocfilehash: 649093259747d045945c55e39edb1391708940cf
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173574"
---
# <a name="comparing-guid-and-uniqueidentifier-values"></a>Vergleichen von GUID- und uniqueidentifier-Werten

Der Datentyp GUID (Globally Unique Identifier) in SQL Server wird vom Datentyp `uniqueidentifier` dargestellt, der einen Binärwert mit 16 Bytes speichert. Ein GUID ist eine Binärzahl, und wird hauptsächlich als Bezeichner verwendet, der in einem Netzwerk mit vielen Computern an vielen Standorten eindeutig sein muss. GUIDs können durch Aufrufen der Transact-SQL-Funktion NEWID generiert werden und sind weltweit eindeutig. Weitere Informationen finden Sie unter [uniqueidentifier (Transact-SQL)](/sql/t-sql/data-types/uniqueidentifier-transact-sql).  
  
## <a name="working-with-sqlguid-values"></a>Arbeiten mit SqlGuid-Werten  

 Aufgrund ihrer langen und unverständlichen Werte sind GUIDs für Benutzer nicht aussagekräftig. Wenn zufällig generierte GUIDs für Schlüsselwerte verwendet werden und Sie viele Zeilen einfügen, erfolgen in Ihren Indizes zufällige E/A-Vorgänge, was sich negativ auf die Leistung auswirken kann. Außerdem sind GUIDs im Vergleich mit anderen Datentypen relativ lang. Generell wird empfohlen, GUIDs nur in sehr eng umgrenzten Szenarien zu verwenden, für die kein anderer Datentyp geeignet ist.  
  
### <a name="comparing-guid-values"></a>Vergleichen von GUID-Werten  

 Vergleichsoperatoren können mit `uniqueidentifier`-Werten verwendet werden. Allerdings erfolgt das Sortieren nicht durch Vergleichen der Bitmuster der beiden Werte. Die einzigen Vorgänge, die für einen Wert zulässig sind, `uniqueidentifier` sind Vergleiche (=,  <>, \<, > , \<=, > =) und die Überprüfung auf NULL (is NULL und is not null). Andere arithmetische Operationen sind nicht zulässig.  
  
 <xref:System.Guid> und <xref:System.Data.SqlTypes.SqlGuid> verfügen über eine `CompareTo`-Methode zum Vergleichen unterschiedlicher GUID-Werte. `System.Guid.CompareTo` und `SqlTypes.SqlGuid.CompareTo` werden jedoch unterschiedlich implementiert. <xref:System.Data.SqlTypes.SqlGuid> implementiert `CompareTo` mit SQL Server-Verhalten, wobei die letzten 6 Bytes eines Werts am signifikantesten sind. <xref:System.Guid> wertet alle 16 Bytes aus. Im folgenden Beispiel werden diese unterschiedlichen Verhaltensweisen veranschaulicht. Der erste Codeabschnitt zeigt unsortierte <xref:System.Guid>-Werte, der zweite die sortierten <xref:System.Guid>-Werte. Der dritte Abschnitt enthält die sortierten <xref:System.Data.SqlTypes.SqlGuid>-Werte. Die Ausgabe wird unter der Codeliste gezeigt.  
  
 [!code-csharp[DataWorks SqlTypes.Guid#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlTypes.Guid/CS/source.cs#1)]
 [!code-vb[DataWorks SqlTypes.Guid#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlTypes.Guid/VB/source.vb#1)]  
  
 Hierdurch werden folgende Ergebnisse generiert.  
  
```output  
Unsorted Guids:  
3aaaaaaa-bbbb-cccc-dddd-2eeeeeeeeeee  
2aaaaaaa-bbbb-cccc-dddd-1eeeeeeeeeee  
1aaaaaaa-bbbb-cccc-dddd-3eeeeeeeeeee  
  
Sorted Guids:  
1aaaaaaa-bbbb-cccc-dddd-3eeeeeeeeeee  
2aaaaaaa-bbbb-cccc-dddd-1eeeeeeeeeee  
3aaaaaaa-bbbb-cccc-dddd-2eeeeeeeeeee  
  
Sorted SqlGuids:  
2aaaaaaa-bbbb-cccc-dddd-1eeeeeeeeeee  
3aaaaaaa-bbbb-cccc-dddd-2eeeeeeeeeee  
1aaaaaaa-bbbb-cccc-dddd-3eeeeeeeeeee  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [SQL Server-Datentypen und ADO.NET](sql-server-data-types.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
