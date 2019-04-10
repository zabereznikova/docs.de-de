---
title: Bitweise kanonische Funktionen
ms.date: 03/30/2017
ms.assetid: 993868ca-16e3-47b6-9915-c29cd63b0a21
ms.openlocfilehash: 67d78e8d31f0bc3564a0a111b9bc71cbd0e14f5c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59127795"
---
# <a name="bitwise-canonical-functions"></a>Bitweise kanonische Funktionen
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] enthält bitweise kanonische Funktionen.  
  
## <a name="remarks"></a>Hinweise  
 In der folgenden Tabelle sind die bitweisen kanonischen [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Funktionen aufgeführt. Diese Funktionen zurück, `Null` Wenn `Null` Eingabe bereitgestellt wird. Der Rückgabetyp der Funktionen ist derselbe wie der Argumenttyp bzw. die Argumenttypen. Die Argumente müssen vom gleichen Typ sein, wenn der Funktion mehr als ein Argument übergeben wird. Um bitweise Operationen für verschiedene Arten ausführen zu können, müssen Sie explizit in den gleichen Typ umgewandelt.  
  
|Funktion|Beschreibung|  
|--------------|-----------------|  
|`BitWiseAnd (` `value1` `,`  `value2` `)`|Gibt die bitweise Konjunktion von `value1` und `value2` als Typ von `value1` und `value2` zurück.<br /><br /> **Argumente**<br /><br /> Ein `Byte`, `Int16`, `Int32`, und `Int64`.<br /><br /> **Beispiel**<br /><br /> `-- The following example returns 1.`<br /><br /> `BitWiseAnd(1,3)`|  
|`BitWiseNot (` `value` `)`|Gibt die bitweise Negation von `value` zurück.<br /><br /> **Argumente**<br /><br /> Ein `Byte`, `Int16`, `Int32`, und `Int64`.<br /><br /> **Beispiel**<br /><br /> `-- The following example returns -4.`<br /><br /> `BitWiseNot(3)`|  
|`BitWiseOr (` `value1` `,`  `value2` `)`|Gibt die bitweise Disjunktion von `value1` und `value2` als Typ von `value1` und `value2` zurück.<br /><br /> **Argumente**<br /><br /> Ein `Byte`, `Int16`, `Int32` und `Int64`.<br /><br /> **Beispiel**<br /><br /> `-- The following example returns 3.`<br /><br /> `BitWiseOr(1,3)`|  
|`BitWiseXor (` `value1` `,`  `value2` `)`|Gibt die bitweise ausschließende Disjunktion von `value1` und `value2` als Typ von `value1` und `value2` zurück.<br /><br /> **Argumente**<br /><br /> Ein `Byte`, `Int16`, `Int32` und `Int64`.<br /><br /> **Beispiel**<br /><br /> `-- The following example returns 2.`<br /><br /> `BitWiseXor (1,3)`|  
  
## <a name="see-also"></a>Siehe auch

- [Kanonische Funktionen](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)
