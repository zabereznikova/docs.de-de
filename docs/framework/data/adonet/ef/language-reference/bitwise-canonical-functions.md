---
title: Bitweise kanonische Funktionen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 993868ca-16e3-47b6-9915-c29cd63b0a21
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 1d703b2467d508324f3eb39b822c239484ac1c6e
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="bitwise-canonical-functions"></a>Bitweise kanonische Funktionen
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] enthält bitweise kanonische Funktionen.  
  
## <a name="remarks"></a>Hinweise  
 In der folgenden Tabelle sind die bitweisen kanonischen [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Funktionen aufgeführt. Diese Funktionen zurück, `Null` Wenn `Null` -Wert übergeben wird. Der Rückgabetyp der Funktionen ist derselbe wie der Argumenttyp bzw. die Argumenttypen. Die Argumente müssen vom gleichen Typ sein, wenn der Funktion mehr als ein Argument übergeben wird. Um bitweise Operationen für verschiedene Typen auszuführen, müssen Sie explizit auf den gleichen Typ umgewandelt.  
  
|Funktion|Beschreibung|  
|--------------|-----------------|  
|`BitWiseAnd (` `value1` `,`  `value2` `)`|Gibt die bitweise Konjunktion von `value1` und `value2` als Typ von `value1` und `value2` zurück.<br /><br /> **Argumente**<br /><br /> Ein `Byte`, `Int16`, `Int32`, und `Int64`.<br /><br /> **Beispiel**<br /><br /> `-- The following example returns 1.`<br /><br /> `BitWiseAnd(1,3)`|  
|`BitWiseNot (` `value` `)`|Gibt die bitweise Negation von `value` zurück.<br /><br /> **Argumente**<br /><br /> Ein `Byte`, `Int16`, `Int32`, und `Int64`.<br /><br /> **Beispiel**<br /><br /> `-- The following example returns -4.`<br /><br /> `BitWiseNot(3)`|  
|`BitWiseOr (` `value1` `,`  `value2` `)`|Gibt die bitweise Disjunktion von `value1` und `value2` als Typ von `value1` und `value2` zurück.<br /><br /> **Argumente**<br /><br /> Ein `Byte`, `Int16`, `Int32` und `Int64`.<br /><br /> **Beispiel**<br /><br /> `-- The following example returns 3.`<br /><br /> `BitWiseOr(1,3)`|  
|`BitWiseXor (` `value1` `,`  `value2` `)`|Gibt die bitweise ausschließende Disjunktion von `value1` und `value2` als Typ von `value1` und `value2` zurück.<br /><br /> **Argumente**<br /><br /> Ein `Byte`, `Int16`, `Int32` und `Int64`.<br /><br /> **Beispiel**<br /><br /> `-- The following example returns 2.`<br /><br /> `BitWiseXor (1,3)`|  
  
## <a name="see-also"></a>Siehe auch  
 [Canonical Functions (Kanonische Funktionen)](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)
