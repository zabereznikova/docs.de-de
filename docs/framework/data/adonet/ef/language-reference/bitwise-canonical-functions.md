---
title: Bitweise kanonische Funktionen
ms.date: 03/30/2017
ms.assetid: 993868ca-16e3-47b6-9915-c29cd63b0a21
ms.openlocfilehash: 67ae0302f6faf0fb7284bc0c4a53a90ba6d55e08
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91185261"
---
# <a name="bitwise-canonical-functions"></a>Bitweise kanonische Funktionen

[!INCLUDE[esql](../../../../../../includes/esql-md.md)] enthält bitweise kanonische Funktionen.  
  
## <a name="remarks"></a>Bemerkungen  

 In der folgenden Tabelle sind die bitweisen kanonischen [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Funktionen aufgeführt. Diese Funktionen geben zurück, `Null` Wenn `Null` Eingaben bereitgestellt werden. Der Rückgabetyp der Funktionen ist derselbe wie der Argumenttyp bzw. die Argumenttypen. Die Argumente müssen vom gleichen Typ sein, wenn der Funktion mehr als ein Argument übergeben wird. Zum Ausführen bitweiser Operationen für verschiedene Typen müssen diese explizit in den gleichen Typ umgewandelt werden.  
  
|Funktion|Beschreibung|  
|--------------|-----------------|  
|`BitWiseAnd (` `value1` `,`  `value2` `)`|Gibt die bitweise Konjunktion von `value1` und `value2` als Typ von `value1` und `value2` zurück.<br /><br /> **Argumente**<br /><br /> `Byte`, `Int16` , `Int32` Und `Int64` .<br /><br /> **Beispiel**<br /><br /> `-- The following example returns 1.`<br /><br /> `BitWiseAnd(1,3)`|  
|`BitWiseNot (` `value` `)`|Gibt die bitweise Negation von `value` zurück.<br /><br /> **Argumente**<br /><br /> `Byte`, `Int16` , `Int32` Und `Int64` .<br /><br /> **Beispiel**<br /><br /> `-- The following example returns -4.`<br /><br /> `BitWiseNot(3)`|  
|`BitWiseOr (` `value1` `,`  `value2` `)`|Gibt die bitweise Disjunktion von `value1` und `value2` als Typ von `value1` und `value2` zurück.<br /><br /> **Argumente**<br /><br /> `Byte`, `Int16` `Int32` Und `Int64` .<br /><br /> **Beispiel**<br /><br /> `-- The following example returns 3.`<br /><br /> `BitWiseOr(1,3)`|  
|`BitWiseXor (` `value1` `,`  `value2` `)`|Gibt die bitweise ausschließende Disjunktion von `value1` und `value2` als Typ von `value1` und `value2` zurück.<br /><br /> **Argumente**<br /><br /> `Byte`, `Int16` `Int32` Und `Int64` .<br /><br /> **Beispiel**<br /><br /> `-- The following example returns 2.`<br /><br /> `BitWiseXor (1,3)`|  
  
## <a name="see-also"></a>Weitere Informationen

- [Kanonische Funktionen](canonical-functions.md)
