---
title: Kanonische Zeichenfolgefunktionen
ms.date: 03/30/2017
ms.assetid: 5e2cbebd-5df3-47c7-b0e2-49a17ab22bfb
ms.openlocfilehash: bfd18f0302b897dabd7c75118e3892df6153ea63
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59155284"
---
# <a name="string-canonical-functions"></a>Kanonische Zeichenfolgefunktionen
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] enthält kanonische Zeichenfolgenfunktionen.  
  
## <a name="remarks"></a>Hinweise  
 In der folgenden Tabelle sind die kanonischen [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Zeichenfolgenfunktionen aufgeführt.  
  
|Funktion|Beschreibung|  
|--------------|-----------------|  
|`Concat(string1, string2)`|Gibt eine Zeichenfolge zurück, die `string2` enthält und an `string1` angehängt ist.<br /><br /> **Argumente**<br /><br /> `string1`: Die Zeichenfolge, die die `string2` angefügt wird.<br /><br /> `string2`: Die Zeichenfolge, die hinzukommt `string1`.<br /><br /> **Rückgabewert**<br /><br /> Ein `String`. Wenn die Länge der zurückgegebenen Wertzeichenfolge die zulässige Höchstlänge überschreitet, wird ein Fehler ausgegeben.<br /><br /> **Beispiel**<br /><br /> `-- The following example returns abcxyz.`<br /><br /> `Concat('abc', 'xyz')`|  
|`Contains(string, target)`|Gibt `true` zurück, wenn `target` in `string` enthalten ist.<br /><br /> **Argumente**<br /><br /> `string`: Die Zeichenfolge, die durchsucht wird.<br /><br /> `target`: Die Zielzeichenfolge, nach dem gesucht wird.<br /><br /> **Rückgabewert**<br /><br /> `true` Wenn `target` befindet sich im `string`andernfalls `false`.<br /><br /> **Beispiel**<br /><br /> `-- The following example returns true.`<br /><br /> `Contains('abc', 'bc')`|  
|`EndsWith(string, target)`|Gibt `true` zurück, wenn `target` mit `string` endet.<br /><br /> **Argumente**<br /><br /> `string`: Die Zeichenfolge, die durchsucht wird.<br /><br /> `target`: Die Zielzeichenfolge gesucht, am Ende der `string`.<br /><br /> **Rückgabewert**<br /><br /> `True` Wenn `string` endet mit `target`andernfalls `false`.<br /><br /> **Beispiel**<br /><br /> `-- The following example returns true.`<br /><br /> `EndsWith('abc', 'bc')` ***Hinweis**:  Wenn Sie den Datenanbieter für SQL Server verwenden, um diese Funktion gibt `false` , wenn die Zeichenfolge in einer Zeichenfolgenspalte mit fester Länge gespeichert wird und `target` ist eine Konstante.IIn diesem Fall wird die ganze Zeichenfolge gesucht, einschließlich aller Auffüllleerzeichen.AEine mögliche problemumgehung besteht darin, um die Daten in die Zeichenfolge mit fester Länge, wie im folgenden Beispiel zu entfernen:`EndsWith(TRIM(string), target)`|  
|`IndexOf(target, string)`|Gibt die Position von `target` in `string` oder, wenn nicht vorhanden, den Wert 0 zurück. Gibt 1 zurück, um den Anfang des `string` anzugeben. Indexbezifferung beginnt mit der Zahl 1.<br /><br /> **Argumente**<br /><br /> `target`: Die Zeichenfolge, die nach der gesucht wird.<br /><br /> `string`: Die Zeichenfolge, die durchsucht wird.<br /><br /> **Rückgabewert**<br /><br /> Eine `Int32`.<br /><br /> **Beispiel**<br /><br /> `-- The following example returns 4.`<br /><br /> `IndexOf('xyz', 'abcxyz')`|  
|`Left(string, length)`|Gibt die ersten `length`-Zeichen von der linken Seite der `string` zurück. Wenn die Länge von `string` kleiner als `length` ist, wird die gesamte Zeichenfolge zurückgegeben.<br /><br /> **Argumente**<br /><br /> `string`: Ein `String`.<br /><br /> `length`: Ein `Int16`, `Int32`, `Int64`, oder `Byte`. `length` darf nicht kleiner als NULL sein.<br /><br /> **Rückgabewert**<br /><br /> Ein `String`.<br /><br /> **Beispiel**<br /><br /> `-- The following example returns abc.`<br /><br /> `Left('abcxyz', 3)`|  
|`Length(string)`|Gibt die (`Int32`-)Länge der Zeichenfolge in Zeichen zurück.<br /><br /> **Argumente**<br /><br /> `string`: Ein `String`.<br /><br /> **Rückgabewert**<br /><br /> Eine `Int32`.<br /><br /> **Beispiel**<br /><br /> `-- The following example returns 6.`<br /><br /> `Legth('abcxyz')`|  
|`LTrim(string)`|Gibt `string` ohne führende Leerzeichen.<br /><br /> **Argumente**<br /><br /> Ein `String`.<br /><br /> **Rückgabewert**<br /><br /> Ein `String`.<br /><br /> **Beispiel**<br /><br /> `-- The following example returns abc.`<br /><br /> `LTrim('   abc')`|  
|`Replace(string1, string2, string3)`|Gibt `string1` mit allen Vorkommen von `string2` zurück, die durch `string3` ersetzt wurden.<br /><br /> **Argumente**<br /><br /> Ein `String`.<br /><br /> **Rückgabewert**<br /><br /> Ein `String`.<br /><br /> **Beispiel**<br /><br /> `-- The following example returns abcxyz.`<br /><br /> `Concat('abc', 'xyz')`|  
|`Reverse(string)`|Gibt `string` mit umgekehrter Reihenfolge der Zeichen zurück.<br /><br /> **Argumente**<br /><br /> Ein `String`.<br /><br /> **Rückgabewert**<br /><br /> Ein `String`.<br /><br /> **Beispiel**<br /><br /> `-- The following example returns dcba.`<br /><br /> `Reverse('abcd')`|  
|`Right(string, length)`|Gibt das letzte `length` Zeichen aus dem `string`. Wenn die Länge von `string` kleiner als `length` ist, wird die gesamte Zeichenfolge zurückgegeben.<br /><br /> **Argumente**<br /><br /> `string`: Ein `String`.<br /><br /> `length`: Ein `Int16`, `Int32`, `Int64`, oder `Byte`. `length` darf nicht kleiner als NULL sein.<br /><br /> **Rückgabewert**<br /><br /> Ein `String`.<br /><br /> **Beispiel**<br /><br /> `-- The following example returns xyz.`<br /><br /> `Right('abcxyz', 3)`|  
|`RTrim(string)`|Gibt `string` ohne nachgestellte Leerzeichen.<br /><br /> **Argumente**<br /><br /> Ein `String`.<br /><br /> **Rückgabewert**<br /><br /> Ein `String`.|  
|`Substring(string, start, length)`|Gibt die Teilzeichenfolge der Zeichenfolge mit einer Länge von `start` Zeichen zurück, die an der Position `length` beginnt. Mit dem Startwert 1 wird das erste Zeichen der Zeichenfolge angegeben. Indexbezifferung beginnt mit der Zahl 1.<br /><br /> **Argumente**<br /><br /> `string`: Ein `String`.<br /><br /> `start`: Ein `Int16`, `Int32`, `Int64` und `Byte`. `start` Dies darf nicht kleiner als 1 sein.<br /><br /> `length`: Ein `Int16`, `Int32`, `Int64` und `Byte`. `length` darf nicht kleiner als NULL sein.<br /><br /> **Rückgabewert**<br /><br /> Ein `String`.<br /><br /> **Beispiel**<br /><br /> `-- The following example returns xyz.`<br /><br /> `Substring('abcxyz', 4, 3)`|  
|`StartsWith(string, target)`|Gibt `true` zurück, wenn `string` mit `target` beginnt.<br /><br /> **Argumente**<br /><br /> `string`: Die Zeichenfolge, die durchsucht wird.<br /><br /> `target`: Die Zielzeichenfolge zu Beginn gesucht `string`.<br /><br /> **Rückgabewert**<br /><br /> `True` Wenn `string` beginnt mit `target`andernfalls `false`.<br /><br /> **Beispiel**<br /><br /> `-- The following example returns true.`<br /><br /> `StartsWith('abc', 'ab')`|  
|`ToLower(string)`|Gibt `string` mit in Kleinbuchstaben umgewandelten Großbuchstaben zurück.<br /><br /> **Argumente**<br /><br /> Ein `String`.<br /><br /> **Rückgabewert**<br /><br /> Ein `String`.<br /><br /> **Beispiel**<br /><br /> `-- The following example returns abc.`<br /><br /> `ToLower('ABC')`|  
|`ToUpper(string)`|Gibt `string` mit in Großbuchstaben umgewandelten Kleinbuchstaben zurück.<br /><br /> **Argumente**<br /><br /> Ein `String`.<br /><br /> **Rückgabewert**<br /><br /> Ein `String`.<br /><br /> **Beispiel**<br /><br /> `-- The following example returns ABC.`<br /><br /> `ToUpper('abc')`|  
|`Trim(string)`|Gibt `string` ohne führende und nachfolgende Leerzeichen.<br /><br /> **Argumente**<br /><br /> Ein `String`.<br /><br /> **Rückgabewert**<br /><br /> Ein `String`.<br /><br /> **Beispiel**<br /><br /> `-- The following example returns abc.`<br /><br /> `Trim('      abc   ')`|  
  
 Diese Funktionen geben `null` zurück, wenn die Eingabe `null` ist.  
  
 Entsprechende Funktionen sind für den verwalteten Anbieter des Microsoft SQL-Clients verfügbar. Weitere Informationen finden Sie unter [SqlClient für Entity Framework-Funktionen](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).  
  
## <a name="see-also"></a>Siehe auch

- [Kanonische Funktionen](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)
