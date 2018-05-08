---
title: Die Objektvariable oder die With-Blockvariable wurde nicht festgelegt.
ms.date: 07/20/2015
f1_keywords:
- vbrID91
ms.assetid: 2f03e611-f0ed-465c-99a2-a816e034faa3
ms.openlocfilehash: b2bd1be83f57dbdc7a64b407dc1052074e19c74b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="object-variable-or-with-block-variable-not-set"></a>Die Objektvariable oder die With-Blockvariable wurde nicht festgelegt.
Eine ungültiges Objekt-Variable ist verwiesen wird.   Dieser Fehler kann mehrere Ursachen haben:  
  
-   Eine Variable wurde deklariert, ohne Angabe eines Typs. Wenn eine Variable ohne Angabe eines Typs deklariert ist, wird standardmäßig Typ `Object`.  
  
     Angenommen, eine Variable mit `Dim x` vom Typ `Object;` eine Variable mit `Dim x As String` vom Typ `String`.  
  
    > [!TIP]
    >  Die `Option Strict` Anweisung lässt keine implizite Typisierung, die in einem `Object` Typ. Wenn Sie den Typ weglassen, wird ein Fehler während der Kompilierung auftreten. Finden Sie unter [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md).  
  
-   Sie versuchen, ein Objekt zu verweisen, die festgelegt wurde `Nothing`  
  
     sein.  
  
-   Sie versuchen, ein Element einer Arrayvariablen zuzugreifen, die ordnungsgemäß deklariert wurde nicht.  
  
     Zum Beispiel deklariert ein Array als `products() As String` der Fehler wird ausgelöst, wenn Sie versuchen, ein Element des Arrays verwiesen werden `products(3) = "Widget"`. Das Array verfügt über keine Elemente und wird als ein Objekt behandelt.  
  
-   Sie versuchen, den Zugriff von Code in einem `With...End With` zu blockieren, bevor der Block initialisiert wurde.   Ein `With...End With` Block muss initialisiert werden, durch das Ausführen der `With` Anweisung Einstiegspunkt.  
  
> [!NOTE]
>  In früheren Versionen von Visual Basic oder VBA dieser Fehler auch durch Zuweisen eines Werts zu einer Variablen ohne Verwendung ausgelöst wurde die `Set` Schlüsselwort (`x = "name"` anstelle von `Set x = "name"`). Die `Set` Schlüsselwort ist nicht mehr gültig in Visual Basic.NET.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Legen Sie `Option Strict` auf `On` durch den folgenden Code am Anfang der das Hinzufügen:  
  
```vb  
Option Strict On  
```  

     When you run the project, a compiler error will appear in the **Error List** for any variable that was specified without a type.  
  
2.  Wenn Sie nicht aktivieren möchten `Option Strict`, suchen Sie den Code auf alle Variablen, die ohne einen Typ angegeben wurden (`Dim x` anstelle von `Dim x As String`), und fügen Sie den gewünschten Typ zur Deklaration hinzu.  
  
3.  Stellen Sie sicher, dass Sie einer Objektvariablen, die festgelegt wurde, verweisen werden nicht `Nothing`.  Suchen Sie den Code für das Schlüsselwort `Nothing`, und überarbeiten, damit das Objekt nicht festgelegt ist das den Code `Nothing` erst nach dem darauf verwiesen haben.  
  
4.  Stellen Sie sicher, dass alle Arrayvariablen dimensioniert werden, bevor Sie darauf zugreifen. Sie können entweder eine Dimension zuweisen, bei der Erstellung von Arrays (`Dim x(5) As String` anstelle von `Dim x() As String`), oder verwenden Sie die `ReDim` Schlüsselwort, um die Dimensionen des Arrays festgelegt, bevor darauf zugreifen.  
  
5.  Stellen Sie sicher, dass Ihre `With` Block wird initialisiert, durch das Ausführen der `With` Anweisung Einstiegspunkt.  
  
## <a name="see-also"></a>Siehe auch  
 [Deklaration von Objektvariablen](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)  
 [ReDim-Anweisung](../../../visual-basic/language-reference/statements/redim-statement.md)  
 [With...End With-Anweisung](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
