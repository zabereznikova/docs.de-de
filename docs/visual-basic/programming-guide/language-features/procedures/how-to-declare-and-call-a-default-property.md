---
title: 'Gewusst wie: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic | Microsoft-Dokumentation'
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
- defaults, properties
- properties [Visual Basic], default
- procedures, defining
- default properties, in Visual Basic
- Visual Basic code, procedures
- Visual Basic code, properties
- default properties
ms.assetid: 68b4026e-09ef-4613-808e-f6287494ff63
caps.latest.revision: 23
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
ms.openlocfilehash: ce98e7fe72a395f6c4cde481feaa60be28c6fcc3
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-declare-and-call-a-default-property-in-visual-basic"></a>Gewusst wie: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic
Ein *Standardeigenschaft* ist eine Klasse oder Struktur-Eigenschaft, die der Code zugreifen kann, ohne dass es. Beim Aufrufen von Code, den Namen einer Klasse oder Struktur, aber keine Eigenschaft, und der Kontext den Zugriff auf eine Eigenschaft ermöglicht [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] löst den Zugriff auf die Klasse oder Struktur Standardeigenschaft, falls vorhanden.  
  
 Eine Klasse oder Struktur kann höchstens eine Standardeigenschaft besitzen. Sie können allerdings haben mehr als eine Version und eine Standardeigenschaft überladen.  
  
 Weitere Informationen finden Sie unter [Standard](../../../../visual-basic/language-reference/modifiers/default.md).  
  
### <a name="to-declare-a-default-property"></a>Deklarieren Sie eine Default-Eigenschaft  
  
1.  Deklarieren Sie die Eigenschaft auf die übliche Weise. Geben Sie die `Shared` oder `Private` Schlüsselwort.  
  
2.  Enthalten die `Default` Schlüsselwort in der Eigenschaftendeklaration.  
  
3.  Geben Sie mindestens einen Parameter für die Eigenschaft. Sie können keine Standardeigenschaft definieren, die nicht mindestens ein Argument annimmt.  
  
     [!code-vb[VbVbcnProcedures&17;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_1.vb)]  
  
### <a name="to-call-a-default-property"></a>Aufrufen eine Standardeigenschaft  
  
1.  Deklarieren Sie eine Variable des enthaltenden Typs Klasse oder Struktur.  
  
     [!code-vb[VbVbcnProcedures Nr.&16;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_2.vb)]  
  
2.  Verwenden Sie den Variablennamen Allein in einem Ausdruck, der Sie normalerweise den Eigenschaftennamen enthalten würde.  
  
     [!code-vb[VbVbcnProcedures&21;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_3.vb)]  
  
3.  Folgen Sie den Variablennamen eine Argumentliste in Klammern. Eine Standardeigenschaft muss mindestens ein Argument annehmen.  
  
     [!code-vb[VbVbcnProcedures&20;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_4.vb)]  
  
4.  Um den Standardwert der Eigenschaft abzurufen, verwenden Sie den Variablennamen mit einer Argumentliste, die in einem Ausdruck oder nach dem Gleichheitszeichen (`=`) melden Sie sich eine Zuweisung.  
  
     [!code-vb[VbVbcnProcedures&#15;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_5.vb)]  
  
5.  Um den Standardwert der Eigenschaft festzulegen, verwenden Sie den Variablennamen mit einer Argumentliste auf der linken Seite einer Zuweisung-Anweisung.  
  
     [!code-vb[VbVbcnProcedures&14;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_6.vb)]  
  
6.  Sie können den Standardnamen für die Eigenschaft zusammen mit dem Variablennamen immer angeben, wie würde für den Zugriff auf eine andere Eigenschaft.  
  
     [!code-vb[VbVbcnProcedures Nr.&19;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_7.vb)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel deklariert eine Standardeigenschaft für eine Klasse.  
  
 [!code-vb[VbVbcnProcedures&#12;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_8.vb)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die Standardeigenschaft Aufrufen `myProperty` Klasse `class1`. Die drei zuweisungsanweisungen speichern Sie die Werte in `myProperty`, und die <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>Aufruf liest die Werte.</xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>  
  
 [!code-vb[VbVbcnProcedures&#13;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_9.vb)]  
  
 Die häufigste Verwendung einer Standard-Eigenschaft wird die <xref:Microsoft.VisualBasic.Collection.Item%2A>-Eigenschaft in verschiedenen Auflistungsklassen.</xref:Microsoft.VisualBasic.Collection.Item%2A>  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Standardeigenschaften können dazu führen, dass eine kleine Reduzierung Code Quellzeichen können, sie jedoch Ihren Code schwieriger zu lesen. Wenn der aufrufende Code nicht mit der Klasse oder Struktur, vertraut ist, wenn einen Verweis auf den Namen der Klasse oder Struktur erstellt kann nicht es sicher sein, ob der Verweis der Klasse oder Struktur selbst oder eine Default-Eigenschaft zugreift. Dies kann zu Compilerfehlern oder feine Laufzeitlogik Fehler führen.  
  
 Sie können das Fehlerrisiko Standard-Eigenschaft etwas reduzieren, indem Sie immer die [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md) Compilertyp Überprüfung festlegen `On`.  
  
 Wenn Sie beabsichtigen, mit eine vordefinierte Klasse oder Struktur im Code müssen Sie bestimmen, ob es sich um eine Standardeigenschaft verfügt, und wenn Ja, wie lautet der Name.  
  
 Wegen dieser Nachteile sollten Sie keine Standardeigenschaften definieren. Für die Lesbarkeit des Codes sollten Sie auch in Betracht ziehen, immer explizit auf alle Eigenschaften verweisen, auch auf Standardeigenschaften.  
  
## <a name="see-also"></a>Siehe auch  
 [Property-Prozeduren](./property-procedures.md)   
 [Prozedurparameter und Argumente](./procedure-parameters-and-arguments.md)   
 [Property-Anweisung](../../../../visual-basic/language-reference/statements/property-statement.md)   
 [Standardwert](../../../../visual-basic/language-reference/modifiers/default.md)   
 [Unterschiede zwischen Eigenschaften und Variablen in Visual Basic](./differences-between-properties-and-variables.md)   
 [Gewusst wie: Erstellen einer Eigenschaft](./how-to-create-a-property.md)   
 [Gewusst wie: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen](./how-to-declare-a-property-with-mixed-access-levels.md)   
 [Gewusst wie: Aufrufen einer Eigenschaftenprozedur](./how-to-call-a-property-procedure.md)   
 [Gewusst wie: Ablegen eines Werts in einer Eigenschaft](./how-to-put-a-value-in-a-property.md)   
 [Gewusst wie: Abrufen eines Werts aus einer Eigenschaft](./how-to-get-a-value-from-a-property.md)
