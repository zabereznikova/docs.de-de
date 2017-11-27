---
title: Vergleichen von GUID- und uniqueidentifier-Werten
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: aababd75-2335-43e3-ace8-4b7ae84191a8
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 7bdd8108261e1e1bc18dd636ba654f7fb6bed981
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="comparing-guid-and-uniqueidentifier-values"></a>Vergleichen von GUID- und uniqueidentifier-Werten
Der GUID-Datentyp (Globally Unique Identifier) in SQL Server wird durch den `uniqueidentifier`-Datentyp dargestellt, der einen 16-Byte-Binärwert speichert. Ein GUID ist eine Binärzahl, und wird hauptsächlich als Bezeichner verwendet, der in einem Netzwerk mit vielen Computern an vielen Standorten eindeutig sein muss. GUIDs können durch den Aufruf der Transact-SQL-Funktion NEWID erstellt werden und sind garantiert weltweit eindeutig. Weitere Informationen finden Sie in der Onlinedokumentation zu SQL Server unter "Using uniqueidentifier Data".  
  
## <a name="working-with-sqlguid-values"></a>Arbeiten mit SqlGuid-Werten  
 Da GUID-Werte lang und verwirrend sind, haben sie für Benutzer keine Bedeutung. Wenn zufällig generierte GUIDs für Schlüsselwerte verwendet werden und Sie viele Zeilen einfügen, erfolgt eine zufällige Eingabe/Ausgabe in den Indizes. Dies führt zu einer Beeinträchtigung der Leistung. GUIDs sind im Vergleich zu anderen Datentypen auch vergleichsweise groß. Daher ist die Verwendung von GUIDs im Allgemeinen nur für sehr begrenzte Szenarien empfehlenswert, für die kein anderer Datentyp passend ist.  
  
### <a name="comparing-guid-values"></a>Vergleichen von GUID-Werten  
 `uniqueidentifier`-Werte können zusammen mit Vergleichsoperatoren verwendet werden. Eine Sortierung wird allerdings nicht durch Vergleich der Bitmuster der beiden Werte implementiert. Die einzigen Operationen, die gegen zulässig sind eine `uniqueidentifier` Wert sind Vergleiche (=, <>, \<, >, \<=, > =) und das Überprüfen auf NULL (IS NULL und IS NOT NULL). Andere arithmetische Operationen sind nicht zulässig.  
  
 Sowohl <xref:System.Guid> als auch <xref:System.Data.SqlTypes.SqlGuid> verfügen über eine `CompareTo`-Methode zum Vergleichen unterschiedlicher GUID-Werte. `System.Guid.CompareTo` und `SqlTypes.SqlGuid.CompareTo` werden jedoch auf andere Weise implementiert. <xref:System.Data.SqlTypes.SqlGuid> implementiert `CompareTo` mit SQL Server-Verhalten. Die letzten sechs Bytes eines Werts haben die höchste Signifikanz. <xref:System.Guid> wertet alle 16 Bytes aus. Im folgenden Beispiel wird dieses unterschiedliche Verhalten veranschaulicht. Der erste Codeabschnitt zeigt unsortierte <xref:System.Guid>-Werte an, und der zweite Codeabschnitt zeigt die sortierten <xref:System.Guid>-Werte. Der dritte Abschnitt zeigt die sortierten <xref:System.Data.SqlTypes.SqlGuid>-Werte. Die Ausgabe wird unter der Codeauflistung gezeigt.  
  
 [!code-csharp[DataWorks SqlTypes.Guid#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlTypes.Guid/CS/source.cs#1)]
 [!code-vb[DataWorks SqlTypes.Guid#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlTypes.Guid/VB/source.vb#1)]  
  
 Dieses Beispiel liefert die folgenden Ergebnisse.  
  
```  
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
  
## <a name="see-also"></a>Siehe auch  
 [SQL Server Data Types and ADO.NET (SQL Server-Datentypen und ADO.NET)](../../../../../docs/framework/data/adonet/sql/sql-server-data-types.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
