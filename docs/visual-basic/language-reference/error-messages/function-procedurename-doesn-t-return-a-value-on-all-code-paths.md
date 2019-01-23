---
title: Funktion &#39; &lt;Prozedurname&gt; &#39; &#39;t für alle Codepfade einen Wert zurück
ms.date: 07/20/2015
f1_keywords:
- bc42105
- vbc42105
helpviewer_keywords:
- BC42105
ms.assetid: b6929bf4-a365-4a70-8dc9-6b0fc09e1468
ms.openlocfilehash: b6cc5143aafb6c2554b183a1fc5fb3b1331ec5d0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54552189"
---
# <a name="function-39ltprocedurenamegt39-doesn39t-return-a-value-on-all-code-paths"></a>Funktion &#39; &lt;Prozedurname&gt; &#39; &#39;t für alle Codepfade einen Wert zurück
Funktion "\<Prozedurname >' nicht für alle Codepfade einen Wert zurück. Fehlt eine Return-Anweisung?  
  
 Ein `Function` Prozedur verfügt über mindestens einen möglichen Pfad durch den Code, die keinen Wert zurückgibt.  
  
 Sie können einen Rückgabewert aus einer `Function` Prozedur in einer der folgenden Methoden:  
  
-   Fügen Sie den Wert in eine [Return-Anweisung](../../../visual-basic/language-reference/statements/return-statement.md).  
  
-   Weisen Sie den Wert der `Function` Prozedur benennen, und führen Sie dann eine `Exit Function` Anweisung.  
  
-   Weisen Sie den Wert der `Function` Prozedur benennen, und führen Sie dann die `End Function` Anweisung.  
  
 Wenn die Steuerung an übergibt `Exit Function` oder `End Function` und Sie für einen beliebigen Wert nicht den Namen der Prozedur zugewiesen haben, gibt die Prozedur den Standardwert des Typs zurückgeben von Daten zurück. Weitere Informationen finden Sie unter "Verhalten" in [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md).  
  
 Standardmäßig ist diese Meldung eine Warnung. Weitere Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC42105  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Überprüfen Sie Ihre Ablaufsteuerungslogik, und stellen Sie sicher, dass Sie vor jeder Anweisung einen Wert zuweisen, die bewirkt, eine Rückgabe dass.  
  
     Es ist einfacher, um sicherzustellen, dass es sich bei jeder Beendigung der Prozedur einen Wert zurückgibt, wenn Sie immer verwenden die `Return` Anweisung. Wenn Sie die letzte Anweisung vor so vorgehen `End Function` muss eine `Return` Anweisung.  
  
## <a name="see-also"></a>Siehe auch
- [Function-Prozeduren](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)
- [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)
- [Seite „Kompilieren“, Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
