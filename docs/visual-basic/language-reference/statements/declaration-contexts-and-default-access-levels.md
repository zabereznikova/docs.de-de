---
title: Deklarationskontexte und Standardzugriffsebenen
ms.date: 07/20/2015
helpviewer_keywords:
- module level, defined
- declaration contexts, Visual Basic
- procedure level, defined
- namespace level, defined
- access levels, Visual Basic
- access levels, default levels
ms.assetid: bf63b96e-e825-4745-88c8-5dae222728db
ms.openlocfilehash: a659481b34b8b44f1f387b464d5d9656ed98ab3f
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874953"
---
# <a name="declaration-contexts-and-default-access-levels-visual-basic"></a>Deklarationskontexte und Standardzugriffsebenen (Visual Basic)

In diesem Thema wird beschrieben, welche Visual Basic Typen in welchen anderen Typen deklariert werden können und welche Zugriffsebenen standardmäßig sind, wenn Sie nicht angegeben werden.  
  
## <a name="declaration-context-levels"></a>Deklarations Kontext Stufen  

 Der *Deklarations Kontext* eines Programmier Elements ist der Code Bereich, in dem er deklariert wird. Dies ist häufig ein weiteres Programmier Element, das dann als *enthaltende Element*bezeichnet wird.  
  
 Die Ebenen für Deklarations Kontexte lauten wie folgt:  
  
- *Namespace-Ebene* – in einer Quelldatei oder einem Namespace, jedoch nicht innerhalb einer Klasse, Struktur, eines Moduls oder einer Schnittstelle  
  
- *Modulebene* – innerhalb einer Klasse, Struktur, eines Moduls oder einer Schnittstelle, aber nicht innerhalb einer Prozedur oder eines Blocks  
  
- *Prozedur Ebene* – innerhalb einer Prozedur oder eines Blocks (z. b. `If` oder `For` )  
  
 In der folgenden Tabelle werden die Standard Zugriffsebenen für verschiedene deklarierte Programmier Elemente angezeigt, abhängig von ihren Deklarations Kontexten.  
  
|Deklariertes Element|Namespace Ebene|Modulebene|Prozedur Ebene|  
|----------------------|---------------------|------------------|---------------------|  
|Variable ([Dim-Anweisung](dim-statement.md))|Nicht zulässig|`Private` ( `Public` in `Structure` , nicht zulässig in `Interface` )|`Public`|  
|Constant (Konstante[Anweisung](const-statement.md))|Nicht zulässig|`Private` ( `Public` in `Structure` , nicht zulässig in `Interface` )|`Public`|  
|Enumeration (Enumeration-[Anweisung](enum-statement.md))|`Friend`|`Public`|Nicht zulässig|  
|Class ([Class-Anweisung](class-statement.md))|`Friend`|`Public`|Nicht zulässig|  
|Structure ([Structure-Anweisung](structure-statement.md))|`Friend`|`Public`|Nicht zulässig|  
|Module ([Modul-Anweisung](module-statement.md))|`Friend`|Nicht zulässig|Nicht zulässig|  
|Interface ([Interface-Anweisung](interface-statement.md))|`Friend`|`Public`|Nicht zulässig|  
|Procedure ([Function-Anweisung](function-statement.md), [Sub-Anweisung](sub-statement.md))|Nicht zulässig|`Public`|Nicht zulässig|  
|Externer Verweis ([Declare-Anweisung](declare-statement.md))|Nicht zulässig|`Public` (in nicht zulässig `Interface` )|Nicht zulässig|  
|Operator ([Operator-Anweisung](operator-statement.md))|Nicht zulässig|`Public` (in oder nicht `Interface` zulässig `Module` )|Nicht zulässig|  
|Property ([Property-Anweisung](property-statement.md))|Nicht zulässig|`Public`|Nicht zulässig|  
|Default-Eigenschaft ([Standard](../modifiers/default.md))|Nicht zulässig|`Public` (in nicht zulässig `Module` )|Nicht zulässig|  
|Event ([Ereignis Anweisung](event-statement.md))|Nicht zulässig|`Public`|Nicht zulässig|  
|Delegat ([delegatanweisung](delegate-statement.md))|`Friend`|`Public`|Nicht zulässig|  
  
 Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Friend](../modifiers/friend.md)
- [Privat](../modifiers/private.md)
- [Öffentlich](../modifiers/public.md)
