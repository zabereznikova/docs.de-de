---
title: Systemfunktionen
ms.date: 03/30/2017
ms.assetid: b7c71b58-09e6-44ce-a3e5-a0fdb892fb86
ms.openlocfilehash: 0d46429ac958e6f5db4d51947669784303af783b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91156497"
---
# <a name="system-functions"></a>Systemfunktionen

Der .NET Framework-Datenanbieter für SQL Server (SqlClient) stellt die folgenden Systemfunktionen zur Verfügung:  
  
|Funktion|Beschreibung|  
|--------------|-----------------|  
|`CHECKSUM (` `value`, [`value`, [`value`]]`)`|Gibt den Prüfsummenwert zurück. `CHECKSUM` wurde zum Erstellen von Hashindizes konzipiert.<br /><br /> **Argumente**<br /><br /> `value`: `Boolean` ,, `Byte` `Int16` , `Int32` , `Int64` , `Single` , `Decimal` , `Double` , `DateTime` , `String` , `Binary` Oder `Guid` . Sie können einen, zwei oder drei Werte angeben.<br /><br /> **Rückgabewert**<br /><br /> Der Absolutwert des angegebenen Ausdrucks.<br /><br /> **Beispiel**<br /><br /> `SqlServer.CHECKSUM(10,100,1000.0)`|  
|`CURRENT_TIMESTAMP ()`|Erzeugt das aktuelle Datum und die Uhrzeit im SQL Server-internen Format für `DateTime`-Werte mit einer Genauigkeit von 7 in SQL Server 2008 und einer Genauigkeit von 3 in SQL Server 2005.<br /><br /> **Rückgabewert**<br /><br /> Das aktuelle Systemdatum und die aktuelle Systemzeit als `DateTime`.<br /><br /> **Beispiel**<br /><br /> `SqlServer.CURRENT_TIMESTAMP()`|  
|`CURRENT_ USER` `()`|Gibt den Namen des aktuellen Benutzers zurück.<br /><br /> **Rückgabewert**<br /><br /> Ein ASCII-`String`.<br /><br /> **Beispiel**<br /><br /> `SqlServer.CURRENT_USER()`|  
|`DATALENGTH` `(` `expression` `)`|Gibt die Anzahl von Bytes zurück, die für die Darstellung eines Ausdrucks verwendet werden.<br /><br /> **Argumente**<br /><br /> `expression`: `Boolean` ,, `Byte` `Int16` , `Int32` , `Int64` , `Single` , `Decimal` , `Double` , `DateTime` , `Time` ,,, `DateTimeOffset` `String` `Binary` Oder `Guid` .<br /><br /> **Rückgabewert**<br /><br /> Die Größe von Eigenschaften als `Int32`.<br /><br /> **Beispiel**<br /><br /> `SELECT VALUE SqlServer.DATALENGTH(P.Name)FROM`<br /><br /> `AdventureWorksEntities.Product AS P`|  
|`HOST_NAME()`|Gibt den Namen der Arbeitsstation zurück.<br /><br /> **Rückgabewert**<br /><br /> Ein `String` (Unicode).<br /><br /> **Beispiel**<br /><br /> `SqlServer.HOST_NAME()`|  
|`ISDATE(` `expression` `)`|Ermittelt, ob der eingegebene Ausdruck ein gültiges Datum ist.<br /><br /> **Argumente**<br /><br /> `expression`: `Boolean` ,, `Byte` `Int16` , `Int32` , `Int64` , `Single` , `Decimal` , `Double` , `DateTime` , `Time` ,,, `DateTimeOffset` `String` `Binary` Oder `Guid` .<br /><br /> **Rückgabewert**<br /><br /> Eine `Int32`. Eins (1), wenn der eingegebene Ausdruck ein gültiges Datum ist. Andernfalls Null (0).<br /><br /> **Beispiel**<br /><br /> `SqlServer.ISDATE('1/1/2006')`|  
|`ISNUMERIC(` `expression` `)`|Ermittelt, ob ein Ausdruck ein gültiger numerischer Typ ist.<br /><br /> **Argumente**<br /><br /> `expression`: `Boolean` ,, `Byte` `Int16` , `Int32` , `Int64` , `Single` , `Decimal` , `Double` , `DateTime` , `Time` ,,, `DateTimeOffset` `String` `Binary` Oder `Guid` .<br /><br /> **Rückgabewert**<br /><br /> Eine `Int32`. Eins (1), wenn der eingegebene Ausdruck ein gültiges Datum ist. Andernfalls Null (0).<br /><br /> **Beispiel**<br /><br /> `SqlServer.ISNUMERIC('21')`|  
|`NEWID()`|Erstellt einen eindeutigen Wert vom Typ Guid.<br /><br /> **Rückgabewert**<br /><br /> Ein `Guid`.<br /><br /> **Beispiel**<br /><br /> `SqlServer.NEWID()`|  
|`USER_NAME(` `id` `)`|Gibt einen Datenbank-Benutzernamen über eine angegebene ID zurück.<br /><br /> **Argumente**<br /><br /> `expression`: Eine `Int32`-ID, die einem Datenbankbenutzer zugeordnet ist.<br /><br /> **Rückgabewert**<br /><br /> Ein `String` (Unicode).<br /><br /> **Beispiel**<br /><br /> `SqlServer.USER_NAME(0)`|  
  
 Weitere Informationen zu den `String` Funktionen, die SqlClient unterstützt, finden Sie unter [Zeichen folgen Funktionen (Transact-SQL)](/sql/t-sql/functions/string-functions-transact-sql).
  
## <a name="see-also"></a>Weitere Informationen

- [Entity SQL-Sprache](./language-reference/entity-sql-language.md)
- [SqlClient für Entity Framework-Funktionen](sqlclient-for-ef-functions.md)
