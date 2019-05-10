---
title: Die <variablename>-Variable wird verwendet, bevor ihr ein Wert zugewiesen wird.
ms.date: 07/20/2015
f1_keywords:
- vbc42104
- BC42104
helpviewer_keywords:
- BC42104
ms.assetid: 6909aa0b-b4a1-46f5-a18c-ba3e565c1dd8
ms.openlocfilehash: a2ba752b95933d146da090a58c416015db75e106
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662671"
---
# <a name="variable-variablename-is-used-before-it-has-been-assigned-a-value"></a>Variable "\<Variablenname >' wird verwendet, bevor ihr einen Wert zugewiesen wurde.
Variable "\<Variablenname >' wird verwendet, bevor sie einen Wert zugewiesen wurde. Zur Laufzeit kann eine NULL-Verweisausnahme auftreten.  
  
 Eine Anwendung muss über mindestens einen möglichen Pfad durch den Code, der eine Variable liest, bevor ein Wert zugewiesen wird.  
  
 Wenn einer Variablen nie ein Wert zugewiesen wurde, enthält sie den Standardwert für ihren Datentyp. Bei Verweisdatentypen ist dieser Standardwert [Nothing](../../../visual-basic/language-reference/nothing.md). Das Lesen einer Verweisvariablen, die den Wert `Nothing` aufweist, kann unter bestimmten Umständen zu einer <xref:System.NullReferenceException> führen.  
  
 Standardmäßig ist diese Meldung eine Warnung. Weitere Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC42104  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Überprüfen Sie Ihre Ablaufsteuerungslogik, und stellen Sie sicher, dass die Variable einen gültigen Wert aufweist, bevor die Steuerung an eine Anweisung übergeben, die diese liest.  
  
- Eine Möglichkeit, um sicherzustellen, dass die Variable immer einen gültigen Wert aufweist, ist als Teil der Deklaration initialisiert werden. Finden Sie unter "Initialisierung" in [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md).  
  
## <a name="see-also"></a>Siehe auch

- [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md)
- [Variablendeklaration](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Problembehandlung bei Variablen](../../../visual-basic/programming-guide/language-features/variables/troubleshooting-variables.md)
