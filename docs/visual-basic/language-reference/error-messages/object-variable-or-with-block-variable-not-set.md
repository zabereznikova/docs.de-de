---
title: Die Objektvariable oder With-Blockvariable wurde nicht festgelegt | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID91
dev_langs:
- VB
ms.assetid: 2f03e611-f0ed-465c-99a2-a816e034faa3
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 820ef0115a6a27d77f10f4e41d95576bbd79bfa3
ms.lasthandoff: 03/13/2017

---
# <a name="object-variable-or-with-block-variable-not-set"></a>Die Objektvariable oder die With-Blockvariable wurde nicht festgelegt.
Eine ungültige Objekt-Variable wird verwiesen.   Dieser Fehler kann mehrere Ursachen haben:  
  
-   Eine Variable wurde deklariert, ohne Angabe eines Typs. Wenn eine Variable ohne Angabe eines Typs deklariert ist, wird standardmäßig zur Eingabe `Object`.  
  
     Z. B. eine Variable mit `Dim x` vom Typ `Object;` eine Variable mit `Dim x As String` vom Typ `String`.  
  
    > [!TIP]
    >  Die `Option Strict` Anweisung lässt keine implizite Typisierung, bei denen ein `Object` Typ. Wenn Sie den Typ angeben, wird ein Kompilierungsfehler auftreten. Finden Sie unter [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md).  
  
-   Sie versuchen, ein Objekt zu verweisen, die festgelegt wurde`Nothing`  
  
     .  
  
-   Sie versuchen, ein Element einer Arrayvariablen zuzugreifen, die ordnungsgemäß deklariert war nicht.  
  
     Zum Beispiel deklariert ein Array als `products() As String` den Fehler wird ausgelöst, wenn Sie versuchen, ein Element des Arrays verweisen `products(3) = "Widget"`. Das Array enthält keine Elemente und wird als Objekt behandelt.  
  
-   Sie versuchen, den Zugriff von Code innerhalb einer `With...End With` blockiert werden, bevor der Block initialisiert wurde.   Ein `With...End With` Block muss initialisiert werden, durch Ausführen der `With` Anweisung Einstiegspunkt.  
  
> [!NOTE]
>  In früheren Versionen von Visual Basic oder VBA dieser Fehler auch durch Zuweisen eines Werts zu einer Variablen ohne ausgelöst wurde der `Set` Schlüsselwort (`x = "name"` anstelle von `Set x = "name"`). Die `Set` Schlüsselwort ist nicht mehr gültig ist, in Visual Basic.NET.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Legen Sie `Option Strict` zu `On` durch den folgenden Code am Anfang der das Hinzufügen:  
  
```vb  
Option Strict On  
```  

     When you run the project, a compiler error will appear in the **Error List** for any variable that was specified without a type.  
  
2.  Wenn Sie nicht aktivieren möchten `Option Strict`, suchen Sie den Code für alle Variablen, die ohne einen Typ angegeben wurden (`Dim x` anstelle von `Dim x As String`) und fügen Sie den gewünschten Typ der Deklaration.  
  
3.  Sicherstellen, dass Sie einer Objektvariablen, die festgelegt wurde, verweisen werden nicht `Nothing`.  Suchen Sie den Code für das Schlüsselwort `Nothing`, und Überarbeiten Sie Ihren Code so, dass das Objekt ist nicht auf `Nothing` erst nachdem Sie darauf verwiesen haben.  
  
4.  Stellen Sie sicher, dass alle Arrayvariablen dimensioniert werden, bevor Sie darauf zugreifen. Sie können entweder eine Dimension zuweisen, beim Erstellen von Arrays (`Dim x(5) As String` anstelle von `Dim x() As String`), oder verwenden Sie die `ReDim` -Schlüsselwort verwenden, um die Dimensionen des Arrays festgelegt, bevor darauf zugreifen.  
  
5.  Stellen Sie sicher, dass Ihre `With` Block wird initialisiert, indem die Ausführung der `With` Anweisung Einstiegspunkt.  
  
## <a name="see-also"></a>Siehe auch  
 [Deklaration von Objektvariablen](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)   
 [ReDim-Anweisung](../../../visual-basic/language-reference/statements/redim-statement.md)   
 [With...End With-Anweisung](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
