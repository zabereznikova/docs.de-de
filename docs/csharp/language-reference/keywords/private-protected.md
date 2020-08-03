---
title: private protected – C#-Referenz
ms.date: 11/15/2017
f1_keywords:
- privateprotected_CSharpKeyword
author: sputier
ms.openlocfilehash: 94ef55d7e13841f81b036f52659b215e22a3a0d7
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301800"
---
# <a name="private-protected-c-reference"></a><span data-ttu-id="fbafb-102">private protected (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="fbafb-102">private protected (C# Reference)</span></span>

<span data-ttu-id="fbafb-103">Die Schlüsselwortkombination `private protected` ist ein Zugriffsmodifizierer für Member.</span><span class="sxs-lookup"><span data-stu-id="fbafb-103">The `private protected` keyword combination is a member access modifier.</span></span> <span data-ttu-id="fbafb-104">Ein Member vom Typ „private protected“ kann von der von Typen aus zugegriffen werden, die von der enthaltenden Klasse abgeleitet werden, jedoch nur innerhalb der enthaltenden Assembly.</span><span class="sxs-lookup"><span data-stu-id="fbafb-104">A private protected member is accessible by types derived from the containing class, but only within its containing assembly.</span></span> <span data-ttu-id="fbafb-105">Einen Vergleich von `private protected` mit den anderen Zugriffsmodifizierern finden Sie unter [Zugriffsebenen](accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="fbafb-105">For a comparison of `private protected` with the other access modifiers, see [Accessibility Levels](accessibility-levels.md).</span></span>

> [!NOTE]
> <span data-ttu-id="fbafb-106">Der Zugriffsmodifizierer `private protected` ist in C# 7.2 und höher gültig.</span><span class="sxs-lookup"><span data-stu-id="fbafb-106">The `private protected` access modifier is valid in C# version 7.2 and later.</span></span>

## <a name="example"></a><span data-ttu-id="fbafb-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fbafb-107">Example</span></span>

<span data-ttu-id="fbafb-108">Ein Member vom Typ „private protected“ einer Basisklasse kann nur dann von abgeleiteten Typen innerhalb seiner enthaltenden Assembly aus zugegriffen werden, wenn der statische Typ der Variable der abgeleitete Klassentyp ist.</span><span class="sxs-lookup"><span data-stu-id="fbafb-108">A private protected member of a base class is accessible from derived types in its containing assembly only if the static type of the variable is the derived class type.</span></span> <span data-ttu-id="fbafb-109">Sehen Sie sich z.B. folgenden Codeabschnitt an:</span><span class="sxs-lookup"><span data-stu-id="fbafb-109">For example, consider the following code segment:</span></span>

```csharp
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

<span data-ttu-id="fbafb-110">Dieses Beispiel enthält zwei Dateien, `Assembly1.cs` und `Assembly2.cs`.</span><span class="sxs-lookup"><span data-stu-id="fbafb-110">This example contains two files, `Assembly1.cs` and `Assembly2.cs`.</span></span>
<span data-ttu-id="fbafb-111">Die erste Datei enthält eine öffentliche Basisklasse, `BaseClass`, und einen davon abgeleiteten Typ, `DerivedClass1`.</span><span class="sxs-lookup"><span data-stu-id="fbafb-111">The first file contains a public base class, `BaseClass`, and a type derived from it, `DerivedClass1`.</span></span> <span data-ttu-id="fbafb-112">`BaseClass` besitzt einen Member vom Typ „private protected“, `myValue`, auf den `DerivedClass1` auf zwei Arten zuzugreifen versucht.</span><span class="sxs-lookup"><span data-stu-id="fbafb-112">`BaseClass` owns a private protected member, `myValue`, which `DerivedClass1` tries to access in two ways.</span></span> <span data-ttu-id="fbafb-113">Der erste Versuch, über eine Instanz von `BaseClass` auf `myValue` zuzugreifen, führt zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="fbafb-113">The first attempt to access `myValue` through an instance of `BaseClass` will produce an error.</span></span> <span data-ttu-id="fbafb-114">Der Versuch, es als geerbten Member in `DerivedClass1` zu verwenden, gelingt jedoch.</span><span class="sxs-lookup"><span data-stu-id="fbafb-114">However, the attempt to use it as an inherited member in `DerivedClass1` will succeed.</span></span>

<span data-ttu-id="fbafb-115">In der zweiten Datei wird ein Versuch, auf `myValue` als geerbtes Mitglied von `DerivedClass2` zuzugreifen, einen Fehler erzeugen, da nur von abgeleiteten Typen in Assembly1 darauf zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="fbafb-115">In the second file, an attempt to access `myValue` as an inherited member of `DerivedClass2` will produce an error, as it is only accessible by derived types in Assembly1.</span></span>

<span data-ttu-id="fbafb-116">Wenn `Assembly1.cs` ein <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> namens `Assembly2` enthält, hat die abgeleitete Klasse `DerivedClass1` Zugriff auf `private protected`-Member, die in `BaseClass` deklariert sind.</span><span class="sxs-lookup"><span data-stu-id="fbafb-116">If `Assembly1.cs` contains an <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> that names `Assembly2`, the derived class `DerivedClass1` will have access to `private protected` members declared in `BaseClass`.</span></span> <span data-ttu-id="fbafb-117">`InternalsVisibleTo` macht `private protected`-Member für abgeleitete Klassen in anderen Assemblys sichtbar.</span><span class="sxs-lookup"><span data-stu-id="fbafb-117">`InternalsVisibleTo` makes `private protected` members visible to derived classes in other assemblies.</span></span>

<span data-ttu-id="fbafb-118">Strukturmember können nicht vom Typ `private protected` sein, da die Struktur nicht vererbt werden kann.</span><span class="sxs-lookup"><span data-stu-id="fbafb-118">Struct members cannot be `private protected` because the struct cannot be inherited.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="fbafb-119">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="fbafb-119">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="fbafb-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fbafb-120">See also</span></span>

- [<span data-ttu-id="fbafb-121">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="fbafb-121">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="fbafb-122">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="fbafb-122">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="fbafb-123">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="fbafb-123">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="fbafb-124">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="fbafb-124">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="fbafb-125">Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="fbafb-125">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="fbafb-126">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="fbafb-126">Modifiers</span></span>](index.md)
- [<span data-ttu-id="fbafb-127">public</span><span class="sxs-lookup"><span data-stu-id="fbafb-127">public</span></span>](public.md)
- [<span data-ttu-id="fbafb-128">private</span><span class="sxs-lookup"><span data-stu-id="fbafb-128">private</span></span>](private.md)
- [<span data-ttu-id="fbafb-129">internal</span><span class="sxs-lookup"><span data-stu-id="fbafb-129">internal</span></span>](internal.md)
- <span data-ttu-id="fbafb-130">[Sicherheitsaspekte für interne virtuelle Schlüsselwörter](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="fbafb-130">[Security concerns for internal virtual keywords](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span></span>
