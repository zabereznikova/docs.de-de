---
title: Die Objektvariable oder die With-Blockvariable wurde nicht festgelegt.
ms.date: 07/20/2015
f1_keywords:
- vbrID91
ms.assetid: 2f03e611-f0ed-465c-99a2-a816e034faa3
ms.openlocfilehash: 1b24bec6dd7c4b5af10349cf523d9a7e93b385fe
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58831656"
---
# <a name="object-variable-or-with-block-variable-not-set"></a>Die Objektvariable oder die With-Blockvariable wurde nicht festgelegt.
Eine ungültiges Objekt-Variable wird verwiesen wird.   Dieser Fehler kann mehrere Ursachen haben:  
  
-   Eine Variable wurde deklariert, ohne Angabe eines Typs. Wenn eine Variable ohne Angabe eines Typs deklariert ist, wird standardmäßig Typ `Object`.  
  
     Z. B. eine Variable mit `Dim x` vom Typ `Object;` eine Variable mit `Dim x As String` vom Typ `String`.  
  
    > [!TIP]
    >  Die `Option Strict` Anweisung lässt keine impliziten Typisierung der Ergebnisse in eine `Object` Typ. Wenn Sie den Typ weglassen, wird ein Fehler während der Kompilierung auftreten. Finden Sie unter [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md).  
  
-   Sie versuchen, ein Objekt zu verweisen, die festgelegt wurde `Nothing`  
  
     sein.  
  
-   Sie versuchen, ein Element eine Array-Variable zuzugreifen, die ordnungsgemäß deklariert war nicht.  
  
     Zum Beispiel ein Array deklariert als `products() As String` den Fehler wird ausgelöst, wenn Sie versuchen, ein Element des Arrays verweisen `products(3) = "Widget"`. Das Array verfügt über keine Elemente und wird als Objekt behandelt.  
  
-   Sie versuchen, den Zugriff von Code in einem `With...End With` zu blockieren, bevor der Block initialisiert wurde.   Ein `With...End With` Block muss initialisiert werden, indem Sie Ausführung der `With` Einstiegspunkt für die Anweisung.  
  
> [!NOTE]
>  In früheren Versionen von Visual Basic oder VBA wurde dieser Fehler auch durch Zuweisen eines Werts einer Variablen ohne Verwendung von ausgelöst der `Set` Schlüsselwort (`x = "name"` anstelle von `Set x = "name"`). Die `Set` Schlüsselwort ist nicht mehr in Visual Basic.NET gültig.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Legen Sie `Option Strict` zu `On` durch den folgenden Code am Anfang der das Hinzufügen:  
  
```vb  
Option Strict On  
```  

     When you run the project, a compiler error will appear in the **Error List** for any variable that was specified without a type.  
  
2.  Wenn Sie nicht aktivieren möchten `Option Strict`, Durchsuchen Ihres gesamten Codes für alle Variablen, die ohne einen Typ angegeben wurden (`Dim x` anstelle von `Dim x As String`), und fügen Sie der Deklaration der gewünschte Typ hinzu.  
  
3.  Stellen Sie sicher, dass Sie einer Objektvariablen, die festgelegt wurde, verweisen sind nicht `Nothing`.  Suchen Sie Ihren Code für das Schlüsselwort `Nothing`, und Ihren Code so überarbeiten, dass das Objekt, dass festgelegt wurde `Nothing` erst nach dem Sie darauf verwiesen haben.  
  
4.  Stellen Sie sicher, dass alle Arrayvariablen, die dimensioniert werden, bevor Sie darauf zugreifen. Sie können entweder eine Dimension zuweisen, wenn Sie das Array erstellen (`Dim x(5) As String` anstelle von `Dim x() As String`), oder verwenden Sie die `ReDim` Schlüsselwort, um die Dimensionen des Arrays festgelegt, bevor Sie zuerst darauf zugreifen.  
  
5.  Stellen Sie sicher, dass Ihre `With` Block wird initialisiert, indem Sie Ausführung der `With` Einstiegspunkt für die Anweisung.  
  
## <a name="see-also"></a>Siehe auch

- [Deklaration von Objektvariablen](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [ReDim-Anweisung](../../../visual-basic/language-reference/statements/redim-statement.md)
- [With...End With-Anweisung](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
