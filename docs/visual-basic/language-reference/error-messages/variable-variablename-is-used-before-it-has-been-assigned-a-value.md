---
title: Variable &#39; &lt;Variablename&gt; &#39; wird verwendet, bevor ihr einen Wert zugewiesen wurde
ms.date: 07/20/2015
f1_keywords:
- vbc42104
- BC42104
helpviewer_keywords:
- BC42104
ms.assetid: 6909aa0b-b4a1-46f5-a18c-ba3e565c1dd8
ms.openlocfilehash: d314f952bd6e11adaac642ba63ed292f48cda805
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33596918"
---
# <a name="variable-39ltvariablenamegt39-is-used-before-it-has-been-assigned-a-value"></a>Variable &#39; &lt;Variablename&gt; &#39; wird verwendet, bevor ihr einen Wert zugewiesen wurde
Variable "\<Variablename >' wird verwendet, bevor ihr einen Wert zugewiesen wurde. Zur Laufzeit kann eine NULL-Verweisausnahme auftreten.  
  
 Eine Anwendung muss über mindestens einen möglichen Pfad durch ihren Code, der eine Variable liest, bevor ein Wert zugewiesen wird.  
  
 Wenn einer Variablen nie ein Wert zugewiesen wurde, enthält sie den Standardwert für ihren Datentyp. Für eine Verweisdatentypen ist dieser Standardwert [nichts](../../../visual-basic/language-reference/nothing.md). Das Lesen einer Verweisvariablen, die den Wert `Nothing` aufweist, kann unter bestimmten Umständen zu einer <xref:System.NullReferenceException> führen.  
  
 Standardmäßig ist diese Meldung eine Warnung. Weitere Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Konfigurieren von Warnungen in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC42104  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Überprüfen Sie Ihre Ablaufsteuerungslogik, und stellen Sie sicher, dass die Variable einen gültigen Wert aufweist, bevor die Steuerung an eine beliebige Anweisung übergeben, die gelesen.  
  
-   Eine Möglichkeit, um sicherzustellen, dass die Variable hat immer einen gültigen Wert wird als Teil der Deklaration initialisiert werden. Siehe "Initialisierung" in [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md)  
 [Variablendeklaration](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [Problembehandlung bei Variablen](../../../visual-basic/programming-guide/language-features/variables/troubleshooting-variables.md)
