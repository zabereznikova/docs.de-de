---
title: Auflösung von Funktionsüberladungen (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 9c648054-3808-4a69-9d3e-98e6a4f9c5ca
ms.openlocfilehash: 517bdb682213deff90a37eafcf32946fef63921f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="function-overload-resolution-entity-sql"></a>Auflösung von Funktionsüberladungen (Entity SQL)
In diesem Thema wird beschrieben, wie [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Funktionen aufgelöst werden.  
  
 Solange die Funktionen über eindeutige Signaturen verfügen, können mehrere Funktionen mit demselben Namen definiert werden.  
  
 Wenn das der Fall ist, muss anhand folgender Kriterien ermittelt werden, auf welche Funktion durch einen gegebenen Ausdruck verwiesen wird. Diese Kriterien werden nacheinander überprüft. Das erste Kriterium, das nur für eine Funktion gilt, kennzeichnet die aufgelöste Funktion.  
  
1.  **Parameternummer**. Die Funktion verfügt über dieselbe Anzahl von Parametern wie der angegebene Ausdruck.  
  
2.  **Genaue Übereinstimmung des Typs**. Jeder Argumenttyp der Funktion stimmt genau mit dem Parametertyp überein oder ist das NULL-Literal.  
  
3.  **Übereinstimmung des Untertyps**. Jeder Argumenttyp der Funktion stimmt mit dem Parametertyp genau überein, ist ein Untertyp des Parametertyps, oder das Argument besteht aus dem NULL-Literal. Wenn sich mehrere Funktionen nur in der Anzahl der erforderlichen Untertypkonvertierungen unterscheiden, ist die Funktion mit der geringsten Anzahl an Untertypkonvertierungen die aufgelöste Funktion.  
  
4.  **Suche nach Übereinstimmungen bei Untertyps oder typheraufstufung**. Jeder Argumenttyp der Funktion stimmt mit dem Parametertyp genau überein, ist ein Untertyp des Parametertyps, kann auf den Parametertyp heraufgestuft werden, oder das Argument besteht aus dem NULL-Literal. Auch hier gilt: Wenn sich mehrere Funktionen nur in der Anzahl der Untertypkonvertierungen und Heraufstufungen unterscheiden, ist die Funktion mit der geringsten Anzahl an Untertypkonvertierungen und Heraufstufungen die aufgelöste Funktion.  
  
 Wenn keine Funktion anhand der Kriterien ausgewählt werden kann, ist der Ausdruck zum Aufruf der Funktion mehrdeutig.  
  
 Auch wenn eine Funktion mithilfe dieser Regeln ermittelt werden kann, stimmen die Argumente dennoch möglicherweise nicht mit den Parametern überein. In diesem Fall wird ein Fehler ausgelöst.  
  
 Bei benutzerdefinierten Funktionen hat die Definition für eine Inlineabfragefunktion Vorrang, selbst wenn eine vom Modell definierte Funktion eine Signatur aufweist, die besser für die benutzerdefinierte Funktion geeignet wäre.  
  
## <a name="see-also"></a>Siehe auch  
 [Entity SQL-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [Übersicht über Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)  
 [Funktionen](../../../../../../docs/framework/data/adonet/ef/language-reference/functions-entity-sql.md)
