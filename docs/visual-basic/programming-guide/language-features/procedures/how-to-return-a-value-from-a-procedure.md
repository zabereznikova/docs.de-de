---
title: "Gewusst wie: Zurückgeben eines Werts aus einer Prozedur (Visual Basic) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, procedures
- procedures, returning from
- procedures, returning a value
ms.assetid: 4bcc4724-2b4e-4df8-9b4b-16054607f87d
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
ms.openlocfilehash: 98f0fb0740a021a16e87454bfaebbfad7858477c
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-return-a-value-from-a-procedure-visual-basic"></a>Gewusst wie: Zurückgeben eines Werts aus einer Prozedur (Visual Basic)
Ein `Function` Prozedur gibt einen Wert an den aufrufenden Code entweder durch Ausführen einer `Return` Anweisung oder beim Auftreten einer `Exit Function` oder `End Function` Anweisung.  
  
### <a name="to-return-a-value-using-the-return-statement"></a>Zum Zurückgeben eines Werts mithilfe der Return-Anweisung  
  
1.  Einfügen einer `Return` -Anweisung an dem Punkt, an dem die Aufgabe der Prozedur abgeschlossen ist.  
  
2.  Führen Sie die `Return` -Schlüsselwort ein Ausdruck den Wert ergibt an den aufrufenden Code zurückgegeben werden soll.  
  
3.  Stehen Ihnen mehrere `Return` Anweisung in der gleichen Prozedur.  
  
     Die folgenden `Function` die längste Seite, die Hypotenuse eines rechtwinkligen Dreiecks berechnet und an den aufrufenden Code zurück.  
  
     [!code-vb[VbVbcnProcedures&#1;](./codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_1.vb)]  
  
     Das folgende Beispiel zeigt einen normalen Aufruf `hypotenuse`, die den zurückgegebenen Wert speichert.  
  
     [!code-vb[VbVbcnProcedures&6;](./codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_2.vb)]  
  
### <a name="to-return-a-value-using-exit-function-or-end-function"></a>Zum Zurückgeben eines Werts mit Exit Function oder End-Funktion  
  
1.  In mindestens einer der `Function` Verfahren, weisen Sie einen Wert, der Name der Prozedur.  
  
2.  Beim Ausführen einer `Exit Function` oder `End Function` -Anweisung [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] gibt den Wert der Name der Prozedur zuletzt zugewiesen wurde.  
  
3.  Stehen Ihnen mehrere `Exit Function` -Anweisung in die gleiche Prozedur, und Sie können mischen `Return` und `Exit Function` Anweisungen in der gleichen Prozedur.  
  
4.  Stehen Ihnen nur eine `End Function` -Anweisung in einem `Function` Verfahren.  
  
     Weitere Informationen und ein Beispiel finden Sie unter "Rückgabewert" in [Function-Anweisung](../../../../visual-basic/language-reference/statements/function-statement.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Verfahren](./index.md)   
 [Sub-Prozeduren](./sub-procedures.md)   
 [Property-Prozeduren](./property-procedures.md)   
 [Operatorprozeduren](./operator-procedures.md)   
 [Prozedurparameter und Argumente](./procedure-parameters-and-arguments.md)   
 [Function-Anweisung](../../../../visual-basic/language-reference/statements/function-statement.md)   
 [Return-Anweisung](../../../../visual-basic/language-reference/statements/return-statement.md)   
 [Gewusst wie: Erstellen einer Prozedur, die einen Wert zurückgibt](./how-to-create-a-procedure-that-returns-a-value.md)   
 [Gewusst wie: Aufrufen einer Prozedur, die einen Wert zurückgibt](./how-to-call-a-procedure-that-returns-a-value.md)
