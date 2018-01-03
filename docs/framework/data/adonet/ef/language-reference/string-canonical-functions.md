---
title: Kanonische Zeichenfolgefunktionen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5e2cbebd-5df3-47c7-b0e2-49a17ab22bfb
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 89e1d99b5573f36fab4f2cfe675ab95e57a8fd2c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="string-canonical-functions"></a>Kanonische Zeichenfolgefunktionen
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] enthält kanonische Zeichenfolgenfunktionen.  
  
## <a name="remarks"></a>Hinweise  
 In der folgenden Tabelle sind die kanonischen [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Zeichenfolgenfunktionen aufgeführt.  
  
|Funktion|Beschreibung|  
|--------------|-----------------|  
|`Concat (` `string1`, `string2``)`|Gibt eine Zeichenfolge zurück, die `string2` enthält und an `string1` angehängt ist.<br /><br /> **Argumente**<br /><br /> `string1`: Die Zeichenfolge, an die `string2` angefügt wird.<br /><br /> `string2`: Die Zeichenfolge, die `string1` angefügt wird.<br /><br /> **Rückgabewert**<br /><br /> Ein `String`. Wenn die Länge der zurückgegebenen Wertzeichenfolge die zulässige Höchstlänge überschreitet, wird ein Fehler ausgegeben.<br /><br /> **Beispiel**<br /><br /> `-- The following example returns abcxyz.`<br /><br /> `Concat('abc', 'xyz')`|  
|`Contains (` `string`, `target``)`|Gibt `true` zurück, wenn `target` in `string` enthalten ist.<br /><br /> **Argumente**<br /><br /> `string`: Die Zeichenfolge, die gesucht wird.<br /><br /> `target`: Die Zielzeichenfolge, nach der gesucht wird.<br /><br /> **Rückgabewert**<br /><br /> `true`, wenn `target` in `string` enthalten ist, andernfalls `false`.<br /><br /> **Beispiel**<br /><br /> `-- The following example returns true.`<br /><br /> `Contains('abc', 'bc')`|  
|`EndsWith (` `string`, `target``)`|Gibt `true` zurück, wenn `target` mit `string` endet.<br /><br /> **Argumente**<br /><br /> `string`: Die Zeichenfolge, die gesucht wird.<br /><br /> `target`: Die Zielzeichenfolge, nach der am Ende der Zeichenfolge gesucht `string` wird.<br /><br /> **Rückgabewert**<br /><br /> `True` wenn `string` mit `target` endet, anderenfalls `false`.<br /><br /> **Beispiel**<br /><br /> `-- The following example returns true.`<br /><br /> `EndsWith('abc', 'bc')`**Hinweis:** bei Verwendung der [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)] Datenanbieter, um diese Funktion gibt `false` , wenn die Zeichenfolge in einer Zeichenfolgenspalte mit fester Länge gespeichert wird und `target` ist eine Konstante. In diesem Fall wird die ganze Zeichenfolge gesucht, einschließlich aller Auffüllleerzeichen. Eine mögliche Problemumgehung stellt die Kürzung der Daten in der Zeichenfolge mit fester Länge dar. Beispiel: `EndsWith(TRIM(string), target)`|  
|`IndexOf(` `target`, `string``)`|Gibt die Position von `target` in `string` oder, wenn nicht vorhanden, den Wert 0 zurück. Gibt 1 zurück, um den Anfang des `string` anzugeben. Indexbezifferung beginnt mit der Zahl 1.<br /><br /> **Argumente**<br /><br /> `target`: Die Zeichenfolge, nach der gesucht wird.<br /><br /> `string`: Die Zeichenfolge, die gesucht wird.<br /><br /> **Rückgabewert**<br /><br /> Eine `Int32`.<br /><br /> **Beispiel**<br /><br /> `-- The following example returns 4.`<br /><br /> `IndexOf('xyz', 'abcxyz')`|  
|`Left (` `string`, `length``)`|Gibt die ersten `length`-Zeichen von der linken Seite der `string` zurück. Wenn die Länge von `string` kleiner als `length` ist, wird die gesamte Zeichenfolge zurückgegeben.<br /><br /> **Argumente**<br /><br /> `string`: `String`<br /><br /> `length`: `Int16`,`Int32`, `Int64` oder `Byte`. `length` darf nicht kleiner 0 (Null) sein.<br /><br /> **Rückgabewert**<br /><br /> Ein `String`.<br /><br /> **Beispiel**<br /><br /> `-- The following example returns abc.`<br /><br /> `Left('abcxyz', 3)`|  
|`Length (` `string` `)`|Gibt die (`Int32`-)Länge der Zeichenfolge in Zeichen zurück.<br /><br /> **Argumente**<br /><br /> `string`: `String`<br /><br /> **Rückgabewert**<br /><br /> Eine `Int32`.<br /><br /> **Beispiel**<br /><br /> `-- The following example returns 6.`<br /><br /> `Legth('abcxyz')`|  
|`LTrim(` `string` `)`|Gibt `string` ohne führendes Leerzeichen zurück.<br /><br /> **Argumente**<br /><br /> Ein `String`.<br /><br /> **Rückgabewert**<br /><br /> Ein `String`.<br /><br /> **Beispiel**<br /><br /> `-- The following example returns abc.`<br /><br /> `LTrim('   abc')`|  
|`Replace (` `string1`, `string2`, `string3``)`|Gibt `string1` mit allen Vorkommen von `string2` zurück, die durch `string3` ersetzt wurden.<br /><br /> **Argumente**<br /><br /> Ein `String`.<br /><br /> **Rückgabewert**<br /><br /> Ein `String`.<br /><br /> **Beispiel**<br /><br /> `-- The following example returns abcxyz.`<br /><br /> `Concat('abc', 'xyz')`|  
|`Reverse (` `string` `)`|Gibt `string` mit umgekehrter Reihenfolge der Zeichen zurück.<br /><br /> **Argumente**<br /><br /> Ein `String`.<br /><br /> **Rückgabewert**<br /><br /> Ein `String`.<br /><br /> **Beispiel**<br /><br /> `-- The following example returns dcba.`<br /><br /> `Reverse('abcd')`|  
|`Right (` `string`, `length``)`|Gibt den letzten `length` Zeichen aus dem `string`. Wenn die Länge von `string` kleiner als `length` ist, wird die gesamte Zeichenfolge zurückgegeben.<br /><br /> **Argumente**<br /><br /> `string`: `String`<br /><br /> `length`: `Int16`,`Int32`, `Int64` oder `Byte`. `length` darf nicht kleiner 0 (Null) sein.<br /><br /> **Rückgabewert**<br /><br /> Ein `String`.<br /><br /> **Beispiel**<br /><br /> `-- The following example returns xyz.`<br /><br /> `Right('abcxyz', 3)`|  
|`RTrim(` `string` `)`|Gibt `string` ohne nachstehendes Leerzeichen zurück.<br /><br /> **Argumente**<br /><br /> Ein `String`.<br /><br /> **Rückgabewert**<br /><br /> Ein `String`.|  
|`Substring (` `string`, `start`, `length``)`|Gibt die Teilzeichenfolge der Zeichenfolge mit einer Länge von `start` Zeichen zurück, die an der Position `length` beginnt. Mit dem Startwert 1 wird das erste Zeichen der Zeichenfolge angegeben. Indexbezifferung beginnt mit der Zahl 1.<br /><br /> **Argumente**<br /><br /> `string`: `String`<br /><br /> `start`: `Int16`, `Int32`, `Int64` und `Byte`. `start` darf nicht kleiner 1 sein.<br /><br /> `length`: `Int16`, `Int32`, `Int64` und `Byte`. `length` darf nicht kleiner 0 (Null) sein.<br /><br /> **Rückgabewert**<br /><br /> Ein `String`.<br /><br /> **Beispiel**<br /><br /> `-- The following example returns xyz.`<br /><br /> `Substring('abcxyz', 4, 3)`|  
|`StartsWith (` `string`, `target``)`|Gibt `true` zurück, wenn `string` mit `target` beginnt.<br /><br /> **Argumente**<br /><br /> `string`: Die Zeichenfolge, die gesucht wird.<br /><br /> `target`: Die Zielzeichenfolge, nach der am Anfang der Zeichenfolge gesucht `string` wird.<br /><br /> **Rückgabewert**<br /><br /> `True` wenn `string` mit `target` beginnt, anderenfalls `false`.<br /><br /> **Beispiel**<br /><br /> `-- The following example returns true.`<br /><br /> `StartsWith('abc', 'ab')`|  
|`ToLower(` `string` `)`|Gibt `string` mit in Kleinbuchstaben umgewandelten Großbuchstaben zurück.<br /><br /> **Argumente**<br /><br /> Ein `String`.<br /><br /> **Rückgabewert**<br /><br /> Ein `String`.<br /><br /> **Beispiel**<br /><br /> `-- The following example returns abc.`<br /><br /> `ToLower('ABC')`|  
|`ToUpper(` `string` `)`|Gibt `string` mit in Großbuchstaben umgewandelten Kleinbuchstaben zurück.<br /><br /> **Argumente**<br /><br /> Ein `String`.<br /><br /> **Rückgabewert**<br /><br /> Ein `String`.<br /><br /> **Beispiel**<br /><br /> `-- The following example returns ABC.`<br /><br /> `ToUpper('abc')`|  
|`Trim(` `string` `)`|Gibt `string` ohne führende und nachstehende Leerzeichen zurück.<br /><br /> **Argumente**<br /><br /> Ein `String`.<br /><br /> **Rückgabewert**<br /><br /> Ein `String`.<br /><br /> **Beispiel**<br /><br /> `-- The following example returns abc.`<br /><br /> `Trim('      abc   ')`|  
  
 Diese Funktionen geben `null` zurück, wenn die Eingabe `null` ist.  
  
 Entsprechende Funktionen sind für den verwalteten Anbieter des Microsoft SQL-Clients verfügbar. Weitere Informationen finden Sie unter [SqlClient für Entity Framework-Funktionen](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Canonical Functions (Kanonische Funktionen)](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)
