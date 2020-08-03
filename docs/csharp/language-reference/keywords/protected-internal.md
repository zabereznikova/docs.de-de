---
title: protected internal – C#-Referenz
ms.date: 11/15/2017
f1_keywords:
- protectedinternal_CSharpKeyword
author: sputier
ms.openlocfilehash: 4067da93bcceba0fa3e4a14aa58b4cde812412f3
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301787"
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

## <a name="see-also"></a>Weitere Informationen

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
