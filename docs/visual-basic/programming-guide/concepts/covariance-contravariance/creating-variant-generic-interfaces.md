---
title: Erstellen von varianten generischen Schnittstellen
ms.date: 07/20/2015
ms.assetid: d4037dd2-dfe9-4811-9150-93d4e8b20113
ms.openlocfilehash: 884349159d2738d8481b217f9dab383483616f2b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400641"
---
# <a name="creating-variant-generic-interfaces-visual-basic"></a>Creating Variant Generic Interfaces (Visual Basic) (Erstellen varianter generischer Schnittstellen (Visual Basic))

Sie können generische Typparameter in Schnittstellen als Kovariante oder als Kontravariante deklarieren. *Kovarianz* ermöglicht Schnittstellenmethoden, stärker abgeleitete Rückgabetypen zu verwenden, als durch die generischen Typparameter definiert. *Kontravarianz* ermöglicht Schnittstellenmethoden, Argumenttypen zu verwenden, die weniger stark abgeleitet sind, als durch die generischen Parameter angegeben. Eine generische Schnittstelle mit ko- oder kontravarianten generischen Typparametern wird als *variant* bezeichnet.

> [!NOTE]
> In .NET Framework 4 wurde die Varianzunterstützung für mehrere vorhandene generische Schnittstellen eingeführt. Die Liste der variant-Schnittstellen im .NET Framework finden Sie unter [Varianz in generischen Schnittstellen (Visual Basic)](variance-in-generic-interfaces.md).

## <a name="declaring-variant-generic-interfaces"></a>Deklarieren von varianten generischen Schnittstellen

Sie können variante generische Schnittstellen deklarieren, indem Sie die `in`- und `out`-Schlüsselwörter für generische Typparameter verwenden.

> [!IMPORTANT]
> `ByRef`Parameter in Visual Basic können nicht Variant sein. Auch Werttypen unterstützen keine Varianz.

Sie können einen generischen Typparameter mithilfe des Schlüsselworts `out` als Kovariante deklarieren. Der kovariante Typ muss die folgenden Bedingungen erfüllen:

- Der Typ wird nur als Rückgabetyp von Schnittstellenmethoden verwendet, und nicht als Typ von Methodenargumenten. Dies wird im folgenden Beispiel veranschaulicht, in dem der Typ `R` als Kovariante deklariert wird.

    ```vb
    Interface ICovariant(Of Out R)
        Function GetSomething() As R
        ' The following statement generates a compiler error.
        ' Sub SetSomething(ByVal sampleArg As R)
    End Interface
    ```

    Es gibt allerdings eine Ausnahme zu dieser Regel. Wenn Sie einen kontravarianten generischen Delegaten als Methodenparameter angegeben haben, können Sie den Typ als generischen Typparameter für den Delegaten verwenden. Dies wird im folgenden Beispiel von Typ `R` veranschaulicht. Weitere Informationen finden Sie unter [Varianz in Delegaten (Visual Basic)](variance-in-delegates.md) und [Verwenden von Varianz für die generischen Delegaten Func und Action (Visual Basic)](using-variance-for-func-and-action-generic-delegates.md).

    ```vb
    Interface ICovariant(Of Out R)
        Sub DoSomething(ByVal callback As Action(Of R))
    End Interface
    ```

- Der Typ wird nicht als generische Einschränkung für die Schnittstellenmethoden verwendet. Der folgende Code veranschaulicht dies.

    ```vb
    Interface ICovariant(Of Out R)
        ' The following statement generates a compiler error
        ' because you can use only contravariant or invariant types
        ' in generic constraints.
        ' Sub DoSomething(Of T As R)()
    End Interface
    ```

Sie können einen generischen Typparameter mithilfe des Schlüsselworts `in` als Kovariante deklarieren. Der kontravariante Typ kann nur als Typ von Methodenargumenten und nicht von Schnittstellenmethoden verwendet werden. Der kontravariante Typ kann auch für generische Einschränkungen verwendet werden. Der folgende Code zeigt, wie eine kontravariante Schnittstelle deklariert und eine generische Einschränkung für eine ihrer Methoden verwendet wird.

```vb
Interface IContravariant(Of In A)
    Sub SetSomething(ByVal sampleArg As A)
    Sub DoSomething(Of T As A)()
    ' The following statement generates a compiler error.
    ' Function GetSomething() As A
End Interface
```

Bei unterschiedlichen Typparametern ist jedoch auch die Verwendung verschiedener Ko- und Kontravarianzen in der gleichen Schnittstelle möglich, wie im folgenden Codebeispiel veranschaulicht wird.

```vb
Interface IVariant(Of Out R, In A)
    Function GetSomething() As R
    Sub SetSomething(ByVal sampleArg As A)
    Function GetSetSomething(ByVal sampleArg As A) As R
End Interface
```

In Visual Basic können Sie Ereignisse nicht in variant-Schnittstellen deklarieren, ohne den Delegattyp anzugeben. Eine Variant-Schnittstelle kann auch keine in der Struktur eingefügten Klassen, enumerationsstrukturen oder Strukturen enthalten, Sie kann jedoch auch über eine Schnittstelle verfügen. Der folgende Code veranschaulicht dies.

```vb
Interface ICovariant(Of Out R)
    ' The following statement generates a compiler error.
    ' Event SampleEvent()
    ' The following statement specifies the delegate type and
    ' does not generate an error.
    Event AnotherEvent As EventHandler

    ' The following statements generate compiler errors,
    ' because a variant interface cannot have
    ' nested enums, classes, or structures.

    'Enum SampleEnum : test : End Enum
    'Class SampleClass : End Class
    'Structure SampleStructure : Dim value As Integer : End Structure

    ' Variant interfaces can have nested interfaces.
    Interface INested : End Interface
End Interface
```

## <a name="implementing-variant-generic-interfaces"></a>Implementieren von varianten generischen Schnittstellen

Sie können variante generische Schnittstellen in Klassen implementieren, indem Sie die gleiche Syntax verwenden, die für invariante Schnittstellen verwendet wird. Im folgenden Codebeispiel wird veranschaulicht, wie eine kovariante Schnittstelle in einer generischen Klasse implementiert wird.

```vb
Interface ICovariant(Of Out R)
    Function GetSomething() As R
End Interface

Class SampleImplementation(Of R)
    Implements ICovariant(Of R)
    Public Function GetSomething() As R _
    Implements ICovariant(Of R).GetSomething
        ' Some code.
    End Function
End Class
```

Klassen, die variante Schnittstellen implementieren, sind nicht variant. Betrachten Sie hierzu den folgenden Beispielcode:

```vb
 The interface is covariant.
Dim ibutton As ICovariant(Of Button) =
    New SampleImplementation(Of Button)
Dim iobj As ICovariant(Of Object) = ibutton

' The class is invariant.
Dim button As SampleImplementation(Of Button) =
    New SampleImplementation(Of Button)
' The following statement generates a compiler error
' because classes are invariant.
' Dim obj As SampleImplementation(Of Object) = button
```

## <a name="extending-variant-generic-interfaces"></a>Erweitern von varianten generischen Schnittstellen

Wenn Sie eine variante generische Schnittstelle erweitern, müssen Sie mit den `in`- und `out`-Schlüsselwörtern explizit angeben, ob Varianz von der abgeleiteten Schnittstelle unterstützt wird. Der Compiler leitet eine Varianz nicht von der Schnittstelle ab, die erweitert wird. Beachten Sie z.B. die folgenden Schnittstellen.

```vb
Interface ICovariant(Of Out T)
End Interface

Interface IInvariant(Of T)
    Inherits ICovariant(Of T)
End Interface

Interface IExtCovariant(Of Out T)
    Inherits ICovariant(Of T)
End Interface
```

In der- `Invariant(Of T)` Schnittstelle ist der generische Typparameter `T` invariant, während im `IExtCovariant (Of Out T)` Typparameter kovariant ist, obwohl beide Schnittstellen die gleiche Schnittstelle erweitern. Die gleiche Regel gilt für kontravariante generische Typparameter.

Sie können eine Schnittstelle erstellen, die sowohl die Schnittstelle mit dem kovarianten generischen Typparameter `T` als auch die Schnittstelle mit dem kontravarianten Typparameter implementiert, wenn der generische Typparameter `T` in der erweiternden Schnittstelle nicht variant ist. Dies wird im folgenden Codebeispiel veranschaulicht.

```vb
Interface ICovariant(Of Out T)
End Interface

Interface IContravariant(Of In T)
End Interface

Interface IInvariant(Of T)
    Inherits ICovariant(Of T), IContravariant(Of T)
End Interface
```

Wenn der generische Typparameter `T` jedoch in einer Schnittstelle als Kovariante deklariert wird, können Sie ihn nicht in der erweiternden Schnittstelle als Kontravariante deklarieren oder umgekehrt. Dies wird im folgenden Codebeispiel veranschaulicht.

```vb
Interface ICovariant(Of Out T)
End Interface

' The following statements generate a compiler error.
' Interface ICoContraVariant(Of In T)
'     Inherits ICovariant(Of T)
' End Interface
```

### <a name="avoiding-ambiguity"></a>Vermeiden von Mehrdeutigkeiten

Wenn Sie variante generische Schnittstellen implementieren, kann Varianz manchmal zu Mehrdeutigkeit führen. Dies sollte vermieden werden.

Wenn Sie z.B. die gleiche variante generische Schnittstelle explizit mit unterschiedlichen generischen Typparametern in einer Klasse implementieren, kann dies zu Mehrdeutigkeit führen. Der Compiler erzeugt in diesem Fall keinen Fehler, aber es wird nicht angegeben, welche Schnittstellenimplementierung zur Laufzeit ausgewählt wird. Dies kann zu schwer erkennbaren Fehlern im Code führen. Betrachten Sie folgendes Codebeispiel.

> [!NOTE]
> Mit `Option Strict Off` generiert Visual Basic eine Compilerwarnung, wenn eine mehrdeutige Schnittstellen Implementierung vorhanden ist. Bei `Option Strict On` generiert Visual Basic einen Compilerfehler.

```vb
' Simple class hierarchy.
Class Animal
End Class

Class Cat
    Inherits Animal
End Class

Class Dog
    Inherits Animal
End Class

' This class introduces ambiguity
' because IEnumerable(Of Out T) is covariant.
Class Pets
    Implements IEnumerable(Of Cat), IEnumerable(Of Dog)

    Public Function GetEnumerator() As IEnumerator(Of Cat) _
        Implements IEnumerable(Of Cat).GetEnumerator
        Console.WriteLine("Cat")
        ' Some code.
    End Function

    Public Function GetEnumerator1() As IEnumerator(Of Dog) _
        Implements IEnumerable(Of Dog).GetEnumerator
        Console.WriteLine("Dog")
        ' Some code.
    End Function

    Public Function GetEnumerator2() As IEnumerator _
        Implements IEnumerable.GetEnumerator
        ' Some code.
    End Function
End Class

Sub Main()
    Dim pets As IEnumerable(Of Animal) = New Pets()
    pets.GetEnumerator()
End Sub
```

In diesem Beispiel ist nicht angegeben, wie die `pets.GetEnumerator`-Methode zwischen `Cat` und `Dog` auswählt. Dies könnte Probleme im Code verursachen.

## <a name="see-also"></a>Weitere Informationen

- [Variance in Generic Interfaces (Visual Basic) (Varianz in generischen Schnittstellen (Visual Basic))](variance-in-generic-interfaces.md)
- [Using Variance for Func and Action Generic Delegates (Visual Basic) (Verwenden von Varianz für die generischen Delegaten Func und Action (Visual Basic))](using-variance-for-func-and-action-generic-delegates.md)
