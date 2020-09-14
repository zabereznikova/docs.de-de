---
title: Varianz bei Delegaten (C#)
description: Hier erfahren Sie, wie Sie mit der Varianzunterstützung in .NET Methodensignaturen und Delegattypen in allen Delegaten vergleichen können.
ms.date: 07/20/2015
ms.assetid: 19de89d2-8224-4406-8964-2965b732b890
ms.openlocfilehash: 02b59dd97cedc6ab35c3122912ee528f7ca29238
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2020
ms.locfileid: "89466130"
---
# <a name="variance-in-delegates-c"></a>Varianz bei Delegaten (C#)
Mit .NET Framework 3.5 wurde die Unterstützung von Varianz eingeführt, um Methodensignaturen und Delegattypen in allen Delegaten in C# vergleichen zu können. Das bedeutet, dass Sie Delegaten nicht nur Methoden mit übereinstimmenden Signaturen zuweisen können, sondern auch Methoden, die mehrere abgeleitete Typen zurückgeben (Kovarianz) oder die Parameter akzeptieren, die über weniger abgeleitete Typen verfügen, als durch den Delegattyp angegeben wurde (Kontravarianz). Dies umfasst generische und nicht generische Delegaten.  
  
 Betrachten Sie beispielsweise folgenden Code, der zwei Klassen und zwei Delegaten aufweist: generisch und nicht generisch.  
  
```csharp  
public class First { }  
public class Second : First { }  
public delegate First SampleDelegate(Second a);  
public delegate R SampleGenericDelegate<A, R>(A a);  
```  
  
 Beim Erstellen von Delegaten vom Typ `SampleDelegate` oder `SampleGenericDelegate<A, R>` können Sie diesen Delegaten eine der folgenden Methoden zuweisen.  
  
```csharp  
// Matching signature.  
public static First ASecondRFirst(Second second)  
{ return new First(); }  
  
// The return type is more derived.  
public static Second ASecondRSecond(Second second)  
{ return new Second(); }  
  
// The argument type is less derived.  
public static First AFirstRFirst(First first)  
{ return new First(); }  
  
// The return type is more derived
// and the argument type is less derived.  
public static Second AFirstRSecond(First first)  
{ return new Second(); }  
```  
  
 Das folgende Codebeispiel veranschaulicht die implizite Konvertierung zwischen der Methodensignatur und dem Delegattyp.  
  
```csharp  
// Assigning a method with a matching signature
// to a non-generic delegate. No conversion is necessary.  
SampleDelegate dNonGeneric = ASecondRFirst;  
// Assigning a method with a more derived return type
// and less derived argument type to a non-generic delegate.  
// The implicit conversion is used.  
SampleDelegate dNonGenericConversion = AFirstRSecond;  
  
// Assigning a method with a matching signature to a generic delegate.  
// No conversion is necessary.  
SampleGenericDelegate<Second, First> dGeneric = ASecondRFirst;  
// Assigning a method with a more derived return type
// and less derived argument type to a generic delegate.  
// The implicit conversion is used.  
SampleGenericDelegate<Second, First> dGenericConversion = AFirstRSecond;  
```  
  
 Weitere Beispiele finden Sie unter [Using Variance in Delegates (C#) (Verwenden von Varianz bei Delegaten (C#))](./using-variance-in-delegates.md) und [Using Variance for Func and Action Generic Delegates (C#) (Verwenden von Varianz für die generischen Delegaten Func und Action (C#))](./using-variance-for-func-and-action-generic-delegates.md).  
  
## <a name="variance-in-generic-type-parameters"></a>Varianz in generischen Typparametern  
 In .NET Framework 4 oder höher können Sie die implizierte Konvertierung zwischen Delegaten aktivieren. Das bedeutet, dass generische Delegaten, die über verschiedene von generischen Typparametern angegebene Typen verfügen, sich gegenseitig zugewiesen werden können, wenn die Typen voneinander geerbt werden. Dies ist für die Varianz erforderlich.  
  
 Sie müssen einen generischen Parameter in einem Delegaten mithilfe der Schlüsselwörter `in` oder `out` explizit als kovariant oder kontravariant deklarieren, um die implizite Konvertierung zu aktivieren.  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie Sie einen Delegaten erstellen können, der über einen kovarianten generischen Typparameter verfügt.  
  
```csharp  
// Type T is declared covariant by using the out keyword.  
public delegate T SampleGenericDelegate <out T>();  
  
public static void Test()  
{  
    SampleGenericDelegate <String> dString = () => " ";  
  
    // You can assign delegates to each other,  
    // because the type T is declared covariant.  
    SampleGenericDelegate <Object> dObject = dString;
}  
```  
  
 Wenn Sie die Unterstützung von Varianz nur verwenden, um Methodensignaturen mit Delegaten zu vergleichen und nicht die Schlüsselwörter `in` und `out` verwenden, kann es möglicherweise passieren, dass Sie zwar Delegate mit identischen Lambdaausdrücken oder -Methoden instanziieren, aber keinen Delegaten einem anderen zuweisen können.  
  
 Im folgenden Codebeispiel kann `SampleGenericDelegate<String>` nicht expliziert in `SampleGenericDelegate<Object>` konvertiert werden, obwohl `String``Object` erbt. Sie können dieses Problem beheben, indem Sie den generischen Parameter `T` mit dem Schlüsselwort `out` markieren.  
  
```csharp  
public delegate T SampleGenericDelegate<T>();  
  
public static void Test()  
{  
    SampleGenericDelegate<String> dString = () => " ";  
  
    // You can assign the dObject delegate  
    // to the same lambda expression as dString delegate  
    // because of the variance support for
    // matching method signatures with delegate types.  
    SampleGenericDelegate<Object> dObject = () => " ";  
  
    // The following statement generates a compiler error  
    // because the generic type T is not marked as covariant.  
    // SampleGenericDelegate <Object> dObject = dString;  
  
}  
```  
  
### <a name="generic-delegates-that-have-variant-type-parameters-in-net"></a>Generische Delegaten mit varianten Typparametern in .NET

Mit .NET Framework 4 wurde die Unterstützung von Varianz für generische Typparameter in verschiedenen vorhandenen generischen Delegaten eingeführt:  
  
- `Action`-Delegaten aus dem <xref:System>-Namespace, z.B. <xref:System.Action%601> und <xref:System.Action%602>  
  
- `Func`-Delegaten aus dem <xref:System>-Namespace, z.B. <xref:System.Func%601> und <xref:System.Func%602>  
  
- Der <xref:System.Predicate%601>-Delegat.  
  
- Der <xref:System.Comparison%601>-Delegat.  
  
- Der <xref:System.Converter%602>-Delegat.  
  
 Weitere Informationen und Beispiele finden Sie unter [Using Variance for Func and Action Generic Delegates (C#) (Verwenden von Varianz für die generischen Delegaten Func und Action (C#))](./using-variance-for-func-and-action-generic-delegates.md).  
  
### <a name="declaring-variant-type-parameters-in-generic-delegates"></a>Angeben varianter Typparameter in generischen Delegaten  
 Wenn ein generischer Delegat über kovariante oder kontravariante generische Typparameter verfügt, kann er als *varianter generischer Delegat* bezeichnet werden.  
  
 Sie können einen generischen Typparameter mithilfe des Schlüsselworts `out` in einem generischen Delegaten als kovariant deklarieren. Der kovariante Typ kann nur als Typ von Methodenrückgaben und nicht von Methodenargumenten verwendet werden. Das folgende Codebeispiel zeigt, wie Sie einen kovarianten generischen Delegaten deklarieren.  
  
```csharp  
public delegate R DCovariant<out R>();  
```  
  
 Sie können einen generischen Typparameter mithilfe des Schlüsselworts `in` in einem generischen Delegaten als kontravariant deklarieren. Der kontravariante Typ kann nur als Typ von Methodenrückgaben und nicht von Methodenargumenten verwendet werden. Das folgende Codebeispiel zeigt, wie Sie einen kontravarianten generischen Delegaten deklarieren.  
  
```csharp  
public delegate void DContravariant<in A>(A a);  
```  
  
> [!IMPORTANT]
> Die Parameter `ref`, `in` und `out` in C# können nicht als variant markiert werden.  
  
 Es ist auch möglich, Varianz und Kovarianz im gleichen Delegaten, aber für verschiedene Typparameter, zu unterstützen. Dies wird im folgenden Beispiel gezeigt.  
  
```csharp  
public delegate R DVariant<in A, out R>(A a);  
```  
  
### <a name="instantiating-and-invoking-variant-generic-delegates"></a>Instanziieren und Aufrufen von varianten generischen Delegaten  
 Sie können variante Delegaten genau wie invariante Delegaten instanziieren und aufrufen. Im folgenden Beispiel wird der Delegat durch einen Lambdaausdruck instanziiert.  
  
```csharp  
DVariant<String, String> dvariant = (String str) => str + " ";  
dvariant("test");  
```  
  
### <a name="combining-variant-generic-delegates"></a>Kombinieren von varianten generischen Delegaten  

Kombinieren Sie keine varianten Delegaten. Die Methode <xref:System.Delegate.Combine%2A> unterstützt keine Konvertierung von varianten Delegaten und erwartet, dass Delegaten vom exakt gleichen Typ sind. Es kann zu einer Laufzeitausnahme führen, wenn Sie Delegaten entweder mit der Methode <xref:System.Delegate.Combine%2A> oder dem Operator `+` kombinieren, wie im folgenden Codebeispiel gezeigt wird.  
  
```csharp  
Action<object> actObj = x => Console.WriteLine("object: {0}", x);  
Action<string> actStr = x => Console.WriteLine("string: {0}", x);  
// All of the following statements throw exceptions at run time.  
// Action<string> actCombine = actStr + actObj;  
// actStr += actObj;  
// Delegate.Combine(actStr, actObj);  
```  
  
## <a name="variance-in-generic-type-parameters-for-value-and-reference-types"></a>Varianz in generischen Typparametern für Wert- und Referenztypen  
 Varianz für generische Typparameter wird nur für Referenztypen unterstützt. `DVariant<int>` kann z.B. nicht implizit in `DVariant<Object>` oder `DVariant<long>` konvertiert werden, da es sich bei „Integer“ um einen Werttyp handelt.  
  
 Das folgende Beispiel veranschaulicht, dass Varianz in generischen Typparametern für Werttypen nicht unterstützt wird.  
  
```csharp  
// The type T is covariant.  
public delegate T DVariant<out T>();  
  
// The type T is invariant.  
public delegate T DInvariant<T>();  
  
public static void Test()  
{  
    int i = 0;  
    DInvariant<int> dInt = () => i;  
    DVariant<int> dVariantInt = () => i;  
  
    // All of the following statements generate a compiler error  
    // because type variance in generic parameters is not supported  
    // for value types, even if generic type parameters are declared variant.  
    // DInvariant<Object> dObject = dInt;  
    // DInvariant<long> dLong = dInt;  
    // DVariant<Object> dVariantObject = dVariantInt;  
    // DVariant<long> dVariantLong = dVariantInt;
}  
```  
  
## <a name="see-also"></a>Siehe auch

- [Generics](../../../../standard/generics/index.md)
- [Verwenden von Varianz für die generischen Delegaten Func und Action (C#)](./using-variance-for-func-and-action-generic-delegates.md)
- [Kombinieren von Delegaten (Multicastdelegaten)](../../delegates/how-to-combine-delegates-multicast-delegates.md)
