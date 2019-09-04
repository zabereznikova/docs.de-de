---
title: Funktionen für Datum und Zeit
ms.date: 03/30/2017
ms.assetid: 971762d0-663b-4b64-8c61-352a8e6d3949
ms.openlocfilehash: fe70795ba98cf500f2066980d259ff995c3398e0
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251640"
---
# <a name="date-and-time-functions"></a>Funktionen für Datum und Zeit
Der .NET Framework-Datenanbieter für SQL Server (SqlClient) stellt Funktionen für Datum und Uhrzeit bereit, die einen `System.DateTime`-Eingabewert verarbeiten und ein Ergebnis vom Typ `string` oder `System.DateTime` bzw. einen numerischen Wert zurückgeben. Diese Funktionen befinden sich im SQLServer-Namespace, der bei der Verwendung von SqlClient verfügbar ist. Anhand der Namespaceigenschaft des Anbieters kann Entity Framework ermitteln, welches Präfix von diesem Anbieter für spezifische Konstrukte, wie Typen und Funktionen, verwendet wird. In der folgenden Tabelle werden die Datums-und Uhrzeit Funktionen von SqlClient aufgeführt.  
  
|Funktion|Beschreibung|  
|--------------|-----------------|  
|`DATEADD(datepart, number, date)`|Gibt einen neuen `DateTime`-Wert zurück, der berechnet wird, indem zum angegebenen Datum ein Intervall addiert wird.<br /><br /> **Argumente**<br /><br /> `datepart`: Ein `String` , der den Teil des Datums darstellt, für den ein neuer Wert zurückgegeben werden soll.<br /><br /> `number`: Der Wert vom Typ `Int32`, `Int64`, `Decimal` oder `Double`, um den `datepart` erhöht wird.<br /><br /> `date:`Ein Ausdruck, der ein `DateTime`-, `DateTimeOffset`-oder `Time` -Zeichen mit einer Genauigkeit von = [0-7] oder eine Zeichenfolge in einem Datumsformat zurückgibt.<br /><br /> **Rückgabewert**<br /><br /> Ein neuer `DateTime`-, `DateTimeOffset`- oder `Time`-Wert mit einer Genauigkeit von = [0-7].<br /><br /> **Beispiel**<br /><br /> `SqlServer.DATEADD('day', 22, cast('6/9/2006' as DateTime))`|  
|`DATEDIFF(datepart,startdate,enddate)`|Gibt die Anzahl der Datums- und Zeitgrenzen zurück, die zwischen zwei Daten überschritten werden.<br /><br /> **Argumente**<br /><br /> `datepart`: Ein `String` , der den Teil des Datums zum Berechnen des Unterschieds darstellt.<br /><br /> `startdate`: Ein Startdatum für die Berechnung ist ein Ausdruck, der einen `DateTime`-, `DateTimeOffset`-oder `Time` -Wert mit einer Genauigkeit von = [0-7] oder eine Zeichenfolge in einem Datumsformat zurückgibt.<br /><br /> `enddate:`Ein Enddatum für die Berechnung ist ein Ausdruck, der einen `DateTime`-, `DateTimeOffset`-oder `Time` -Wert mit einer Genauigkeit von = [0-7] oder eine Zeichenfolge in einem Datumsformat zurückgibt.<br /><br /> **Rückgabewert**<br /><br /> Eine `Int32`.<br /><br /> **Beispiel**<br /><br /> `SqlServer.DATEDIFF('day', cast('6/9/2006' as DateTime),`<br /><br /> `cast('6/20/2006' as DateTime))`|  
|`DATENAME(datepart, date)`|Gibt eine Zeichenfolge zurück, die den Datumsteil des angegebenen Datums darstellt.<br /><br /> **Argumente**<br /><br /> `datepart`: Ein `String` , der den Teil des Datums darstellt, für den ein neuer Wert zurückgegeben werden soll.<br /><br /> `date`: Ein Ausdruck, der einen `DateTime,` - `DateTimeOffset`oder `Time` -Wert mit einer Genauigkeit von = [0-7] oder eine Zeichenfolge in einem Datumsformat zurückgibt.<br /><br /> **Rückgabewert**<br /><br /> Die Zeichenfolge, die den angegebenen Datumsteil des angegebenen Datums darstellt.<br /><br /> **Beispiel**<br /><br /> `SqlServer.DATENAME('year', cast('6/9/2006' as DateTime))`|  
|`DATEPART(datepart, date)`|Gibt eine ganze Zahl zurück, die den angegebenen Teil des angegebenen Datums darstellt.<br /><br /> **Argumente**<br /><br /> `datepart`: Ein `String` , der den Teil des Datums darstellt, für den ein neuer Wert zurückgegeben werden soll.<br /><br /> `date`: Ein Ausdruck, der einen `DateTime,` `DateTimeOffset,` `Time` -oder-Wert mit einer Genauigkeit von = [0-7] oder eine Zeichenfolge in einem Datumsformat zurückgibt.<br /><br /> **Rückgabewert**<br /><br /> Der angegebene Datumsteil des angegebenen Datums als `Int32`-Wert.<br /><br /> **Beispiel**<br /><br /> `SqlServer.DATEPART('year', cast('6/9/2006' as DateTime))`|  
|`DAY(date)`|Gibt den Tag des angegebenen Datums als Ganzzahl zurück.<br /><br /> **Argumente**<br /><br /> `date`: Ein Ausdruck vom Typ `DateTime` oder `DateTimeOffset` mit einer Genauigkeit von = 0-7.<br /><br /> **Rückgabewert**<br /><br /> Der Tag des angegebenen Datums als `Int32`-Wert.<br /><br /> **Beispiel**<br /><br /> `SqlServer.DAY(cast('6/9/2006' as DateTime))`|  
|`GETDATE()`|Erstellt die aktuellen Werte für Datum und Uhrzeit im internen SQL Server-Format für datetime-Werte.<br /><br /> **Rückgabewert**<br /><br /> Das aktuelle Systemdatum und die aktuelle Systemzeit als `DateTime`-Wert mit einer Genauigkeit von 3.<br /><br /> **Beispiel**<br /><br /> `SqlServer.GETDATE()`|  
|`GETUTCDATE()`|Erstellt den datetime-Wert im UTC-Format (koordinierte Weltzeit oder GMT).<br /><br /> **Rückgabewert**<br /><br /> Der `DateTime`-Wert mit einer Genauigkeit von 3 im UTC-Format.<br /><br /> **Beispiel**<br /><br /> `SqlServer.GETUTCDATE()`|  
|`MONTH(date)`|Gibt den Monat des angegebenen Datums als Ganzzahl zurück.<br /><br /> **Argumente**<br /><br /> `date`: Ein Ausdruck vom Typ `DateTime` oder `DateTimeOffset` mit einer Genauigkeit von = 0-7.<br /><br /> **Rückgabewert**<br /><br /> Der Monat des angegebenen Datums als `Int32`-Wert.<br /><br /> **Beispiel**<br /><br /> `SqlServer.MONTH(cast('6/9/2006' as DateTime))`|  
|`YEAR(date)`|Gibt das Jahr des angegebenen Datums als Ganzzahl zurück.<br /><br /> **Argumente**<br /><br /> `date`: Ein Ausdruck vom Typ `DateTime` oder `DateTimeOffset` mit einer Genauigkeit von = 0-7.<br /><br /> **Rückgabewert**<br /><br /> Das Jahr des angegebenen Datums als `Int32`-Wert.<br /><br /> **Beispiel**<br /><br /> `SqlServer.YEAR(cast('6/9/2006' as DateTime))`|  
|`SYSDATETIME()`|Gibt einen `DateTime`-Wert mit einer Genauigkeit von 7 zurück.<br /><br /> **Rückgabewert**<br /><br /> Ein `DateTime`-Wert mit einer Genauigkeit von 7.<br /><br /> **Beispiel**<br /><br /> `SqlServer.SYSDATETIME()`|  
|`SYSUTCDATE()`|Erstellt den datetime-Wert im UTC-Format (koordinierte Weltzeit oder GMT).<br /><br /> **Rückgabewert**<br /><br /> Der `DateTime`-Wert mit einer Genauigkeit von = 7 im UTC-Format.<br /><br /> **Beispiel**<br /><br /> `SqlServer.SYSUTCDATE()`|  
|`SYSDATETIMEOFFSET()`|Gibt einen `DateTimeOffset`-Wert mit einer Genauigkeit von 7 zurück.<br /><br /> **Rückgabewert**<br /><br /> Ein `DateTimeOffset`-Wert mit einer Genauigkeit von 7 im UTC-Format.<br /><br /> **Beispiel**<br /><br /> `SqlServer.SYSDATETIMEOFFSET()`|  
  
 Weitere Informationen zu den von SqlClient unterstützten Datums- und Uhrzeitfunktionen finden Sie in der Dokumentation für die SQL Server-Version, die im SqlClient-Anbietermanifest angegeben wurde:  
  
|SQL Server 2000|SQL Server 2005|SQL Server 2008|  
|---------------------|---------------------|---------------------|  
|[Datums-und Uhrzeit Funktionen (Transact-SQL)](https://go.microsoft.com/fwlink/?LinkId=115908)|[Datums-und Uhrzeit Funktionen (Transact-SQL)](https://go.microsoft.com/fwlink/?LinkId=115909)|[Datums-und Uhrzeit Funktionen (Transact-SQL)](https://go.microsoft.com/fwlink/?LinkId=98360)|  
  
## <a name="see-also"></a>Siehe auch

- [SqlClient für Entity Framework-Funktionen](sqlclient-for-ef-functions.md)
