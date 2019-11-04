---
title: protected internal – C#-Referenz
ms.custom: seodec18
ms.date: 11/15/2017
author: sputier
ms.openlocfilehash: 6e5a4c6e63c2c05df54df6bed542eab3f43f9272
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73422587"
---
# <a name="protected-internal-c-reference"></a>protected internal (C#-Referenz)

Die Schlüsselwortkombination `protected internal` ist ein Zugriffsmodifizierer für Member. Ein Member vom Typ „protected internal“ kann von der aktuellen Assembly oder von Typen aus zugegriffen werden, die von der enthaltenden Klasse abgeleitet werden. Einen Vergleich von `protected internal` mit den anderen Zugriffsmodifizierern finden Sie unter [Zugriffsebenen](accessibility-levels.md).

## <a name="example"></a>Beispiel

Ein Member vom Typ „protected internal“ einer Basisklasse kann von jedem Typ innerhalb seiner enthaltenden Assembly aus zugegriffen werden. Sie kann auch von einer abgeleiteten Klasse zugegriffen werden, die sich in einer anderen Assembly befindet, jedoch nur, wenn der Zugriff über eine Variable des abgeleiteten Klassentyps erfolgt. Sehen Sie sich z.B. folgenden Codeabschnitt an:

```csharp
// Assembly1.cs
// Compile with: /target:library
public class BaseClass
{
   protected internal int myValue = 0;
}

class TestAccess
{
    void Access()
    {
        var baseObject = new BaseClass();
        baseObject.myValue = 5;
    }
}
```

```csharp
// Assembly2.cs
// Compile with: /reference:Assembly1.dll
class DerivedClass : BaseClass
{
    static void Main()
    {
        var baseObject = new BaseClass();
        var derivedObject = new DerivedClass();

        // Error CS1540, because myValue can only be accessed by
        // classes derived from BaseClass.
        // baseObject.myValue = 10;

        // OK, because this class derives from BaseClass.
        derivedObject.myValue = 10;
    }
}
```

Dieses Beispiel enthält zwei Dateien, `Assembly1.cs` und `Assembly2.cs`.
Die erste Datei enthält eine öffentliche Basisklasse, `BaseClass`, und eine weitere Klasse, `TestAccess`. `BaseClass` besitzt einen Member vom Typ „protected internal“, `myValue`, auf den über den Typ `TestAccess` zugegriffen wird.
In der zweiten Datei verursacht ein Versuch, über eine `BaseClass`-Instanz auf `myValue` zuzugreifen, einen Fehler, während ein Zugriff auf diesen Member über eine Instanz einer abgeleiteten Klasse `DerivedClass` gelingt.

Strukturmember können nicht vom Typ `protected internal` sein, da die Struktur nicht vererbt werden kann.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Schlüsselwörter](index.md)
- [Zugriffsmodifizierer](access-modifiers.md)
- [Zugriffsebenen](accessibility-levels.md)
- [Modifizierer](index.md)
- [public](public.md)
- [private](private.md)
- [internal](internal.md)
- [Sicherheitsaspekte für interne virtuelle Schlüsselwörter](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))
