---
title: Die Objektvariable oder die With-Blockvariable wurde nicht festgelegt.
ms.date: 07/20/2015
f1_keywords:
- vbrID91
ms.assetid: 2f03e611-f0ed-465c-99a2-a816e034faa3
ms.openlocfilehash: 5eff7622ce2a35cf2846c5141cede98ea033d708
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159884"
---
# <a name="object-variable-or-with-block-variable-not-set"></a>Die Objektvariable oder die With-Blockvariable wurde nicht festgelegt.

Es wird auf eine ungültige Objekt Variable verwiesen. Dieser Fehler kann mehrere Ursachen haben:

- Eine Variable wurde ohne Angabe eines Typs deklariert. Wenn eine Variable ohne Angabe eines Typs deklariert wird, wird standardmäßig der Typ verwendet `Object` .

    Beispielsweise ist eine Variable, die mit deklariert `Dim x` wird, vom Typ `Object;` . eine Variable, die mit deklariert wurde, ist `Dim x As String` vom Typ `String` .

    > [!TIP]
    > Die- `Option Strict` Anweisung lässt die implizite Typisierung nicht zu, die zu einem- `Object` Typ führt. Wenn Sie den Typ weglassen, tritt ein Kompilierzeitfehler auf. Informationen hierzu finden Sie unter [Option Strict-Anweisung](../statements/option-strict-statement.md).

- Sie versuchen, auf ein Objekt zu verweisen, das auf festgelegt wurde `Nothing` .

- Sie versuchen, auf ein Element einer Array Variablen zuzugreifen, die nicht ordnungsgemäß deklariert wurde.

    Beispielsweise löst ein als deklariertes Array `products() As String` den Fehler aus, wenn Sie versuchen, auf ein Element des Arrays zu verweisen `products(3) = "Widget"` . Das Array hat keine Elemente und wird als Objekt behandelt.

- Sie versuchen, auf Code innerhalb eines- `With...End With` Blocks zuzugreifen, bevor der-Block initialisiert wurde.   Ein- `With...End With` Block muss initialisiert werden, indem der `With` Anweisungs Einstiegspunkt ausgeführt wird.

> [!NOTE]
> In früheren Versionen von Visual Basic oder VBA wurde dieser Fehler auch durch Zuweisen eines Werts zu einer Variablen ausgelöst, ohne das- `Set` Schlüsselwort ( `x = "name"` anstelle von) zu verwenden `Set x = "name"` . Das `Set` Schlüsselwort ist in Visual Basic .net nicht mehr gültig.

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

1. Legen `Option Strict` Sie auf fest, `On` indem Sie am Anfang der Datei den folgenden Code hinzufügen:

    ```vb
    Option Strict On
    ```

    Wenn Sie das Projekt ausführen, wird ein Compilerfehler im **Fehlerliste** für jede Variable angezeigt, die ohne Typ angegeben wurde.

2. Wenn Sie nicht aktivieren möchten `Option Strict` , Durchsuchen Sie den Code nach allen Variablen, die ohne einen Typ ( `Dim x` anstelle von) angegeben wurden, `Dim x As String` und fügen Sie den vorgesehenen Typ der Deklaration hinzu.

3. Stellen Sie sicher, dass Sie nicht auf eine Objekt Variable verweisen, die auf festgelegt wurde `Nothing` .  Durchsuchen Sie den Code nach dem Schlüsselwort `Nothing` , und überarbeiten Sie den Code so, dass das Objekt nicht auf festgelegt ist, `Nothing` bis Sie darauf verwiesen haben.

4. Stellen Sie sicher, dass alle Array Variablen dimensioniert sind, bevor Sie darauf zugreifen. Sie können entweder eine Dimension zuweisen, wenn Sie das Array erstmalig erstellen ( `Dim x(5) As String` anstelle von `Dim x() As String` ), oder das- `ReDim` Schlüsselwort verwenden, um die Dimensionen des Arrays vor dem ersten Zugriff festzulegen.

5. Stellen Sie sicher, dass `With` der Block initialisiert wird, indem Sie den `With` Anweisungs Einstiegspunkt ausführen.

## <a name="see-also"></a>Siehe auch

- [Deklaration von Objektvariablen](../../programming-guide/language-features/variables/object-variable-declaration.md)
- [ReDim-Anweisung](../statements/redim-statement.md)
- [With...End With-Anweisung](../statements/with-end-with-statement.md)
