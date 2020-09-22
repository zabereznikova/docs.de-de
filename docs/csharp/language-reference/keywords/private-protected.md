---
description: private protected – C#-Referenz
title: private protected – C#-Referenz
ms.date: 11/15/2017
f1_keywords:
- privateprotected_CSharpKeyword
author: sputier
ms.openlocfilehash: e7ef6d691b43abd3d07321adfc0c166629ce9098
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90537300"
---
# <a name="private-protected-c-reference"></a><span data-ttu-id="ed34b-103">private protected (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="ed34b-103">private protected (C# Reference)</span></span>

<span data-ttu-id="ed34b-104">Die Schlüsselwortkombination `private protected` ist ein Zugriffsmodifizierer für Member.</span><span class="sxs-lookup"><span data-stu-id="ed34b-104">The `private protected` keyword combination is a member access modifier.</span></span> <span data-ttu-id="ed34b-105">Ein Member vom Typ „private protected“ kann von der von Typen aus zugegriffen werden, die von der enthaltenden Klasse abgeleitet werden, jedoch nur innerhalb der enthaltenden Assembly.</span><span class="sxs-lookup"><span data-stu-id="ed34b-105">A private protected member is accessible by types derived from the containing class, but only within its containing assembly.</span></span> <span data-ttu-id="ed34b-106">Einen Vergleich von `private protected` mit den anderen Zugriffsmodifizierern finden Sie unter [Zugriffsebenen](accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="ed34b-106">For a comparison of `private protected` with the other access modifiers, see [Accessibility Levels](accessibility-levels.md).</span></span>

> [!NOTE]
> <span data-ttu-id="ed34b-107">Der Zugriffsmodifizierer `private protected` ist in C# 7.2 und höher gültig.</span><span class="sxs-lookup"><span data-stu-id="ed34b-107">The `private protected` access modifier is valid in C# version 7.2 and later.</span></span>

## <a name="example"></a><span data-ttu-id="ed34b-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ed34b-108">Example</span></span>

<span data-ttu-id="ed34b-109">Ein Member vom Typ „private protected“ einer Basisklasse kann nur dann von abgeleiteten Typen innerhalb seiner enthaltenden Assembly aus zugegriffen werden, wenn der statische Typ der Variable der abgeleitete Klassentyp ist.</span><span class="sxs-lookup"><span data-stu-id="ed34b-109">A private protected member of a base class is accessible from derived types in its containing assembly only if the static type of the variable is the derived class type.</span></span> <span data-ttu-id="ed34b-110">Sehen Sie sich z.B. folgenden Codeabschnitt an:</span><span class="sxs-lookup"><span data-stu-id="ed34b-110">For example, consider the following code segment:</span></span>

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

<span data-ttu-id="ed34b-111">Dieses Beispiel enthält zwei Dateien, `Assembly1.cs` und `Assembly2.cs`.</span><span class="sxs-lookup"><span data-stu-id="ed34b-111">This example contains two files, `Assembly1.cs` and `Assembly2.cs`.</span></span>
<span data-ttu-id="ed34b-112">Die erste Datei enthält eine öffentliche Basisklasse, `BaseClass`, und einen davon abgeleiteten Typ, `DerivedClass1`.</span><span class="sxs-lookup"><span data-stu-id="ed34b-112">The first file contains a public base class, `BaseClass`, and a type derived from it, `DerivedClass1`.</span></span> <span data-ttu-id="ed34b-113">`BaseClass` besitzt einen Member vom Typ „private protected“, `myValue`, auf den `DerivedClass1` auf zwei Arten zuzugreifen versucht.</span><span class="sxs-lookup"><span data-stu-id="ed34b-113">`BaseClass` owns a private protected member, `myValue`, which `DerivedClass1` tries to access in two ways.</span></span> <span data-ttu-id="ed34b-114">Der erste Versuch, über eine Instanz von `BaseClass` auf `myValue` zuzugreifen, führt zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="ed34b-114">The first attempt to access `myValue` through an instance of `BaseClass` will produce an error.</span></span> <span data-ttu-id="ed34b-115">Der Versuch, es als geerbten Member in `DerivedClass1` zu verwenden, gelingt jedoch.</span><span class="sxs-lookup"><span data-stu-id="ed34b-115">However, the attempt to use it as an inherited member in `DerivedClass1` will succeed.</span></span>

<span data-ttu-id="ed34b-116">In der zweiten Datei wird ein Versuch, auf `myValue` als geerbtes Mitglied von `DerivedClass2` zuzugreifen, einen Fehler erzeugen, da nur von abgeleiteten Typen in Assembly1 darauf zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="ed34b-116">In the second file, an attempt to access `myValue` as an inherited member of `DerivedClass2` will produce an error, as it is only accessible by derived types in Assembly1.</span></span>

<span data-ttu-id="ed34b-117">Wenn `Assembly1.cs` ein <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> namens `Assembly2` enthält, hat die abgeleitete Klasse `DerivedClass1` Zugriff auf `private protected`-Member, die in `BaseClass` deklariert sind.</span><span class="sxs-lookup"><span data-stu-id="ed34b-117">If `Assembly1.cs` contains an <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> that names `Assembly2`, the derived class `DerivedClass1` will have access to `private protected` members declared in `BaseClass`.</span></span> <span data-ttu-id="ed34b-118">`InternalsVisibleTo` macht `private protected`-Member für abgeleitete Klassen in anderen Assemblys sichtbar.</span><span class="sxs-lookup"><span data-stu-id="ed34b-118">`InternalsVisibleTo` makes `private protected` members visible to derived classes in other assemblies.</span></span>

<span data-ttu-id="ed34b-119">Strukturmember können nicht vom Typ `private protected` sein, da die Struktur nicht vererbt werden kann.</span><span class="sxs-lookup"><span data-stu-id="ed34b-119">Struct members cannot be `private protected` because the struct cannot be inherited.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="ed34b-120">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="ed34b-120">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="ed34b-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ed34b-121">See also</span></span>

- [<span data-ttu-id="ed34b-122">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="ed34b-122">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="ed34b-123">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="ed34b-123">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="ed34b-124">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="ed34b-124">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="ed34b-125">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="ed34b-125">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="ed34b-126">Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="ed34b-126">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="ed34b-127">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="ed34b-127">Modifiers</span></span>](index.md)
- [<span data-ttu-id="ed34b-128">public</span><span class="sxs-lookup"><span data-stu-id="ed34b-128">public</span></span>](public.md)
- [<span data-ttu-id="ed34b-129">private</span><span class="sxs-lookup"><span data-stu-id="ed34b-129">private</span></span>](private.md)
- [<span data-ttu-id="ed34b-130">internal</span><span class="sxs-lookup"><span data-stu-id="ed34b-130">internal</span></span>](internal.md)
- <span data-ttu-id="ed34b-131">[Sicherheitsaspekte für interne virtuelle Schlüsselwörter](/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="ed34b-131">[Security concerns for internal virtual keywords](/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span></span>
