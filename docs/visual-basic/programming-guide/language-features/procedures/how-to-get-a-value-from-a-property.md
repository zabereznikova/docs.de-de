---
title: 'Gewusst wie: Abrufen eines Werts aus einer Eigenschaft (Visual Basic) | Microsoft-Dokumentation'
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
- property values
- Visual Basic code, procedures
- values, properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: 3954423e-6ab7-4a4c-b55c-a8d27be47891
caps.latest.revision: 11
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
ms.openlocfilehash: 7487e4cde724c46a193639f2ad116d25e4ff834c
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-get-a-value-from-a-property-visual-basic"></a>Gewusst wie: Abrufen eines Werts aus einer Eigenschaft (Visual Basic)
Abrufen des Werts einer Eigenschaft von den Eigenschaftennamen in einen Ausdruck einschließen.  
  
 Der Eigenschaft `Get` Prozedur ruft den Wert ab, aber Sie rufen ihn nicht explizit nach Namen. Verwenden Sie die Eigenschaft, wie Sie eine Variable verwenden würden. [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]Ruft die Prozeduren der Eigenschaft.  
  
### <a name="to-retrieve-a-value-from-a-property"></a>Zum Abrufen eines Werts aus einer Eigenschaft  
  
1.  Verwenden Sie den Eigenschaftennamen in einem Ausdruck die gleiche Weise wie ein Variablenname. Sie können eine Eigenschaft überall dort verwenden, eine Variable oder eine Konstante.  
  
     - oder -   
  
     Verwenden Sie den Namen der Eigenschaft, nach dem Gleichheitszeichen (`=`) melden Sie sich eine Zuweisung.  
  
     Das folgende Beispiel liest den Wert der [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] `Now` Eigenschaft implizit aufgerufen seine `Get` Verfahren.  
  
     [!code-vb[VbVbalrDateProperties&4;](./codesnippet/VisualBasic/how-to-get-a-value-from-a-property_1.vb)]  
  
2.  Wenn die Eigenschaft Argumente annimmt, führen Sie die Namen der Eigenschaft in Klammern, um die Argumentliste einschließen. Wenn keine Argumente vorhanden sind, können Sie die Klammern auch weglassen.  
  
3.  Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern durch Kommas getrennt. Achten Sie darauf, dass Sie die Argumente in der gleichen Reihenfolge angeben, dass die Eigenschaft die entsprechenden Parameter definiert.  
  
 Der Wert der Eigenschaft hat im Ausdruck wie eine Variable oder Konstante, oder wird in der Variablen oder Eigenschaft auf der linken Seite der Zuweisung gespeichert.  
  
## <a name="see-also"></a>Siehe auch  
 [Verfahren](./index.md)   
 [Property-Prozeduren](./property-procedures.md)   
 [Prozedurparameter und Argumente](./procedure-parameters-and-arguments.md)   
 [Property-Anweisung](../../../../visual-basic/language-reference/statements/property-statement.md)   
 [Unterschiede zwischen Eigenschaften und Variablen in Visual Basic](./differences-between-properties-and-variables.md)   
 [Gewusst wie: Erstellen einer Eigenschaft](./how-to-create-a-property.md)   
 [Gewusst wie: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen](./how-to-declare-a-property-with-mixed-access-levels.md)   
 [Gewusst wie: Aufrufen einer Eigenschaftenprozedur](./how-to-call-a-property-procedure.md)   
 [Gewusst wie: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic](./how-to-declare-and-call-a-default-property.md)   
 [Gewusst wie: Ablegen eines Werts in einer Eigenschaft](./how-to-put-a-value-in-a-property.md)
