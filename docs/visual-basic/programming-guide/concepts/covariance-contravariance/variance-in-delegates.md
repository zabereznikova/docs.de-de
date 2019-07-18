---
title: Varianz in Delegaten (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 38e9353f-74f8-4211-a8f0-7a495414df4a
ms.openlocfilehash: 6d341c7c2b5adeebcafc5b0787b132ab6bd57e41
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61787230"
---
# <a name="variance-in-delegates-visual-basic"></a>Varianz in Delegaten (Visual Basic)

Seit .NET Framework 3.5-Unterstützung von Varianz für Methodensignaturen und Delegattypen in allen Delegaten in C# und Visual Basic. Das bedeutet, dass Sie Delegaten nicht nur Methoden mit übereinstimmenden Signaturen zuweisen können, sondern auch Methoden, die mehrere abgeleitete Typen zurückgeben (Kovarianz) oder die Parameter akzeptieren, die über weniger abgeleitete Typen verfügen, als durch den Delegattyp angegeben wurde (Kontravarianz). Dies umfasst generische und nicht generische Delegaten.

Betrachten Sie beispielsweise folgenden Code, der zwei Klassen und zwei Delegaten aufweist: generisch und nicht generisch.

```vb
Public Class First
End Class

Public Class Second
    Inherits First
End Class

Public Delegate Function SampleDelegate(ByVal a As Second) As First
Public Delegate Function SampleGenericDelegate(Of A, R)(ByVal a As A) As R
```

Beim Erstellen von Delegaten vom Typ `SampleDelegate` oder `SampleDelegate(Of A, R)` können Sie diesen Delegaten eine der folgenden Methoden zuweisen.

```vb
' Matching signature.
Public Shared Function ASecondRFirst(
    ByVal second As Second) As First
    Return New First()
End Function

' The return type is more derived.
Public Shared Function ASecondRSecond(
    ByVal second As Second) As Second
    Return New Second()
End Function

' The argument type is less derived.
Public Shared Function AFirstRFirst(
    ByVal first As First) As First
    Return New First()
End Function

' The return type is more derived
' and the argument type is less derived.
Public Shared Function AFirstRSecond(
    ByVal first As First) As Second
    Return New Second()
End Function
```

Das folgende Codebeispiel veranschaulicht die implizite Konvertierung zwischen der Methodensignatur und dem Delegattyp.

```vb
' Assigning a method with a matching signature
' to a non-generic delegate. No conversion is necessary.
Dim dNonGeneric As SampleDelegate = AddressOf ASecondRFirst
' Assigning a method with a more derived return type
' and less derived argument type to a non-generic delegate.
' The implicit conversion is used.
Dim dNonGenericConversion As SampleDelegate = AddressOf AFirstRSecond

' Assigning a method with a matching signature to a generic delegate.
' No conversion is necessary.
Dim dGeneric As SampleGenericDelegate(Of Second, First) = AddressOf ASecondRFirst
' Assigning a method with a more derived return type
' and less derived argument type to a generic delegate.
' The implicit conversion is used.
Dim dGenericConversion As SampleGenericDelegate(Of Second, First) = AddressOf AFirstRSecond
```

Weitere Beispiele finden Sie unter [Verwenden von Varianz in Delegaten (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md) und [Verwenden von Varianz für Delegaten Func und Action Generic (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).

## <a name="variance-in-generic-type-parameters"></a>Varianz in generischen Typparametern

In .NET Framework 4 und höher, können Sie implizite Konvertierung zwischen Delegaten aktivieren, damit, dass generische Delegaten, die verschiedene Typen von generischen Typparametern angegeben haben, zugewiesen werden können, wenn die Typen voneinander, wie erforderlich geerbt werden Varianz.

Sie müssen einen generischen Parameter in einem Delegaten mithilfe der Schlüsselwörter `in` oder `out` explizit als kovariant oder kontravariant deklarieren, um die implizite Konvertierung zu aktivieren.

Im folgenden Codebeispiel wird veranschaulicht, wie Sie einen Delegaten erstellen können, der über einen kovarianten generischen Typparameter verfügt.

```vb
' Type T is declared covariant by using the out keyword.
Public Delegate Function SampleGenericDelegate(Of Out T)() As T
Sub Test()
    Dim dString As SampleGenericDelegate(Of String) = Function() " "
    ' You can assign delegates to each other,
    ' because the type T is declared covariant.
    Dim dObject As SampleGenericDelegate(Of Object) = dString
End Sub
```

Wenn Sie die Unterstützung von Varianz nur verwenden, um Methodensignaturen mit Delegaten zu vergleichen und nicht die Schlüsselwörter `in` und `out` verwenden, kann es möglicherweise passieren, dass Sie zwar Delegate mit identischen Lambdaausdrücken oder -Methoden instanziieren, aber keinen Delegaten einem anderen zuweisen können.

Das folgende Codebeispiel zeigt `SampleGenericDelegate(Of String)` nicht explizit in konvertiert werden `SampleGenericDelegate(Of Object)`, obwohl `String` erbt `Object`. Sie können dieses Problem beheben, indem Sie den generischen Parameter `T` mit dem Schlüsselwort `out` markieren.

```vb
Public Delegate Function SampleGenericDelegate(Of T)() As T
Sub Test()
    Dim dString As SampleGenericDelegate(Of String) = Function() " "

    ' You can assign the dObject delegate
    ' to the same lambda expression as dString delegate
    ' because of the variance support for
    ' matching method signatures with delegate types.
    Dim dObject As SampleGenericDelegate(Of Object) = Function() " "

    ' The following statement generates a compiler error
    ' because the generic type T is not marked as covariant.
    ' Dim dObject As SampleGenericDelegate(Of Object) = dString

End Sub
```

### <a name="generic-delegates-that-have-variant-type-parameters-in-the-net-framework"></a>Generische Delegaten mit varianten Typparametern in .NET Framework

Mit .NET Framework 4 wurde die Unterstützung von Varianz für generische Typparameter in verschiedenen vorhandenen generischen Delegaten eingeführt:

- `Action`-Delegaten aus dem <xref:System>-Namespace, z.B. <xref:System.Action%601> und <xref:System.Action%602>

- `Func`-Delegaten aus dem <xref:System>-Namespace, z.B. <xref:System.Func%601> und <xref:System.Func%602>

- Der <xref:System.Predicate%601>-Delegat.

- Der <xref:System.Comparison%601>-Delegat.

- Der <xref:System.Converter%602>-Delegat.

Weitere Informationen und Beispiele finden Sie unter [Verwenden von Varianz für Delegaten Func und Action Generic (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).

### <a name="declaring-variant-type-parameters-in-generic-delegates"></a>Angeben varianter Typparameter in generischen Delegaten

Wenn ein generischer Delegat über kovariante oder kontravariante generische Typparameter verfügt, kann er als *varianter generischer Delegat* bezeichnet werden.

Sie können einen generischen Typparameter mithilfe des Schlüsselworts `out` in einem generischen Delegaten als kovariant deklarieren. Der kovariante Typ kann nur als Typ von Methodenrückgaben und nicht von Methodenargumenten verwendet werden. Das folgende Codebeispiel zeigt, wie Sie einen kovarianten generischen Delegaten deklarieren.

```vb
Public Delegate Function DCovariant(Of Out R)() As R
```

Sie können einen generischen Typparameter mithilfe des Schlüsselworts `in` in einem generischen Delegaten als kontravariant deklarieren. Der kontravariante Typ kann nur als Typ von Methodenrückgaben und nicht von Methodenargumenten verwendet werden. Das folgende Codebeispiel zeigt, wie Sie einen kontravarianten generischen Delegaten deklarieren.

```vb
Public Delegate Sub DContravariant(Of In A)(ByVal a As A)
```

> [!IMPORTANT]
> `ByRef` -Parametern in Visual Basic können nicht als Variant markiert werden.

Es ist auch möglich, Varianz und Kovarianz im gleichen Delegaten, aber für verschiedene Typparameter, zu unterstützen. Dies wird im folgenden Beispiel gezeigt.

```vb
Public Delegate Function DVariant(Of In A, Out R)(ByVal a As A) As R
```

### <a name="instantiating-and-invoking-variant-generic-delegates"></a>Instanziieren und Aufrufen von varianten generischen Delegaten

Sie können variante Delegaten genau wie invariante Delegaten instanziieren und aufrufen. Im folgenden Beispiel wird der Delegat durch einen Lambdaausdruck instanziiert.

```vb
Dim dvariant As DVariant(Of String, String) = Function(str) str + " "
dvariant("test")
```

### <a name="combining-variant-generic-delegates"></a>Kombinieren von varianten generischen Delegaten

Variante Delegaten sollten nicht kombiniert werden. Die Methode <xref:System.Delegate.Combine%2A> unterstützt keine Konvertierung von varianten Delegaten und erwartet, dass Delegaten vom exakt gleichen Typ sind. Dies kann zu einer Laufzeitausnahme führen, beim Kombinieren von Delegaten entweder mit der <xref:System.Delegate.Combine%2A> Methode (in C# und Visual Basic) oder mithilfe der `+` Operator (in C#), wie im folgenden Codebeispiel gezeigt.

```vb
Dim actObj As Action(Of Object) = Sub(x) Console.WriteLine("object: {0}", x)
Dim actStr As Action(Of String) = Sub(x) Console.WriteLine("string: {0}", x)

' The following statement throws an exception at run time.
' Dim actCombine = [Delegate].Combine(actStr, actObj)
```

## <a name="variance-in-generic-type-parameters-for-value-and-reference-types"></a>Varianz in generischen Typparametern für Wert- und Referenztypen

Varianz für generische Typparameter wird nur für Referenztypen unterstützt. Z. B. `DVariant(Of Int)`kann nicht implizit konvertiert `DVariant(Of Object)` oder `DVariant(Of Long)`, da ganze Zahl einen Werttyp handelt.

Das folgende Beispiel veranschaulicht, dass Varianz in generischen Typparametern für Werttypen nicht unterstützt wird.

```vb
' The type T is covariant.
Public Delegate Function DVariant(Of Out T)() As T
' The type T is invariant.
Public Delegate Function DInvariant(Of T)() As T
Sub Test()
    Dim i As Integer = 0
    Dim dInt As DInvariant(Of Integer) = Function() i
    Dim dVariantInt As DVariant(Of Integer) = Function() i

    ' All of the following statements generate a compiler error
    ' because type variance in generic parameters is not supported
    ' for value types, even if generic type parameters are declared variant.
    ' Dim dObject As DInvariant(Of Object) = dInt
    ' Dim dLong As DInvariant(Of Long) = dInt
    ' Dim dVariantObject As DInvariant(Of Object) = dInt
    ' Dim dVariantLong As DInvariant(Of Long) = dInt
End Sub
```

## <a name="relaxed-delegate-conversion-in-visual-basic"></a>Gelockerte Delegatenkonvertierung in Visual Basic

Gelockerte delegatenkonvertierung ermöglicht eine höhere Flexibilität in Methodensignaturen und Delegattypen zu vergleichen. Angenommen, können dass Sie die Parameterspezifikationen und Rückgabewerte zu verzichten, wenn Sie eine Methode einem Delegaten zuweisen. Weitere Informationen finden Sie unter [gelockerte Delegatenkonvertierung](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).

## <a name="see-also"></a>Siehe auch

- [Generika](~/docs/standard/generics/index.md)
- [Using Variance for Func and Action Generic Delegates (Visual Basic) (Verwenden von Varianz für die generischen Delegaten Func und Action (Visual Basic))](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)
