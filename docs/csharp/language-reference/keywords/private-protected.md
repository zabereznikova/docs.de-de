---
title: private protected – C#-Referenz
ms.custom: seodec18
ms.date: 11/15/2017
author: sputier
ms.openlocfilehash: dfb2e754d81116012b9fc3f8fd4f6fe1ad0daef1
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73422626"
---
# <a name="private-protected-c-reference"></a>private protected (C#-Referenz)

Die Schlüsselwortkombination `private protected` ist ein Zugriffsmodifizierer für Member. Ein Member vom Typ „private protected“ kann von der von Typen aus zugegriffen werden, die von der enthaltenden Klasse abgeleitet werden, jedoch nur innerhalb der enthaltenden Assembly. Einen Vergleich von `private protected` mit den anderen Zugriffsmodifizierern finden Sie unter [Zugriffsebenen](accessibility-levels.md).

> [!NOTE]
> Der Zugriffsmodifizierer `private protected` ist in C# 7.2 und höher gültig.

## <a name="example"></a>Beispiel

Ein Member vom Typ „private protected“ einer Basisklasse kann nur dann von abgeleiteten Typen innerhalb seiner enthaltenden Assembly aus zugegriffen werden, wenn der statische Typ der Variable der abgeleitete Klassentyp ist. Sehen Sie sich z.B. folgenden Codeabschnitt an:  

```csharp
// Assembly1.cs  
// Compile with: /target:library  
public class BaseClass
{
    private protected int myValue = 0;
}

public class DerivedClass1 : BaseClass
{
    void Access()
    {
        var baseObject = new BaseClass();

        // Error CS1540, because myValue can only be accessed by
        // classes derived from BaseClass.
        // baseObject.myValue = 5;  

        // OK, accessed through the current derived class instance
        myValue = 5;
    }
}
```

```csharp
// Assembly2.cs  
// Compile with: /reference:Assembly1.dll  
class DerivedClass2 : BaseClass
{
    void Access()
    {
        // Error CS0122, because myValue can only be
        // accessed by types in Assembly1
        // myValue = 10;
    }
}
```

Dieses Beispiel enthält zwei Dateien, `Assembly1.cs` und `Assembly2.cs`.
Die erste Datei enthält eine öffentliche Basisklasse, `BaseClass`, und einen davon abgeleiteten Typ, `DerivedClass1`. `BaseClass` besitzt einen Member vom Typ „private protected“, `myValue`, auf den `DerivedClass1` auf zwei Arten zuzugreifen versucht. Der erste Versuch, über eine Instanz von `BaseClass` auf `myValue` zuzugreifen, führt zu einem Fehler. Der Versuch, es als geerbten Member in `DerivedClass1` zu verwenden, gelingt jedoch.
In der zweiten Datei wird ein Versuch, auf `myValue` als geerbtes Mitglied von `DerivedClass2` zuzugreifen, einen Fehler erzeugen, da nur von abgeleiteten Typen in Assembly1 darauf zugegriffen werden kann.

Strukturmember können nicht vom Typ `private protected` sein, da die Struktur nicht vererbt werden kann.  

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
