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
ms.openlocfilehash: 1ba25d830b1e7529bdf09c1195cc1fe7f9b2243b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354099"
---
# <a name="declaration-contexts-and-default-access-levels-visual-basic"></a>Deklarationskontexte und Standardzugriffsebenen (Visual Basic)
In diesem Thema wird beschrieben, welche Visual Basic Typen in welchen anderen Typen deklariert werden können und welche Zugriffsebenen standardmäßig sind, wenn Sie nicht angegeben werden.  
  
## <a name="declaration-context-levels"></a>Deklarations Kontext Stufen  
 Der *Deklarations Kontext* eines Programmier Elements ist der Code Bereich, in dem er deklariert wird. Dies ist häufig ein weiteres Programmier Element, das dann als *enthaltende Element*bezeichnet wird.  
  
 Die Ebenen für Deklarations Kontexte lauten wie folgt:  
  
- *Namespace-Ebene* – in einer Quelldatei oder einem Namespace, jedoch nicht innerhalb einer Klasse, Struktur, eines Moduls oder einer Schnittstelle  
  
- *Modulebene* – innerhalb einer Klasse, Struktur, eines Moduls oder einer Schnittstelle, aber nicht innerhalb einer Prozedur oder eines Blocks  
  
- *Prozedur Ebene* – innerhalb einer Prozedur oder eines Blocks (z. b. `If` oder `For`)  
  
 In der folgenden Tabelle werden die Standard Zugriffsebenen für verschiedene deklarierte Programmier Elemente angezeigt, abhängig von ihren Deklarations Kontexten.  
  
|Deklariertes Element|Namespace Ebene|Modulebene|Prozedur Ebene|  
|----------------------|---------------------|------------------|---------------------|  
|Variable ([Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md))|Nicht zulässig|`Private` (`Public` in `Structure`in `Interface`nicht zulässig)|`Public`|  
|Constant (Konstante[Anweisung](../../../visual-basic/language-reference/statements/const-statement.md))|Nicht zulässig|`Private` (`Public` in `Structure`in `Interface`nicht zulässig)|`Public`|  
|Enumeration (Enumeration-[Anweisung](../../../visual-basic/language-reference/statements/enum-statement.md))|`Friend`|`Public`|Nicht zulässig|  
|Class ([Class-Anweisung](../../../visual-basic/language-reference/statements/class-statement.md))|`Friend`|`Public`|Nicht zulässig|  
|Structure ([Structure-Anweisung](../../../visual-basic/language-reference/statements/structure-statement.md))|`Friend`|`Public`|Nicht zulässig|  
|Module ([Modul-Anweisung](../../../visual-basic/language-reference/statements/module-statement.md))|`Friend`|Nicht zulässig|Nicht zulässig|  
|Interface ([Interface-Anweisung](../../../visual-basic/language-reference/statements/interface-statement.md))|`Friend`|`Public`|Nicht zulässig|  
|Procedure ([Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md), [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md))|Nicht zulässig|`Public`|Nicht zulässig|  
|Externer Verweis ([Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md))|Nicht zulässig|`Public` (nicht zulässig in `Interface`)|Nicht zulässig|  
|Operator ([Operator-Anweisung](../../../visual-basic/language-reference/statements/operator-statement.md))|Nicht zulässig|`Public` (nicht zulässig in `Interface` oder `Module`)|Nicht zulässig|  
|Property ([Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md))|Nicht zulässig|`Public`|Nicht zulässig|  
|Default-Eigenschaft ([Standard](../../../visual-basic/language-reference/modifiers/default.md))|Nicht zulässig|`Public` (nicht zulässig in `Module`)|Nicht zulässig|  
|Event ([Ereignis Anweisung](../../../visual-basic/language-reference/statements/event-statement.md))|Nicht zulässig|`Public`|Nicht zulässig|  
|Delegat ([delegatanweisung](../../../visual-basic/language-reference/statements/delegate-statement.md))|`Friend`|`Public`|Nicht zulässig|  
  
 Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="see-also"></a>Siehe auch

- [Friend](../../../visual-basic/language-reference/modifiers/friend.md)
- [Private](../../../visual-basic/language-reference/modifiers/private.md)
- [Public](../../../visual-basic/language-reference/modifiers/public.md)
