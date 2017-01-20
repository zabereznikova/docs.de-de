---
title: "Relaxed Delegate Conversion (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "relaxed delegate conversion [Visual Basic]"
  - "delegates [Visual Basic], relaxed conversion"
  - "conversions, relaxed delegate"
ms.assetid: 64f371d0-5416-4f65-b23b-adcbf556e81c
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Relaxed Delegate Conversion (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Die gelockerte Delegatenkonvertierung ermöglicht das Zuweisen von Unterroutinen und Funktionen zu Delegaten oder Handlern, auch wenn deren Signaturen nicht identisch sind. Das Binden an Delegaten ist deshalb konsistent mit dem bereits zulässigen Binden für Methodenaufrufe.  
  
## Parameter und Rückgabetyp  
 Anstatt der exakten Übereinstimmung von Signaturen setzt die gelockerte Konvertierung voraus, dass die folgenden Bedingungen erfüllt sind, wenn `Option Strict` auf `On` festgelegt ist:  
  
-   Eine Erweiterungskonvertierung aus dem Datentyp der einzelnen Delegatparameter in den Datentyp des entsprechenden Parameters der zugewiesenen Funktion oder `Sub` muss vorhanden sein.  Im folgenden Beispiel verfügt der Delegat `Del1` über einen Parameter, eine `Integer`.  Der Parameter `m` in den zugewiesenen Lambda\-Ausdrücken muss über einen Datentyp verfügen, für den eine Erweiterungskonvertierung aus `Integer`, z. B. `Long` oder `Double`, unterstützt wird.  
  
     [!code-vb[VbVbalrRelaxedDelegates#1](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/VbVbalrRelaxedDelegates/Module1.vb#1)]  
  
     [!code-vb[VbVbalrRelaxedDelegates#2](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/VbVbalrRelaxedDelegates/Module1.vb#2)]  
  
     Einschränkende Konvertierungen sind nur erlaubt, wenn `Option Strict` auf `Off` festgelegt ist.  
  
     [!code-vb[VbVbalrRelaxedDelegates#8](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/VbVbalrRelaxedDelegates/Module2.vb#8)]  
  
-   Eine Erweiterungskonvertierung in die entgegengesetzte Richtung aus dem Rückgabetyp der zugewiesenen Funktion oder `Sub` in den Rückgabetyp des Delegaten muss vorhanden sein.  In den folgenden Beispielen muss der Text jedes zugewiesenen Lambda\-Ausdrucks als Datentyp ausgewertet werden, der zu `Integer` erweitert wird, da der Rückgabetyp von `del1` `Integer` ist.  
  
     [!code-vb[VbVbalrRelaxedDelegates#3](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/VbVbalrRelaxedDelegates/Module1.vb#3)]  
  
 Wenn `Option Strict` auf `Off` festgelegt ist, wird die Erweiterungseinschränkung in beiden Richtungen entfernt.  
  
 [!code-vb[VbVbalrRelaxedDelegates#4](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/VbVbalrRelaxedDelegates/Module2.vb#4)]  
  
## Auslassen von Parameterspezifikationen  
 Bei Verwendung gelockerter Delegaten können Sie Parameterspezifikationen in der zugewiesenen Methode vollständig auslassen:  
  
 [!code-vb[VbVbalrRelaxedDelegates#5](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/VbVbalrRelaxedDelegates/Module1.vb#5)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#6](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/VbVbalrRelaxedDelegates/Module1.vb#6)]  
  
 Beachten Sie, dass Sie nicht einige Parameter angeben und andere weglassen dürfen.  
  
 [!code-vb[VbVbalrRelaxedDelegates#15](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/VbVbalrRelaxedDelegates/Module1.vb#15)]  
  
 Dies ist in Situationen wie dem Definieren eines Ereignishandlers hilfreich, in denen mehrere komplexe Parameter berücksichtigt werden müssen.  Die Argumente für einige Ereignishandler werden nicht verwendet.  Stattdessen greift der Handler direkt auf den Zustand des Steuerelements zu, für das das Ereignis registriert wurde, und ignoriert die Argumente.  Mithilfe von gelockerten Delegaten können Sie die Argumente in Deklarationen weglassen, in denen keine Mehrdeutigkeiten auftreten.  Im folgenden Beispiel kann die vollständig angegebene Methode `OnClick` als `RelaxedOnClick` umgeschrieben werden.  
  
```vb#  
Sub OnClick(ByVal sender As Object, ByVal e As EventArgs) Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
  
Sub RelaxedOnClick() Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
```  
  
## AddressOf\-Beispiele  
 Lambda\-Ausdrücke werden in den vorherigen Beispielen verwendet, um die Typbeziehungen leicht erkennbar zu machen.  Die gleichen Lockerungen sind jedoch für Delegatzuweisungen zulässig, die `AddressOf`, `Handles` oder `AddHandler` verwenden.  
  
 Im folgenden Beispiel können die Funktionen `f1`, `f2`, `f3` und `f4` alle `Del1` zugewiesen werden.  
  
 [!code-vb[VbVbalrRelaxedDelegates#1](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/VbVbalrRelaxedDelegates/Module1.vb#1)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#7](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/VbVbalrRelaxedDelegates/Module1.vb#7)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#9](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/VbVbalrRelaxedDelegates/Module1.vb#9)]  
  
 Das folgende Beispiel ist nur gültig, wenn `Option Strict` auf `Off` festgelegt ist.  
  
 [!code-vb[VbVbalrRelaxedDelegates#14](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/VbVbalrRelaxedDelegates/Module2.vb#14)]  
  
## Ignorieren von Funktionsrückgabewerten  
 Über die gelockerte Delegatenkonvertierung können Sie einem `Sub`\-Delegaten eine Funktion zuweisen und so den Rückgabewert der Funktion vollständig ignorieren.  Sie können einem Funktionsdelegaten jedoch kein `Sub` zuweisen.  Im folgenden Beispiel wird die Adresse von Funktion `doubler` dem `Sub`\-Delegaten `Del3` zugewiesen.  
  
 [!code-vb[VbVbalrRelaxedDelegates#10](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/VbVbalrRelaxedDelegates/Module1.vb#10)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#11](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/VbVbalrRelaxedDelegates/Module1.vb#11)]  
  
## Siehe auch  
 [Lambda Expressions](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)   
 [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)   
 [Delegates](../../../../visual-basic/programming-guide/language-features/delegates/delegates.md)   
 [How to: Pass Procedures to Another Procedure in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)   
 [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)