---
title: Deklarationskontexte und Standardzugriffsebenen (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- module level, defined
- declaration contexts, Visual Basic
- procedure level, defined
- namespace level, defined
- access levels, Visual Basic
- access levels, default levels
ms.assetid: bf63b96e-e825-4745-88c8-5dae222728db
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b89b74a6c0393f6a52a0b5c1ddf6f66c505564ba
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="declaration-contexts-and-default-access-levels-visual-basic"></a>Deklarationskontexte und Standardzugriffsebenen (Visual Basic)
In diesem Thema wird beschrieben, welche Visual Basic-Typen in den anderen Typen deklariert werden können und was ihre Zugriffsebenen Standard Wenn kein Wert angegeben.  
  
## <a name="declaration-context-levels"></a>Deklaration Kontextebenen  
 Die *Deklarationskontext* ein Programmierelement ist die Region des Codes in der sie deklariert ist. Dies ist häufig ein anderes Programmierelement, der dann aufgerufen wird, die *mit Element*.  
  
 Der Schwellenwert für Deklarationskontexte lauten wie folgt:  
  
-   *Namespace-Ebene* – innerhalb einer Quelldatei oder eines Namespaces, aber nicht innerhalb einer Klasse, Struktur, Modul oder Schnittstelle  
  
-   *Modulebene* – innerhalb einer Klasse, Struktur, Modul oder Schnittstelle, aber nicht innerhalb einer Prozedur oder eines Blocks  
  
-   *Prozedurebene* – innerhalb einer Prozedur oder eines Blocks (z. B. `If` oder `For`)  
  
 Die folgende Tabelle zeigt die Standardzugriffsebenen für verschiedene deklarierte Programmierelemente, je nach ihren Deklarationskontexte.  
  
|Deklariertes Element|Namespace-Ebene|Modulebene|Prozedurebene|  
|----------------------|---------------------|------------------|---------------------|  
|Variablen ([Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md))|Nicht zulässig|`Private`(`Public` in `Structure`, nicht zulässig in `Interface`)|`Public`|  
|Konstanten ([Const-Anweisung](../../../visual-basic/language-reference/statements/const-statement.md))|Nicht zulässig|`Private`(`Public` in `Structure`, nicht zulässig in `Interface`)|`Public`|  
|Enumeration ([Enum-Anweisung](../../../visual-basic/language-reference/statements/enum-statement.md))|`Friend`|`Public`|Nicht zulässig|  
|Klasse ([Class-Anweisung](../../../visual-basic/language-reference/statements/class-statement.md))|`Friend`|`Public`|Nicht zulässig|  
|Struktur ([Struktur Anweisung](../../../visual-basic/language-reference/statements/structure-statement.md))|`Friend`|`Public`|Nicht zulässig|  
|Modul ([Modulanweisung](../../../visual-basic/language-reference/statements/module-statement.md))|`Friend`|Nicht zulässig|Nicht zulässig|  
|Schnittstelle ([Interface-Anweisung](../../../visual-basic/language-reference/statements/interface-statement.md))|`Friend`|`Public`|Nicht zulässig|  
|Prozedur ([Funktion Anweisung](../../../visual-basic/language-reference/statements/function-statement.md), [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md))|Nicht zulässig|`Public`|Nicht zulässig|  
|Externer Verweis ([Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md))|Nicht zulässig|`Public`(nicht zulässig `Interface`)|Nicht zulässig|  
|Operator ([Operator-Anweisung](../../../visual-basic/language-reference/statements/operator-statement.md))|Nicht zulässig|`Public`(nicht zulässig `Interface` oder `Module`)|Nicht zulässig|  
|Eigenschaft ([Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md))|Nicht zulässig|`Public`|Nicht zulässig|  
|Default-Eigenschaft ([Standard](../../../visual-basic/language-reference/modifiers/default.md))|Nicht zulässig|`Public`(nicht zulässig `Module`)|Nicht zulässig|  
|Ereignis ([Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md))|Nicht zulässig|`Public`|Nicht zulässig|  
|Delegaten ([Delegate-Anweisung](../../../visual-basic/language-reference/statements/delegate-statement.md))|`Friend`|`Public`|Nicht zulässig|  
  
 Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
 [Private](../../../visual-basic/language-reference/modifiers/private.md)  
 [Public](../../../visual-basic/language-reference/modifiers/public.md)
