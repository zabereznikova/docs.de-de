---
title: Funktion &#39; &lt;Prozedurname&gt; &#39; ist nicht&#39;t für alle Codepfade einen Wert zurück
ms.date: 07/20/2015
f1_keywords:
- bc42105
- vbc42105
helpviewer_keywords:
- BC42105
ms.assetid: b6929bf4-a365-4a70-8dc9-6b0fc09e1468
ms.openlocfilehash: 4c18c6229eb170e8a688aaa2734ae8fbfa081061
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33589983"
---
# <a name="function-39ltprocedurenamegt39-doesn39t-return-a-value-on-all-code-paths"></a>Funktion &#39; &lt;Prozedurname&gt; &#39; ist nicht&#39;t für alle Codepfade einen Wert zurück
Funktion "\<Prozedurname >' ist nicht für alle Codepfade einen Wert zurück. Fehlt eine "Return"-Anweisung?  
  
 Ein `Function` Prozedur hat mindestens einen möglichen Pfad durch ihren Code, die keinen Wert zurückgibt.  
  
 Sie können einen Rückgabewert aus einer `Function` Prozedur in einem der folgenden Methoden:  
  
-   Schließen Sie den Wert in einer [Return-Anweisung](../../../visual-basic/language-reference/statements/return-statement.md).  
  
-   Weisen Sie den Wert der `Function` Prozedur benennen, und führen Sie dann eine `Exit Function` Anweisung.  
  
-   Weisen Sie den Wert der `Function` Prozedur benennen, und führen Sie dann die `End Function` Anweisung.  
  
 Wenn die Steuerung an übergibt `Exit Function` oder `End Function` und Sie den Namen der Prozedur ausnahmslos zugewiesen haben, die Prozedur den Standardwert der Rückgabedatentyp zurückgegeben. Weitere Informationen finden Sie unter "Verhalten" in [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md).  
  
 Standardmäßig ist diese Meldung eine Warnung. Weitere Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Konfigurieren von Warnungen in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC42105  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Überprüfen Sie Ihre Ablaufsteuerungslogik, und stellen Sie sicher, dass Sie vor jeder Anweisung einen Wert zuweisen, die bewirkt, eine Rückgabe dass.  
  
     Es ist einfacher, um sicherzustellen, dass jede Rückgabe aus der Prozedur einen Wert zurückgibt, wenn Sie immer verwenden die `Return` Anweisung. Wenn Sie die letzte Anweisung vor dazu `End Function` sollte eine `Return` Anweisung.  
  
## <a name="see-also"></a>Siehe auch  
 [Function-Prozeduren](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)  
 [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Seite „Kompilieren“, Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
