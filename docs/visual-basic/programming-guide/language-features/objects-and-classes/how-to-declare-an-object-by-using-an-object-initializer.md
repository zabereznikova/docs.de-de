---
title: "How to: Declare an Object by Using an Object Initializer (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "declaring objects using object initializer"
  - "object initializers [Visual Basic]"
  - "initializers [Visual Basic]"
  - "Video How tos, Visual Basic"
ms.assetid: 0f53a553-efd6-466d-80bf-6b679e5cd174
caps.latest.revision: 20
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 20
---
# How to: Declare an Object by Using an Object Initializer (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Objektinitialisierer ermöglichen Ihnen, in einer einzelnen Anweisung eine Instanz einer Klasse zu deklarieren und zu instanziieren.  Weiterhin können ein oder mehrere Member der Instanz gleichzeitig initialisiert werden, ohne einen parametrisierten Konstruktor aufzurufen.  
  
 Wenn Sie mit einem Objektinitialisierer eine Instanz eines benannten Typen erstellen, wird der standardmäßige Konstruktor für diese Klasse aufgerufen, gefolgt von der Initialisierung der angegebenen Member in der festgelegten Reihenfolge.  
  
 In der folgenden Prozedur wird dargestellt, wie eine Instanz einer `Student`\-Klasse auf drei verschiedene Weisen erstellt werden kann.  Die Klasse verfügt unter anderem über einen Vornamen, einen Nachnamen und Klassenjahreseigenschaften.  Jede dieser drei Deklarationen erstellt eine neue Instanz von `Student`, in der die `First`\-Eigenschaft auf "Michael", die `Last`\-Eigenschaft auf "Tucker" und die verbleibenden Member auf ihre Standardwerte festgelegt sind.  Das Ergebnis jeder Deklaration in der Prozedur entspricht dem folgenden Beispiel, in dem kein Objektinitialisierer verwendet wurde.  
  
 [!code-vb[VbVbalrObjectInit#20](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/visualbasic/how-to-declare-an-object_1.vb)]  
  
 Weiter Informationen zur Implementierung der `Student`\-Klasse finden Sie unter [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).  Sie können den Code dieses Themas kopieren, um die Klasse einzurichten und eine Liste von `Student`\-Objekten zum Arbeiten zu erstellen.  
  
### So erstellen Sie mithilfe eines Objektinitialisierers ein Objekt einer benannten Klasse  
  
1.  Beginnen Sie die Deklaration so, als ob Sie einen Konstruktor verwenden wollten.  
  
     `Dim student1 As New Student`  
  
2.  Geben Sie das Schlüsselwort `With` gefolgt von einer Initialisierungsliste in geschweiften Klammern ein.  
  
     `Dim student1 As New Student With { <initialization list> }`  
  
3.  Schließen Sie in die Initialisierungsliste sämtliche Eigenschaften ein, die initialisiert werden sollen, und weisen Sie ihnen einen Anfangswert zu.  Der Name der Eigenschaft wird von einem voranstehenden Punkt eingeleitet.  
  
     [!code-vb[VbVbalrObjectInit#21](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/visualbasic/how-to-declare-an-object_2.vb)]  
  
     Sie können einen oder mehrere Member der Klasse initialisieren.  
  
4.  Wahlweise können Sie eine neue Instanz der Klasse deklarieren und ihr dann einen Wert zuweisen.  Deklarieren Sie zuerst eine Instanz von `Student`:  
  
     `Dim student2 As Student`  
  
5.  Beginnen Sie wie gewohnt mit der Erstellung einer Instanz von `Student`.  
  
     `Dim student2 As Student = New Student`  
  
6.  Geben Sie `With` gefolgt von einem Objektinitialisierer ein, um einen oder mehrere Member der neuen Instanz zu initialisieren.  
  
     [!code-vb[VbVbalrObjectInit#22](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/visualbasic/how-to-declare-an-object_3.vb)]  
  
7.  Sie können die Definition im vorherigen Schritt vereinfachen, indem Sie `As Student` auslassen.  In diesem Fall bestimmt der Compiler mithilfe des lokalen Typrückschlusses, dass `student3` eine Instanz von `Student` ist.  
  
     [!code-vb[VbVbalrObjectInit#23](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/visualbasic/how-to-declare-an-object_4.vb)]  
  
     Weitere Informationen finden Sie unter [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).  
  
## Siehe auch  
 [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)   
 [Object Initializers: Named and Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)   
 [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)