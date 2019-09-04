---
title: Bitweise kanonische Funktionen
ms.date: 03/30/2017
ms.assetid: 993868ca-16e3-47b6-9915-c29cd63b0a21
ms.openlocfilehash: 3c1f32acc7a035658198b807646c1ceb95dfed0b
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251296"
---
# <a name="bitwise-canonical-functions"></a>Bitweise kanonische Funktionen
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] enthält bitweise kanonische Funktionen.  
  
## <a name="remarks"></a>Hinweise  
 In der folgenden Tabelle sind die bitweisen kanonischen [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Funktionen aufgeführt. Diese Funktionen geben zurück `Null` , `Null` wenn Eingaben bereitgestellt werden. Der Rückgabetyp der Funktionen ist derselbe wie der Argumenttyp bzw. die Argumenttypen. Die Argumente müssen vom gleichen Typ sein, wenn der Funktion mehr als ein Argument übergeben wird. Um bitweise Vorgänge über verschiedene Typen hinweg auszuführen, müssen Sie explizit in denselben Typ umwandeln.  
  
|Funktion|Beschreibung|  
|--------------|-----------------|  
|`BitWiseAnd (` `value1` `,` `value2` `)`|Gibt die bitweise Konjunktion von `value1` und `value2` als Typ von `value1` und `value2` zurück.<br /><br /> **Argumente**<br /><br /> `Byte`, ,`Int16` Und`Int64`. `Int32`<br /><br /> **Beispiel**<br /><br /> `-- The following example returns 1.`<br /><br /> `BitWiseAnd(1,3)`|  
|`BitWiseNot (` `value` `)`|Gibt die bitweise Negation von `value` zurück.<br /><br /> **Argumente**<br /><br /> `Byte`, ,`Int16` Und`Int64`. `Int32`<br /><br /> **Beispiel**<br /><br /> `-- The following example returns -4.`<br /><br /> `BitWiseNot(3)`|  
|`BitWiseOr (` `value1` `,` `value2` `)`|Gibt die bitweise Disjunktion von `value1` und `value2` als Typ von `value1` und `value2` zurück.<br /><br /> **Argumente**<br /><br /> `Byte` ,`Int16`Und .`Int64` `Int32`<br /><br /> **Beispiel**<br /><br /> `-- The following example returns 3.`<br /><br /> `BitWiseOr(1,3)`|  
|`BitWiseXor (` `value1` `,` `value2` `)`|Gibt die bitweise ausschließende Disjunktion von `value1` und `value2` als Typ von `value1` und `value2` zurück.<br /><br /> **Argumente**<br /><br /> `Byte` ,`Int16`Und .`Int64` `Int32`<br /><br /> **Beispiel**<br /><br /> `-- The following example returns 2.`<br /><br /> `BitWiseXor (1,3)`|  
  
## <a name="see-also"></a>Siehe auch

- [Canonical Functions (Kanonische Funktionen)](canonical-functions.md)
