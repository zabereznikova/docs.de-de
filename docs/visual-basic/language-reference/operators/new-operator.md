---
title: "New Operator (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.new"
  - "vb.NewConstraint"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "constraints, Visual Basic generic types"
  - "generics [Visual Basic], constraints"
  - "constraints, New keyword"
  - "New constraint"
  - "New keyword"
ms.assetid: d7d566d7-fe0e-4336-91f7-641a542de4d0
caps.latest.revision: 23
caps.handback.revision: 23
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# New Operator (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Führt eine `New`\-Klausel ein, um eine neue Objektinstanz zu erstellen, gibt eine Konstruktoreinschränkung auf einem Typparameter an oder identifiziert eine `Sub`\-Prozedur als Klassenkonstruktor.  
  
## Hinweise  
 In einer Deklarations\- oder Zuweisungsanweisung muss eine `New`\-Klausel eine definierte Klasse angeben, aus der die Instanz erstellt werden kann.  Dies bedeutet, dass die Klasse mindestens einen Konstruktor verfügbar machen muss, auf den der Aufrufcode zugreifen kann.  
  
 Sie können eine `New`\-Klausel in Deklarationsanweisungen oder Zuweisungsanweisungen verwenden.  Bei der Ausführung der Anweisung wird der entsprechende Konstruktor der angegebenen Klasse aufgerufen, und die festgelegten Argumente werden übergeben.  Dies wird im folgenden Beispiel veranschaulicht. Dabei werden Instanzen einer `Customer`\-Klasse mit zwei Konstruktoren erstellt, von denen einer keine Parameter und der andere einen Zeichenfolgenparameter annimmt.  
  
 [!code-vb[VbVbalrKeywords#11](../../../visual-basic/language-reference/codesnippet/VisualBasic/new-operator_1.vb)]  
  
 Da Arrays Klassen sind, kann `New` eine neue Arrayinstanz erstellen, wie in den folgenden Beispielen veranschaulicht.  
  
 [!code-vb[VbVbalrKeywords#12](../../../visual-basic/language-reference/codesnippet/VisualBasic/new-operator_2.vb)]  
  
 Die Common Language Runtime \(CLR\) löst einen <xref:System.OutOfMemoryException>\-Fehler aus, wenn nicht genügend Speicher für die Erstellung der neuen Instanz verfügbar ist.  
  
> [!NOTE]
>  Das `New`\-Schlüsselwort wird auch in Typparameterlisten verwendet, um anzugeben, dass der angegebene Typ einen zugreifbaren parameterlosen Konstruktor verfügbar machen muss.  Weitere Informationen zu Typparametern und Einschränkungen finden Sie unter [Type List](../../../visual-basic/language-reference/statements/type-list.md).  
  
 Um eine Konstruktorprozedur für eine Klasse zu erstellen, legen Sie den Namen einer `Sub`\-Prozedur auf das `New`\-Schlüsselwort fest.  Weitere Informationen finden Sie unter [Object Lifetime: How Objects Are Created and Destroyed](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).  
  
 Das `New`\-Schlüsselwort kann in den folgenden Kontexten verwendet werden:  
  
 [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Of](../../../visual-basic/language-reference/statements/of-clause.md)  
  
 [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## Siehe auch  
 <xref:System.OutOfMemoryException>   
 [Stichwörter](../../../visual-basic/language-reference/keywords/index.md)   
 [Type List](../../../visual-basic/language-reference/statements/type-list.md)   
 [Generische Typen in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Object Lifetime: How Objects Are Created and Destroyed](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)