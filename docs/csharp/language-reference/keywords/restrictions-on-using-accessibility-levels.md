---
title: Einschränkungen bei der Verwendung von Zugriffsebenen – C#-Referenz
ms.date: 07/20/2015
helpviewer_keywords:
- access modifiers [C#], accessibility level restrictions
ms.assetid: 987e2f22-46bf-4fea-80ee-270b9cd01045
ms.openlocfilehash: 8082dbd7398b6634b68f1dd2887cd55d6798a5d9
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795156"
---
# <a name="restrictions-on-using-accessibility-levels-c-reference"></a>Einschränkungen bei der Verwendung von Zugriffsebenen (C#-Referenz)

Wenn Sie in einer Deklaration einen Typ angeben, überprüfen Sie, ob die Zugriffsebene dieses Typs von der Zugriffsebene eines Members oder eines anderen Typs abhängt. Auf die direkte Basisklasse muss z.B. mindestens genauso zugegriffen werden können wie auf die abgeleitete Klasse. Die folgende Deklaration verursacht einen Compilerfehler, da die Basisklasse `BaseClass` eine stärkere Zugriffsbeschränkung hat als `MyClass`:

```csharp
class BaseClass {...}
public class MyClass: BaseClass {...} // Error
```

In der folgenden Tabelle werden die Einschränkungen für deklarierte Zugriffsebenen zusammengefasst.

|Kontext|Hinweise|
|-------------|-------------|
|[Klassen](../../programming-guide/classes-and-structs/classes.md)|Die direkte Basisklasse eines Klassentyps muss mindesten dieselben Zugriffsmöglichkeiten wie der Klassentyp selbst bieten.|
|[Schnittstellen](../../programming-guide/interfaces/index.md)|Die explizite Basisschnittstelle eines Schnittstellentyps muss mindesten dieselben Zugriffsmöglichkeiten bieten wie der Schnittstellentyp selbst.|
|[Delegaten](../../programming-guide/delegates/index.md)|Die Rückgabe- und Parametertypen eines Delegattyps müssen mindestens dieselben Zugriffsmöglichkeiten wie der Delegattyp selbst bieten.|
|[Konstanten](../../programming-guide/classes-and-structs/constants.md)|Der Typ einer Konstante muss mindestens dieselben Zugriffsmöglichkeiten wie die Konstante selbst bieten.|
|[Felder](../../programming-guide/classes-and-structs/fields.md)|Der Typ eines Felds muss mindestens dieselben Zugriffsmöglichkeiten bieten wie das Feld selbst.|
|[Methoden](../../programming-guide/classes-and-structs/methods.md)|Die Rückgabe- und Parametertypen einer Methode müssen mindestens dieselben Zugriffsmöglichkeiten bieten wie die Methode selbst.|
|[Eigenschaften](../../programming-guide/classes-and-structs/properties.md)|Der Typ einer Eigenschaft muss mindestens dieselben Zugriffsmöglichkeiten bieten wie die Eigenschaft selbst.|
|[Ereignisse](../../programming-guide/events/index.md)|Der Typ eines Ereignisses muss mindestens dieselben Zugriffsmöglichkeiten bieten wie das Ereignis selbst.|
|[Indexer](../../programming-guide/indexers/index.md)|Der Typ und die Parametertypen eines Indexers müssen mindestens dieselben Zugriffsmöglichkeiten bieten wie der Indexer selbst.|
|[Operatoren](../operators/index.md)|Die Rückgabe- und Parametertypen eines Operators müssen mindestens dieselben Zugriffsmöglichkeiten bieten wie der Operator selbst.|
|[Konstruktoren](../../programming-guide/classes-and-structs/constructors.md)|Die Parametertypen eines Konstruktors müssen mindestens dieselben Zugriffsmöglichkeiten bieten wie der Konstruktor selbst.|

## <a name="example"></a>Beispiel

Das folgende Beispiel enthält fehlerhafte Deklarationen verschiedener Typen. Der Kommentar nach jeder Deklaration gibt den erwarteten Compilerfehler an.

```csharp
// Restrictions on Using Accessibility Levels
// CS0052 expected as well as CS0053, CS0056, and CS0057
// To make the program work, change access level of both class B
// and MyPrivateMethod() to public.

using System;

// A delegate:
delegate int MyDelegate();

class B
{
    // A private method:
    static int MyPrivateMethod()
    {
        return 0;
    }
}

public class A
{
    // Error: The type B is less accessible than the field A.myField.
    public B myField = new B();

    // Error: The type B is less accessible
    // than the constant A.myConst.
    public readonly B myConst = new B();

    public B MyMethod()
    {
        // Error: The type B is less accessible
        // than the method A.MyMethod.
        return new B();
    }

    // Error: The type B is less accessible than the property A.MyProp
    public B MyProp
    {
        set
        {
        }
    }

    MyDelegate d = new MyDelegate(B.MyPrivateMethod);
    // Even when B is declared public, you still get the error:
    // "The parameter B.MyPrivateMethod is not accessible due to
    // protection level."

    public static B operator +(A m1, B m2)
    {
        // Error: The type B is less accessible
        // than the operator A.operator +(A,B)
        return new B();
    }

    static void Main()
    {
        Console.Write("Compiled successfully");
    }
}
```

## <a name="c-language-specification"></a>C#-Sprachspezifikation

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Weitere Informationen

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Schlüsselwörter](index.md)
- [Zugriffsmodifizierer](access-modifiers.md)
- [Zugriffsdomäne](accessibility-domain.md)
- [Zugriffsebenen](accessibility-levels.md)
- [Zugriffsmodifizierer](../../programming-guide/classes-and-structs/access-modifiers.md)
- [public](public.md)
- [private](private.md)
- [protected](protected.md)
- [internal](internal.md)
