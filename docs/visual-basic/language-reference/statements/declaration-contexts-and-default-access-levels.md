---
title: Deklarationskontexte und Standardzugriffsebenen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- module level, defined
- declaration contexts, Visual Basic
- procedure level, defined
- namespace level, defined
- access levels, Visual Basic
- access levels, default levels
ms.assetid: bf63b96e-e825-4745-88c8-5dae222728db
ms.openlocfilehash: 75c5b16164e9ecb6558e445c59e4a312158ff4f8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54580810"
---
# <a name="declaration-contexts-and-default-access-levels-visual-basic"></a>Deklarationskontexte und Standardzugriffsebenen (Visual Basic)
In diesem Thema wird beschrieben, welche Visual Basic-Typen in der anderen Typen deklariert werden können und was ihre Zugriffsebenen Standard Wenn kein Wert angegeben.  
  
## <a name="declaration-context-levels"></a>Deklaration Kontextebenen  
 Die *Deklarationskontext* eines Programmierelements ist der Code in der sie deklariert ist. Dies ist häufig ein anderes Programmierelement, der dann aufgerufen wird, die *, das Element enthält*.  
  
 Der Schwellenwert für Deklarationskontexte lauten wie folgt:  
  
-   *Namespace-Ebene* – innerhalb einer Quelldatei oder der Namespace, jedoch nicht innerhalb einer Klasse, Struktur, Modul oder Schnittstelle  
  
-   *Auf Modulebene* – innerhalb einer Klasse, Struktur, Modul oder Schnittstelle jedoch nicht innerhalb einer Prozedur oder einem Block  
  
-   *Prozedurebene* – innerhalb einer Prozedur oder der Block (z. B. `If` oder `For`)  
  
 Die folgende Tabelle zeigt die Zugriffsebenen "Standard" für verschiedene deklarierte Programmierelemente, je nach ihren Deklarationskontexte.  
  
|Deklariertes Element|Namespace-Ebene|Modulebene|Prozedurebene|  
|----------------------|---------------------|------------------|---------------------|  
|Variablen ([Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md))|Nicht zulässig|`Private` (`Public` in `Structure`, nicht zulässig in `Interface`)|`Public`|  
|Konstanten ([Const-Anweisung](../../../visual-basic/language-reference/statements/const-statement.md))|Nicht zulässig|`Private` (`Public` in `Structure`, nicht zulässig in `Interface`)|`Public`|  
|Enumeration ([Enum-Anweisung](../../../visual-basic/language-reference/statements/enum-statement.md))|`Friend`|`Public`|Nicht zulässig|  
|Klasse ([Class-Anweisung](../../../visual-basic/language-reference/statements/class-statement.md))|`Friend`|`Public`|Nicht zulässig|  
|Struktur ([Struktur Anweisung](../../../visual-basic/language-reference/statements/structure-statement.md))|`Friend`|`Public`|Nicht zulässig|  
|Modul ([Module-Anweisung](../../../visual-basic/language-reference/statements/module-statement.md))|`Friend`|Nicht zulässig|Nicht zulässig|  
|Schnittstelle ([Interface-Anweisung](../../../visual-basic/language-reference/statements/interface-statement.md))|`Friend`|`Public`|Nicht zulässig|  
|Verfahren ([Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md), [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md))|Nicht zulässig|`Public`|Nicht zulässig|  
|Externer Verweis ([Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md))|Nicht zulässig|`Public` (nicht zulässig `Interface`)|Nicht zulässig|  
|Operator ([Operator-Anweisung](../../../visual-basic/language-reference/statements/operator-statement.md))|Nicht zulässig|`Public` (nicht zulässig `Interface` oder `Module`)|Nicht zulässig|  
|Eigenschaft ([Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md))|Nicht zulässig|`Public`|Nicht zulässig|  
|Default-Eigenschaft ([Standard](../../../visual-basic/language-reference/modifiers/default.md))|Nicht zulässig|`Public` (nicht zulässig `Module`)|Nicht zulässig|  
|Event ([Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md))|Nicht zulässig|`Public`|Nicht zulässig|  
|Delegat ([Delegate-Anweisung](../../../visual-basic/language-reference/statements/delegate-statement.md))|`Friend`|`Public`|Nicht zulässig|  
  
 Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="see-also"></a>Siehe auch
- [Friend](../../../visual-basic/language-reference/modifiers/friend.md)
- [Private](../../../visual-basic/language-reference/modifiers/private.md)
- [Public](../../../visual-basic/language-reference/modifiers/public.md)
