---
title: Verwenden von Befehlen zum Ändern von Daten
ms.date: 03/30/2017
ms.assetid: f4160389-b9ff-4b74-b655-437c76dcd586
ms.openlocfilehash: cec079d16c6dc3d98cee9bf17b4201654e9ba10a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54509266"
---
# <a name="using-commands-to-modify-data"></a>Verwenden von Befehlen zum Ändern von Daten
Mit einem .NET Framework-Datenanbieter können gespeicherte Prozeduren oder Datendefinitionssprachen-Anweisungen (z. B. CREATE TABLE und ALTER COLUMN) ausgeführt werden, um eine Schemabearbeitung an einer Datenbank oder einem Katalog vorzunehmen. Mit diesen Befehlen werden keine Zeilen zurückgegeben, wie eine Abfrage, sodass der **Befehl** -Objekt bietet eine **ExecuteNonQuery** für die Verarbeitung.  
  
 Zusätzlich zur Verwendung von **ExecuteNonQuery** Schema ändern, können Sie auch diese Methode, um SQL-Anweisungen verarbeiten, die Daten ändern, aber, die nicht Zeilen zurückgeben, z. B. INSERT, UPDATE und DELETE, verwenden.  
  
 Zwar von keine Zeilen zurückgegeben werden die **ExecuteNonQuery** -Methode, die Eingabeparameter, Ausgabeparameter und Rückgabewerte übergeben und zurückgegeben wird, über die **Parameter** Auflistung von der **Befehl**  Objekt.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Aktualisieren von Daten in einer Datenquelle](../../../../docs/framework/data/adonet/updating-data-in-a-data-source.md)  
 Beschreibt das Ausführen von Befehlen oder gespeicherten Prozeduren, mit denen Daten in einer Datenbank geändert werden.  
  
 [Ausführen von Katalogoperationen](../../../../docs/framework/data/adonet/performing-catalog-operations.md)  
 Beschreibt das Ausführen von Befehlen, mit denen ein Datenbankschema geändert wird.  
  
## <a name="see-also"></a>Siehe auch
- [Abrufen und Ändern von Daten in ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [Befehle und Parameter](../../../../docs/framework/data/adonet/commands-and-parameters.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
