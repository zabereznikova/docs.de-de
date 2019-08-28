---
title: Die Objektvariable oder die With-Blockvariable wurde nicht festgelegt.
ms.date: 07/20/2015
f1_keywords:
- vbrID91
ms.assetid: 2f03e611-f0ed-465c-99a2-a816e034faa3
ms.openlocfilehash: 07c215d373e4ac1cbadf82a48b8cb3d90efdbdb4
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2019
ms.locfileid: "70040561"
---
# <a name="object-variable-or-with-block-variable-not-set"></a>Die Objektvariable oder die With-Blockvariable wurde nicht festgelegt.
Es wird auf eine ungültige Objekt Variable verwiesen.   Dieser Fehler kann mehrere Ursachen haben:

- Eine Variable wurde ohne Angabe eines Typs deklariert. Wenn eine Variable ohne Angabe eines Typs deklariert wird, wird standardmäßig der `Object`Typ verwendet.

    Beispielsweise ist eine Variable, die `Dim x` mit deklariert wird, `Object;` vom Typ. eine `Dim x As String` Variable, die mit `String`deklariert wurde, ist vom Typ.

    > [!TIP]
    > Die `Option Strict` -Anweisung lässt die implizite Typisierung nicht zu `Object` , die zu einem-Typ führt. Wenn Sie den Typ weglassen, tritt ein Kompilierzeitfehler auf. Siehe [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md).

- Sie versuchen, auf ein Objekt zu verweisen, das auf `Nothing`festgelegt wurde.

- Sie versuchen, auf ein Element einer Array Variablen zuzugreifen, die nicht ordnungsgemäß deklariert wurde.

    Beispielsweise löst ein als `products() As String` deklariertes Array den Fehler aus, wenn Sie versuchen, auf ein Element des Arrays `products(3) = "Widget"`zu verweisen. Das Array hat keine Elemente und wird als Objekt behandelt.

- Sie versuchen, auf Code innerhalb eines `With...End With` -Blocks zuzugreifen, bevor der-Block initialisiert wurde.   Ein `With...End With` -Block muss initialisiert werden, indem `With` der Anweisungs Einstiegspunkt ausgeführt wird.

> [!NOTE]
> In früheren Versionen von Visual Basic oder VBA wurde dieser Fehler auch durch Zuweisen eines Werts zu einer Variablen ausgelöst, ohne das `Set` -Schlüssel`x = "name"` Wort ( `Set x = "name"`anstelle von) zu verwenden. Das `Set` Schlüsselwort ist in Visual Basic .net nicht mehr gültig.

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

1. Legen `Option Strict` Sie `On` auf fest, indem Sie am Anfang der Datei den folgenden Code hinzufügen:

    ```vb
    Option Strict On
    ```

    Wenn Sie das Projekt ausführen, wird ein Compilerfehler im **Fehlerliste** für jede Variable angezeigt, die ohne Typ angegeben wurde.

2. Wenn Sie nicht aktivieren `Option Strict`möchten, Durchsuchen Sie den Code nach allen Variablen, die ohne einen Typ (`Dim x` anstelle von `Dim x As String`) angegeben wurden, und fügen Sie den vorgesehenen Typ der Deklaration hinzu.

3. Stellen Sie sicher, dass Sie nicht auf eine Objekt Variable verweisen, die `Nothing`auf festgelegt wurde.  Durchsuchen Sie den Code nach `Nothing`dem Schlüsselwort, und überarbeiten Sie den Code so, `Nothing` dass das Objekt nicht auf festgelegt ist, bis Sie darauf verwiesen haben.

4. Stellen Sie sicher, dass alle Array Variablen dimensioniert sind, bevor Sie darauf zugreifen. Sie können entweder eine Dimension zuweisen, wenn Sie das Array erstmalig erstellen `Dim x() As String`(`Dim x(5) As String` anstelle von), `ReDim` oder das-Schlüsselwort verwenden, um die Dimensionen des Arrays vor dem ersten Zugriff festzulegen.

5. Stellen Sie sicher `With` , dass der Block initialisiert wird `With` , indem Sie den Anweisungs Einstiegspunkt ausführen.

## <a name="see-also"></a>Siehe auch

- [Deklaration von Objektvariablen](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [ReDim-Anweisung](../../../visual-basic/language-reference/statements/redim-statement.md)
- [With...End With-Anweisung](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
