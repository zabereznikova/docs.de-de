---
title: "Gewusst wie: Übergeben von Argumenten an eine Prozedur (Visual Basic) | Microsoft-Dokumentation"
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
- arguments [Visual Basic], passing to procedures
- procedures, arguments
- procedures, parameters
- procedure arguments
- Visual Basic code, procedures
- procedure parameters
- procedures, calling
- argument passing, procedures
ms.assetid: 08723588-3890-4ddc-8249-79e049e0f241
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: ddccd476b2347368d0435f637edf3882db306f45
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-pass-arguments-to-a-procedure-visual-basic"></a>Gewusst wie: Übergeben von Argumenten an eine Prozedur (Visual Basic)
Wenn Sie eine Prozedur aufrufen, führen Sie den Namen der Prozedur mit einer Argumentliste in Klammern. Ein Argument für jeden erforderlichen Parameter definiert die Prozedur bereit, und geben Sie optional Argumente für die `Optional` Parameter. Wenn Sie keinen angeben einer `Optional` Parameter im Aufruf muss ein Komma, um seine Position in der Argumentliste zu markieren, wenn Sie nachfolgende Argumente angeben, sind enthalten.  
  
 Wenn Sie beabsichtigen, die Übergabe eines Arguments einen Datentyp sich von dem des entsprechenden Parameters, wie z. B. `Byte` auf `String`, Sie können festlegen, dass den Switch Typprüfung ([Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) zu `Off`. Wenn `Option Strict` ist `On`, müssen Sie entweder verwenden erweiternde Konvertierungen oder explizite Konvertierungsschlüsselwörter. Weitere Informationen finden Sie unter [Widening und einschränkende Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) und [Typkonvertierungsfunktionen](../../../../visual-basic/language-reference/functions/type-conversion-functions.md).  
  
 Weitere Informationen finden Sie unter [Prozedurparameter und Argumente](./procedure-parameters-and-arguments.md).  
  
### <a name="to-pass-one-or-more-arguments-to-a-procedure"></a>Ein oder mehrere Argumente an eine Prozedur übergeben  
  
1.  Folgen Sie in der aufrufenden Anweisung den Namen der Prozedur mit Klammern.  
  
2.  Fügen Sie innerhalb der Klammern eine Argumentliste. Ein Argument für jeden erforderlichen Parameter die Prozedur definiert sind, und trennen Sie die Argumente durch Kommas.  
  
3.  Stellen Sie sicher, dass jedes Argument ein gültiger Ausdruck, der eine Daten konvertiert werden kann, der den Typ der Prozedur ergibt für den entsprechenden Parameter definiert.  
  
4.  Wenn ein Parameter, als definiert ist [Optional](../../../../visual-basic/language-reference/modifiers/optional.md), können Sie in der Argumentliste einschließen oder weglassen. Wenn Sie ihn weglassen, verwendet die Prozedur den für diesen Parameter definierten Standardwert.  
  
5.  Wenn Sie ein Argument für auslassen einer `Optional` Parameter und einen weiteren Parameter nach dem in der Parameterliste, Sie können die Position des ausgelassenen Arguments durch ein zusätzliches Komma in der Argumentliste markieren.  
  
     Im folgenden Beispiel wird die [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>Funktion.</xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>  
  
     [!code-vb[VbVbcnProcedures&#34;](./codesnippet/VisualBasic/how-to-pass-arguments-to-a-procedure_1.vb)]  
  
     Das obige Beispiel liefert das erforderliche erste Argument ist die Zeichenfolge, die angezeigt werden. Sie lässt es sich um ein Argument für den optionalen zweiten Parameter, durch Angabe die Schaltflächen im Meldungsfeld angezeigt werden. Da der Aufruf einen Wert nicht angegeben wird `MsgBox` verwendet den Standardwert `MsgBoxStyle.OKOnly`, woraufhin nur ein **OK** Schaltfläche.  
  
     Das zweite Komma in der Argumentliste markiert die Position des ausgelassenen zweiten Arguments, und die letzte Zeichenfolge wird an den optionalen dritten Parameter von übergeben `MsgBox`, wird in der Titelleiste angezeigt werden sollen.  
  
## <a name="see-also"></a>Siehe auch  
 [Sub-Prozeduren](./sub-procedures.md)   
 [Function-Prozeduren](./function-procedures.md)   
 [Property-Prozeduren](./property-procedures.md)   
 [Operatorprozeduren](./operator-procedures.md)   
 [Gewusst wie: Definieren eines Parameters für eine Prozedur](./how-to-define-a-parameter-for-a-procedure.md)   
 [Übergeben von Argumenten als Wert und als Verweis](./passing-arguments-by-value-and-by-reference.md)   
 [Rekursive Prozeduren](./recursive-procedures.md)   
 [Prozedurüberladung](./procedure-overloading.md)   
 [Objekte und Klassen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)   
 [Objektorientierte Programmierung](http://msdn.microsoft.com/library/1cf6e655-3f30-45f1-9a5d-4a88ca24a1c2)
