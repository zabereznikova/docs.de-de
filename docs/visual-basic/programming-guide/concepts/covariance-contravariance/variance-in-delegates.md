---
title: Varianz in Delegaten (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 38e9353f-74f8-4211-a8f0-7a495414df4a
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: cbab7da8c97ca202f8a4d0a1a65b8fa240cca32d
ms.lasthandoff: 03/13/2017

---
# <a name="variance-in-delegates-visual-basic"></a>Varianz in Delegaten (Visual Basic)
Varianz-Unterstützung um Methodensignaturen und Delegattypen in alle Delegaten in c# und Visual Basic wurde in .NET Framework 3.5 eingeführt. Dies bedeutet, die Sie zuweisen können Delegaten nicht nur Methoden, die über übereinstimmende Signaturen verfügen, sondern auch Methoden, stärker abgeleitete Typen (Kovarianz) oder Parameter annehmen, die weniger stark abgeleiteten Typen (Kontravarianz sind) als vom Delegattyp angegeben haben. Dies schließt die generische und nicht generischen Delegaten.  
  
 Betrachten Sie beispielsweise den folgenden Code, der zwei Klassen und zwei Delegaten aufweist: generisch und nicht generisch.  
  
```vb  
Public Class First  
End Class  
  
Public Class Second  
    Inherits First  
End Class  
  
Public Delegate Function SampleDelegate(ByVal a As Second) As First  
Public Delegate Function SampleGenericDelegate(Of A, R)(ByVal a As A) As R  
```  
  
 Beim Erstellen von Delegaten, der die `SampleDelegate` oder `SampleDelegate(Of A, R)` Typen, Sie können eine der folgenden Methoden an diesen Delegaten zuweisen.  
  
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
  
 Das folgende Codebeispiel veranschaulicht die implizite Konvertierung zwischen der Methodensignatur und dem Typ des Delegaten.  
  
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
  
 Weitere Beispiele finden Sie unter [Verwenden von Varianz in Delegaten (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md) und [mithilfe von Varianz für die Aktion generischen Delegaten Func und (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).  
  
## <a name="variance-in-generic-type-parameters"></a>Varianz in generischen Typparametern  
 In .NET Framework 4 und höher können Sie die implizite Konvertierung zwischen Delegaten, aktivieren, sodass generischen Delegaten, die verschiedene Typen von generischen Typparametern angegeben haben, zugewiesen werden können, wenn die Typen von einander gemäß der Varianz geerbt werden.  
  
 Um die implizite Konvertierung zu aktivieren, müssen Sie explizit deklarieren generische Parametern in einen Delegaten als kovariant oder kontravariant mithilfe der `in` oder `out` Schlüsselwort.  
  
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
  
 Bei Verwendung des unterstützen nur Varianz entsprechend Methodensignaturen mit Delegattypen und verwenden Sie nicht die `in` und `out` Schlüsselwörter, können Sie feststellen, dass manchmal können Sie Delegaten mit identischen Lambda-Ausdrücke oder Methoden instanziieren, aber nicht, Sie einem Delegaten in einen anderen weisen kann.  
  
 Im folgenden Codebeispiel `SampleGenericDelegate(Of String)` nicht explizit in konvertiert werden `SampleGenericDelegate(Of Object)`, obwohl `String` erbt `Object`. Sie können dieses Problem beheben, indem der generische Parameter markieren `T` mit dem `out` Schlüsselwort.  
  
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
  
### <a name="generic-delegates-that-have-variant-type-parameters-in-the-net-framework"></a>Generische Delegaten mit Varianten Typparametern in .NET Framework  
 .NET Framework 4 wurde die Varianz-Unterstützung für generische Typparameter in mehrere vorhandene generische Delegaten:  
  
-   `Action`-Delegaten aus dem <xref:System>-Namespace, z. B. <xref:System.Action%601>und <xref:System.Action%602></xref:System.Action%602> </xref:System.Action%601> </xref:System>  
  
-   `Func`-Delegaten aus dem <xref:System>-Namespace, z. B. <xref:System.Func%601>und <xref:System.Func%602></xref:System.Func%602> </xref:System.Func%601> </xref:System>  
  
-   Der <xref:System.Predicate%601>Delegat</xref:System.Predicate%601>  
  
-   Der <xref:System.Comparison%601>Delegat</xref:System.Comparison%601>  
  
-   Der <xref:System.Converter%602>Delegat</xref:System.Converter%602>  
  
 Weitere Informationen und Beispiele finden Sie unter [mithilfe von Varianz für die Aktion generischen Delegaten Func und (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).  
  
### <a name="declaring-variant-type-parameters-in-generic-delegates"></a>Deklarieren von Varianten Typparametern in generischen Delegaten  
 Wenn für ein generischer Delegaten kovariant oder kontravariante generische Typparameter, es kann als bezeichnet ein *generischen Delegaten*.  
  
 Sie können einen generischen Typparameter kovariant in einem generischen Delegaten deklarieren, indem die `out` Schlüsselwort. Der kovariante Typ kann nur als Methodenrückgabetyp und nicht als Typ von Methodenargumenten verwendet werden. Im folgenden Codebeispiel wird veranschaulicht, wie einen kovarianten generischen Delegat deklariert wird.  
  
<CodeContentPlaceHolder>5</CodeContentPlaceHolder>  
 Sie können einen generischen Typparameter in einem generischen Delegaten als Kontravariante deklarieren, indem die `in` Schlüsselwort. Der kontravariante Typ kann nur als Typ von Methodenargumenten und nicht als Methodenrückgabetyp verwendet werden. Im folgenden Codebeispiel wird veranschaulicht, wie einen kontravarianter generischer Delegat deklariert wird.  
  
<CodeContentPlaceHolder>6</CodeContentPlaceHolder>  
> [!IMPORTANT]
>  `ByRef`-Parameter in Visual Basic können nicht als Variant gekennzeichnet werden.  
  
 Es ist auch möglich, Varianz und Kovarianz im gleichen Delegaten, aber für unterschiedliche Typparameter unterstützen. Dies wird im folgenden Beispiel gezeigt.  
  
<CodeContentPlaceHolder>7</CodeContentPlaceHolder>  
### <a name="instantiating-and-invoking-variant-generic-delegates"></a>Instanziieren und Aufrufen von Varianten generischen Delegaten  
 Sie können instanziiert und Variante Delegaten aufrufen, wie Sie instanziieren und aufgerufen. Im folgenden Beispiel wird der Delegat durch einen Lambda-Ausdruck instanziiert.  
  
<CodeContentPlaceHolder>8</CodeContentPlaceHolder>  
### <a name="combining-variant-generic-delegates"></a>Kombinieren von Varianten generischen Delegaten  
 Variante Delegaten sollten nicht kombiniert werden. Die <xref:System.Delegate.Combine%2A>Methode unterstützt keine delegatenkonvertierung und erwartet Delegaten genau den gleichen Typ sein.</xref:System.Delegate.Combine%2A> Dies kann zu einer Laufzeitausnahme führen, beim Kombinieren von Delegaten, die entweder mithilfe der <xref:System.Delegate.Combine%2A>-Methode (in c# und Visual Basic) oder mithilfe der `+` -Operator (in c#), wie im folgenden Codebeispiel gezeigt.</xref:System.Delegate.Combine%2A>  
  
<CodeContentPlaceHolder>9</CodeContentPlaceHolder>  
## <a name="variance-in-generic-type-parameters-for-value-and-reference-types"></a>Varianz in generischen Typparametern für Wert- und Verweistypen  
 Varianz für die generischen Typparameter wird nur für Verweistypen unterstützt. Beispielsweise `DVariant(Of Int)`kann implizit in konvertiert `DVariant(Of Object)` oder `DVariant(Of Long)`, da ganze Zahl ein Werttyp ist.  
  
 Das folgende Beispiel veranschaulicht, dass Varianz in generischen Typ Parameter nicht für Werttypen unterstützt wird.  
  
```vb  
' The type T is covariant.  
Public Delegate Function DVariant(Of Out T)() As T  
' The type T is invariant.  
Public Delegate Function DInvariant(Of T)() As T  
Sub Test()  
    Dim i As Integer = 0  
    Dim dInt As DInvariant(Of Integer) = Function() i  
    Dim dVaraintInt As DVariant(Of Integer) = Function() i  
  
    ' All of the following statements generate a compiler error  
    ' because type variance in generic parameters is not supported  
    ' for value types, even if generic type parameters are declared variant.  
    ' Dim dObject As DInvariant(Of Object) = dInt  
    ' Dim dLong As DInvariant(Of Long) = dInt  
    ' Dim dVaraintObject As DInvariant(Of Object) = dInt  
    ' Dim dVaraintLong As DInvariant(Of Long) = dInt  
End Sub  
```  
  
## <a name="relaxed-delegate-conversion-in-visual-basic"></a>Gelockerte Delegatenkonvertierung in Visual Basic  
 Gelockerte delegatenkonvertierung ermöglicht mehr Flexibilität in Methodensignaturen und Delegattypen zu vergleichen. Beispielsweise können Sie Parameterspezifikationen und Rückgabewerte verzichten, wenn Sie einem Delegaten eine Methode zuweisen. Weitere Informationen finden Sie unter [gelockerte Delegatenkonvertierung](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Generika](https://msdn.microsoft.com/library/ms172192)   
 [Verwenden von Varianz für die Aktion generischen Delegaten Func und (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)
