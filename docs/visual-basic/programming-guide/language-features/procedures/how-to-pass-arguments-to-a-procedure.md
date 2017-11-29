---
title: "Gewusst wie: Übergeben von Argumenten an eine Prozedur (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- arguments [Visual Basic], passing to procedures
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- Visual Basic code, procedures
- procedure parameters
- procedures [Visual Basic], calling
- argument passing [Visual Basic], procedures
ms.assetid: 08723588-3890-4ddc-8249-79e049e0f241
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3debb4fa6e7b15f9c321ef207d0cc04181a98da2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-pass-arguments-to-a-procedure-visual-basic"></a>Gewusst wie: Übergeben von Argumenten an eine Prozedur (Visual Basic)
Wenn Sie eine Prozedur aufrufen, folgen Sie den Namen der Prozedur mit einer Argumentliste in Klammern. Geben Sie ein Argument für jeden erforderlichen Parameter der Prozedur definiert, und geben Sie optional Argumente für die `Optional` Parameter. Wenn Sie keine angeben einer `Optional` Parameter im Aufruf muss ein Komma, um seine Position in der Argumentliste zu markieren, wenn Sie nachfolgende Argumente angeben, sind enthalten.  
  
 Wenn Sie beabsichtigen, ein Argument eines Datentyps wie z. B. unterscheidet, von den entsprechenden Parameter übergeben `Byte` auf `String`, Sie können festlegen, dass den Switch Typprüfung ([Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) zu `Off`. Wenn `Option Strict` ist `On`, verwenden Sie entweder erweiternde Konvertierungen oder explizite Konvertierungsschlüsselwörter. Weitere Informationen finden Sie unter [Widening und einschränkende Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) und [Typkonvertierungsfunktionen](../../../../visual-basic/language-reference/functions/type-conversion-functions.md).  
  
 Weitere Informationen finden Sie unter [Prozedurparameter und Argumente](./procedure-parameters-and-arguments.md).  
  
### <a name="to-pass-one-or-more-arguments-to-a-procedure"></a>Um ein oder mehrere Argumente an eine Prozedur übergeben.  
  
1.  Führen Sie in der aufrufenden Anweisung den Prozedurnamen mit Klammern aus.  
  
2.  Fügen Sie innerhalb der Klammern eine Argumentliste. Ein Argument für jeden Parameter erforderlich, dass die Prozedur definiert sind, und trennen Sie die Argumente durch Kommas.  
  
3.  Stellen Sie sicher, dass jedes Argument ist ein gültiger Ausdruck, der eine Daten konvertiert werden kann, den Typ der Prozedur ergibt für den entsprechenden Parameter definiert.  
  
4.  Wenn ein Parameter, als definiert ist [Optional](../../../../visual-basic/language-reference/modifiers/optional.md), Sie können entweder in der Argumentliste eingeschlossen wird, oder lassen sie. Wenn Sie ihn weglassen, verwendet die Prozedur den für diesen Parameter definierten Standardwert.  
  
5.  Wenn Sie ein Argument für weglassen ein `Optional` Parameter ein anderer Parameter nach ihm in der Parameterliste ist, können Sie die Stelle der ausgelassenes Argument markieren, durch ein zusätzliches Komma in der Argumentliste.  
  
     Im folgenden Beispiel wird die [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> Funktion.  
  
     [!code-vb[VbVbcnProcedures#34](./codesnippet/VisualBasic/how-to-pass-arguments-to-a-procedure_1.vb)]  
  
     Das obige Beispiel liefert das erforderliche erste Argument, also die Zeichenfolge, die angezeigt werden soll. Es wird ein Argument für den optionalen zweiten Parameter, der angibt, die Schaltflächen im Meldungsfeld anzuzeigende ausgelassen. Da der Aufruf einen Wert nicht angegeben wird `MsgBox` verwendet den Standardwert `MsgBoxStyle.OKOnly`, woraufhin nur ein **OK** Schaltfläche.  
  
     Das zweite Komma in der Argumentliste markiert die Position des zweiten Arguments nicht angegeben, und die letzte Zeichenfolge übergeben wird, des optionalen dritten Parameters von `MsgBox`, dies ist der Text, der in der Titelleiste angezeigt werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Sub-Prozeduren](./sub-procedures.md)  
 [Function-Prozeduren](./function-procedures.md)  
 [Eigenschaftenprozeduren](./property-procedures.md)  
 [Operatorprozeduren](./operator-procedures.md)  
 [Gewusst wie: Definieren eines Parameters für eine Prozedur](./how-to-define-a-parameter-for-a-procedure.md)  
 [Übergeben von Argumenten als Wert und als Verweis](./passing-arguments-by-value-and-by-reference.md)  
 [Rekursive Prozeduren](./recursive-procedures.md)  
 [Prozedurüberladung](./procedure-overloading.md)  
 [Objekte und Klassen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [Objektorientierte Programmierung](http://msdn.microsoft.com/library/1cf6e655-3f30-45f1-9a5d-4a88ca24a1c2)
