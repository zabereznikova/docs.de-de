---
title: Erstellen varianter generischer Schnittstellen (C#)
ms.date: 07/20/2015
ms.assetid: 30330ec4-9df2-4838-a535-6c406d0ed4df
ms.openlocfilehash: 4ba72f28cd2ddd800f169387cc2c742159d4cb1b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "69595306"
---
# <a name="creating-variant-generic-interfaces-c"></a>Erstellen varianter generischer Schnittstellen (C#)

Sie können generische Typparameter in Schnittstellen als Kovariante oder als Kontravariante deklarieren. *Kovarianz* ermöglicht Schnittstellenmethoden, stärker abgeleitete Rückgabetypen zu verwenden, als durch die generischen Typparameter definiert. *Kontravarianz* ermöglicht Schnittstellenmethoden, Argumenttypen zu verwenden, die weniger stark abgeleitet sind, als durch die generischen Parameter angegeben. Eine generische Schnittstelle mit ko- oder kontravarianten generischen Typparametern wird als *variant* bezeichnet.

> [!NOTE]
> In .NET Framework 4 wurde die Varianzunterstützung für mehrere vorhandene generische Schnittstellen eingeführt. Die Liste der varianten Schnittstellen in .NET Framework finden Sie unter [Varianz in generischen Schnittstellen (C#)](./variance-in-generic-interfaces.md).

## <a name="declaring-variant-generic-interfaces"></a>Deklarieren von varianten generischen Schnittstellen

Sie können variante generische Schnittstellen deklarieren, indem Sie die `in`- und `out`-Schlüsselwörter für generische Typparameter verwenden.

> [!IMPORTANT]
> `ref`-, `in`- und `out`-Parameter in C# können nicht variant sein. Auch Werttypen unterstützen keine Varianz.

Sie können einen generischen Typparameter mithilfe des Schlüsselworts `out` als Kovariante deklarieren. Der kovariante Typ muss die folgenden Bedingungen erfüllen:

- Der Typ wird nur als Rückgabetyp von Schnittstellenmethoden verwendet, und nicht als Typ von Methodenargumenten. Dies wird im folgenden Beispiel veranschaulicht, in dem der Typ `R` als Kovariante deklariert wird.

    ```csharp
    interface ICovariant<out R>
    {
        R GetSomething();
        // The following statement generates a compiler error.
        // void SetSomething(R sampleArg);

    }
    ```

    Es gibt allerdings eine Ausnahme zu dieser Regel. Wenn Sie einen kontravarianten generischen Delegaten als Methodenparameter angegeben haben, können Sie den Typ als generischen Typparameter für den Delegaten verwenden. Dies wird im folgenden Beispiel von Typ `R` veranschaulicht. Weitere Informationen finden Sie unter [Varianz in Delegaten (C#)](./variance-in-delegates.md) und [Verwenden von Varianz für die generischen Delegaten Func und Action (C#)](./using-variance-for-func-and-action-generic-delegates.md).

    ```csharp
    interface ICovariant<out R>
    {
        void DoSomething(Action<R> callback);
    }
    ```

- Der Typ wird nicht als generische Einschränkung für die Schnittstellenmethoden verwendet. Der folgende Code veranschaulicht dies.

    ```csharp
    interface ICovariant<out R>
    {
        // The following statement generates a compiler error
        // because you can use only contravariant or invariant types
        // in generic constraints.
        // void DoSomething<T>() where T : R;
    }
    ```

Sie können einen generischen Typparameter mithilfe des Schlüsselworts `in` als Kovariante deklarieren. Der kontravariante Typ kann nur als Typ von Methodenargumenten und nicht von Schnittstellenmethoden verwendet werden. Der kontravariante Typ kann auch für generische Einschränkungen verwendet werden. Der folgende Code zeigt, wie eine kontravariante Schnittstelle deklariert und eine generische Einschränkung für eine ihrer Methoden verwendet wird.

```csharp
interface IContravariant<in A>
{
    void SetSomething(A sampleArg);
    void DoSomething<T>() where T : A;
    // The following statement generates a compiler error.
    // A GetSomething();
}
```

Bei unterschiedlichen Typparametern ist jedoch auch die Verwendung verschiedener Ko- und Kontravarianzen in der gleichen Schnittstelle möglich, wie im folgenden Codebeispiel veranschaulicht wird.

```csharp
interface IVariant<out R, in A>
{
    R GetSomething();
    void SetSomething(A sampleArg);
    R GetSetSomethings(A sampleArg);
}
```

## <a name="implementing-variant-generic-interfaces"></a>Implementieren von varianten generischen Schnittstellen

Sie können variante generische Schnittstellen in Klassen implementieren, indem Sie die gleiche Syntax verwenden, die für invariante Schnittstellen verwendet wird. Im folgenden Codebeispiel wird veranschaulicht, wie eine kovariante Schnittstelle in einer generischen Klasse implementiert wird.

```csharp
interface ICovariant<out R>
{
    R GetSomething();
}
class SampleImplementation<R> : ICovariant<R>
{
    public R GetSomething()
    {
        // Some code.
        return default(R);
    }
}
```

Klassen, die variante Schnittstellen implementieren, sind nicht variant. Betrachten Sie hierzu den folgenden Beispielcode:

```csharp
// The interface is covariant.
ICovariant<Button> ibutton = new SampleImplementation<Button>();
ICovariant<Object> iobj = ibutton;

// The class is invariant.
SampleImplementation<Button> button = new SampleImplementation<Button>();
// The following statement generates a compiler error
// because classes are invariant.
// SampleImplementation<Object> obj = button;
```

## <a name="extending-variant-generic-interfaces"></a>Erweitern von varianten generischen Schnittstellen

Wenn Sie eine variante generische Schnittstelle erweitern, müssen Sie mit den `in`- und `out`-Schlüsselwörtern explizit angeben, ob Varianz von der abgeleiteten Schnittstelle unterstützt wird. Der Compiler leitet eine Varianz nicht von der Schnittstelle ab, die erweitert wird. Beachten Sie z.B. die folgenden Schnittstellen.

```csharp
interface ICovariant<out T> { }
interface IInvariant<T> : ICovariant<T> { }
interface IExtCovariant<out T> : ICovariant<T> { }
```

In der `IInvariant<T>`-Schnittstelle ist der generische Typparameter `T` nicht variant, während in `IExtCovariant<out T>` der Typparameter kovariant ist, obwohl beide Schnittstellen die gleiche Schnittstelle erweitern. Die gleiche Regel gilt für kontravariante generische Typparameter.

Sie können eine Schnittstelle erstellen, die sowohl die Schnittstelle mit dem kovarianten generischen Typparameter `T` als auch die Schnittstelle mit dem kontravarianten Typparameter implementiert, wenn der generische Typparameter `T` in der erweiternden Schnittstelle nicht variant ist. Dies wird im folgenden Codebeispiel veranschaulicht.

```csharp
interface ICovariant<out T> { }
interface IContravariant<in T> { }
interface IInvariant<T> : ICovariant<T>, IContravariant<T> { }
```

Wenn der generische Typparameter `T` jedoch in einer Schnittstelle als Kovariante deklariert wird, können Sie ihn nicht in der erweiternden Schnittstelle als Kontravariante deklarieren oder umgekehrt. Dies wird im folgenden Codebeispiel veranschaulicht.

```csharp
interface ICovariant<out T> { }
// The following statement generates a compiler error.
// interface ICoContraVariant<in T> : ICovariant<T> { }
```

### <a name="avoiding-ambiguity"></a>Vermeiden von Mehrdeutigkeiten

Wenn Sie variante generische Schnittstellen implementieren, kann Varianz manchmal zu Mehrdeutigkeit führen. Dies sollte vermieden werden.

Wenn Sie z.B. die gleiche variante generische Schnittstelle explizit mit unterschiedlichen generischen Typparametern in einer Klasse implementieren, kann dies zu Mehrdeutigkeit führen. Der Compiler erzeugt in diesem Fall keinen Fehler, aber es wird nicht angegeben, welche Schnittstellenimplementierung zur Laufzeit ausgewählt wird. Dies kann zu schwer erkennbaren Fehlern im Code führen. Betrachten Sie folgendes Codebeispiel.

```csharp
// Simple class hierarchy.
class Animal { }
class Cat : Animal { }
class Dog : Animal { }

// This class introduces ambiguity
// because IEnumerable<out T> is covariant.
class Pets : IEnumerable<Cat>, IEnumerable<Dog>
{
    IEnumerator<Cat> IEnumerable<Cat>.GetEnumerator()
    {
        Console.WriteLine("Cat");
        // Some code.
        return null;
    }

    IEnumerator IEnumerable.GetEnumerator()
    {
        // Some code.
        return null;
    }

    IEnumerator<Dog> IEnumerable<Dog>.GetEnumerator()
    {
        Console.WriteLine("Dog");
        // Some code.
        return null;
    }
}
class Program
{
    public static void Test()
    {
        IEnumerable<Animal> pets = new Pets();
        pets.GetEnumerator();
    }
}
```

In diesem Beispiel ist nicht angegeben, wie die `pets.GetEnumerator`-Methode zwischen `Cat` und `Dog` auswählt. Dies könnte Probleme im Code verursachen.

## <a name="see-also"></a>Weitere Informationen

- [Varianz in generischen Schnittstellen](./variance-in-generic-interfaces.md)
- [Using Variance for Func and Action Generic Delegates C# (Verwenden von Varianz für die generischen Delegaten Func und Action (C#))](./using-variance-for-func-and-action-generic-delegates.md)
