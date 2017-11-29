---
title: Systemfunktionen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b7c71b58-09e6-44ce-a3e5-a0fdb892fb86
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: f2b7939371d99f8b503ac779f07b34f5fff497a4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="system-functions"></a>Systemfunktionen
Der .NET Framework-Datenanbieter für SQL Server (SqlClient) stellt die folgenden Systemfunktionen zur Verfügung:  
  
|Funktion|Beschreibung|  
|--------------|-----------------|  
|`CHECKSUM (` `value`, [`value`, [`value`]]`)`|Gibt den Prüfsummenwert zurück. `CHECKSUM` wurde zum Erstellen von Hashindizes konzipiert.<br /><br /> **Argumente**<br /><br /> `value`: Ein `Boolean`, `Byte`, `Int16`, `Int32`, `Int64`, `Single`, `Decimal`, `Double`, `DateTime`, `String`, `Binary`, oder `Guid`. Sie können einen, zwei oder drei Werte angeben.<br /><br /> **Rückgabewert**<br /><br /> Der Absolutwert des angegebenen Ausdrucks.<br /><br /> **Beispiel**<br /><br /> `SqlServer.CHECKSUM(10,100,1000.0)`|  
|`CURRENT_TIMESTAMP ()`|Erzeugt das aktuelle Datum und die Uhrzeit im SQL Server-internen Format für `DateTime`-Werte mit einer Genauigkeit von 7 in SQL Server 2008 und einer Genauigkeit von 3 in SQL Server 2005.<br /><br /> **Rückgabewert**<br /><br /> Das aktuelle Systemdatum und die aktuelle Systemzeit als `DateTime`.<br /><br /> **Beispiel**<br /><br /> `SqlServer.CURRENT_TIMESTAMP()`|  
|`CURRENT_ USER` `()`|Gibt den Namen des aktuellen Benutzers zurück.<br /><br /> **Rückgabewert**<br /><br /> Ein ASCII-`String`.<br /><br /> **Beispiel**<br /><br /> `SqlServer.CURRENT_USER()`|  
|`DATALENGTH` `(` `expression` `)`|Gibt die Anzahl von Bytes zurück, die für die Darstellung eines Ausdrucks verwendet werden.<br /><br /> **Argumente**<br /><br /> `expression`: Ein `Boolean`, `Byte`, `Int16`, `Int32`, `Int64`, `Single`, `Decimal`, `Double`, `DateTime`, `Time`, `DateTimeOffset`, `String`, `Binary`, oder `Guid`.<br /><br /> **Rückgabewert**<br /><br /> Die Größe von Eigenschaften als `Int32`.<br /><br /> **Beispiel**<br /><br /> `SELECT VALUE SqlServer.DATALENGTH(P.Name)FROM`<br /><br /> `AdventureWorksEntities.Product AS P`|  
|`HOST_NAME()`|Gibt den Namen der Arbeitsstation zurück.<br /><br /> **Rückgabewert**<br /><br /> Ein `String` (Unicode).<br /><br /> **Beispiel**<br /><br /> `SqlServer.HOST_NAME()`|  
|`ISDATE(` `expression` `)`|Ermittelt, ob der eingegebene Ausdruck ein gültiges Datum ist.<br /><br /> **Argumente**<br /><br /> `expression`: Ein `Boolean`, `Byte`, `Int16`, `Int32`, `Int64`, `Single`, `Decimal`, `Double`, `DateTime`, `Time`, `DateTimeOffset`, `String`, `Binary`, oder `Guid`.<br /><br /> **Rückgabewert**<br /><br /> Eine `Int32`. Eins (1), wenn der eingegebene Ausdruck ein gültiges Datum ist. Andernfalls Null (0).<br /><br /> **Beispiel**<br /><br /> `SqlServer.ISDATE('1/1/2006')`|  
|`ISNUMERIC(` `expression` `)`|Ermittelt, ob ein Ausdruck ein gültiger numerischer Typ ist.<br /><br /> **Argumente**<br /><br /> `expression`: Ein `Boolean`, `Byte`, `Int16`, `Int32`, `Int64`, `Single`, `Decimal`, `Double`, `DateTime`, `Time`, `DateTimeOffset`, `String`, `Binary`, oder `Guid`.<br /><br /> **Rückgabewert**<br /><br /> Eine `Int32`. Eins (1), wenn der eingegebene Ausdruck ein gültiges Datum ist. Andernfalls Null (0).<br /><br /> **Beispiel**<br /><br /> `SqlServer.ISNUMERIC('21')`|  
|`NEWID()`|Erstellt einen eindeutigen Wert vom Typ Guid.<br /><br /> **Rückgabewert**<br /><br /> Ein `Guid`.<br /><br /> **Beispiel**<br /><br /> `SqlServer.NEWID()`|  
|`USER_NAME(` `id` `)`|Gibt den Datenbank-Benutzernamen zur angegebenen ID zurück.<br /><br /> **Argumente**<br /><br /> `expression`: Eine `Int32`-ID, die einem Datenbankbenutzer zugeordnet ist.<br /><br /> **Rückgabewert**<br /><br /> Ein `String` (Unicode).<br /><br /> **Beispiel**<br /><br /> `SqlServer.USER_NAME(0)`|  
  
 Weitere Informationen zu den von SqlClient unterstützten Zeichenfolgenfunktionen finden Sie in der Dokumentation für die SQL Server-Version, die im SqlClient-Anbietermanifest angegeben wurde:  
  
|SQL Server 2000|SQL Server 2005|SQL Server 2008|  
|---------------------|---------------------|---------------------|  
|[System Funktionen Transact-SQL)](http://go.microsoft.com/fwlink/?LinkId=115918)|[System Funktionen Transact-SQL)](http://go.microsoft.com/fwlink/?LinkId=115917)|[Systemfunktionen (Transact-SQL)](http://go.microsoft.com/fwlink/?LinkId=115919)|  
  
## <a name="see-also"></a>Siehe auch  
 [Entity SQL Language (Entity SQL-Sprache)](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)  
 [SqlClient für Entity Framework-Funktionen](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md)
