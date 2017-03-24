---
title: "Funktion &quot;&lt;Prozedurname&gt;&quot; nicht für alle Codepfade einen Wert zurück | Microsoft-Dokumentation"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc42105
- vbc42105
dev_langs:
- VB
helpviewer_keywords:
- BC42105
ms.assetid: b6929bf4-a365-4a70-8dc9-6b0fc09e1468
caps.latest.revision: 12
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 288fdf7c4845b20283681d9eb3504ac314f1ddd2
ms.lasthandoff: 03/13/2017

---
# <a name="function-39ltprocedurenamegt39-doesn39t-return-a-value-on-all-code-paths"></a>Funktion "&lt;Prozedurname&gt;' nicht für alle Codepfade einen Wert zurück
Funktion "\<Prozedurname >' nicht für alle Codepfade einen Wert zurück. Fehlt eine Return-Anweisung?  
  
 Ein `Function` Prozedur verfügt über mindestens einen möglichen Codepfad auf, die keinen Wert zurückgibt.  
  
 Kann man einen Wert aus einer `Function` Prozedur in einer der folgenden Methoden:  
  
-   Fügen Sie den Wert in einem [Return-Anweisung](../../../visual-basic/language-reference/statements/return-statement.md).  
  
-   Weisen Sie den Wert der `Function` Prozedur benennen, und führen Sie dann eine `Exit Function` Anweisung.  
  
-   Weisen Sie den Wert der `Function` Prozedur benennen, und führen Sie dann die `End Function` Anweisung.  
  
 Wenn die Steuerung an `Exit Function` oder `End Function` und Sie den Namen der Prozedur einen Wert zugewiesen haben, wird die Prozedur gibt den Standardwert des Rückgabedatentyps zurück. Weitere Informationen finden Sie unter "Verhalten" in [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md).  
  
 Standardmäßig ist diese Meldung eine Warnung. Weitere Informationen zu Ausblenden von Warnungen oder Warnungen als Fehler behandeln, finden Sie unter [Konfigurieren von Warnungen in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC42105  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Überprüfen Sie die Ablaufsteuerungslogik, und stellen Sie sicher, dass Sie vor jeder Anweisung einen Wert zuweisen, der eine Rückgabe verursacht.  
  
     Es ist einfacher sicherstellen, dass bei jeder Beendigung der Prozedur einen Wert zurückgibt, wenn Sie immer verwenden die `Return` Anweisung. Wenn Sie die letzte Anweisung vor dazu `End Function` sollte eine `Return` Anweisung.  
  
## <a name="see-also"></a>Siehe auch  
 [Function-Prozeduren](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)   
 [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Seite „Kompilieren“, Projekt-Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
