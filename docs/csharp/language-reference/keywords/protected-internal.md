---
description: protected internal – C#-Referenz
title: protected internal – C#-Referenz
ms.date: 11/15/2017
f1_keywords:
- protectedinternal_CSharpKeyword
author: sputier
ms.openlocfilehash: f22de104154df74f02c048b1209eeac754a03e64
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90536800"
---
# <a name="protected-internal-c-reference"></a><span data-ttu-id="5e253-103">protected internal (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="5e253-103">protected internal (C# Reference)</span></span>

<span data-ttu-id="5e253-104">Die Schlüsselwortkombination `protected internal` ist ein Zugriffsmodifizierer für Member.</span><span class="sxs-lookup"><span data-stu-id="5e253-104">The `protected internal` keyword combination is a member access modifier.</span></span> <span data-ttu-id="5e253-105">Ein Member vom Typ „protected internal“ kann von der aktuellen Assembly oder von Typen aus zugegriffen werden, die von der enthaltenden Klasse abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="5e253-105">A protected internal member is accessible from the current assembly or from types that are derived from the containing class.</span></span> <span data-ttu-id="5e253-106">Einen Vergleich von `protected internal` mit den anderen Zugriffsmodifizierern finden Sie unter [Zugriffsebenen](accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="5e253-106">For a comparison of `protected internal` with the other access modifiers, see [Accessibility Levels](accessibility-levels.md).</span></span>

## <a name="example"></a><span data-ttu-id="5e253-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5e253-107">Example</span></span>

<span data-ttu-id="5e253-108">Ein Member vom Typ „protected internal“ einer Basisklasse kann von jedem Typ innerhalb seiner enthaltenden Assembly aus zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="5e253-108">A protected internal member of a base class is accessible from any type within its containing assembly.</span></span> <span data-ttu-id="5e253-109">Sie kann auch von einer abgeleiteten Klasse zugegriffen werden, die sich in einer anderen Assembly befindet, jedoch nur, wenn der Zugriff über eine Variable des abgeleiteten Klassentyps erfolgt.</span><span class="sxs-lookup"><span data-stu-id="5e253-109">It is also accessible in a derived class located in another assembly only if the access occurs through a variable of the derived class type.</span></span> <span data-ttu-id="5e253-110">Sehen Sie sich z.B. folgenden Codeabschnitt an:</span><span class="sxs-lookup"><span data-stu-id="5e253-110">For example, consider the following code segment:</span></span>

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

<span data-ttu-id="5e253-111">Dieses Beispiel enthält zwei Dateien, `Assembly1.cs` und `Assembly2.cs`.</span><span class="sxs-lookup"><span data-stu-id="5e253-111">This example contains two files, `Assembly1.cs` and `Assembly2.cs`.</span></span>
<span data-ttu-id="5e253-112">Die erste Datei enthält eine öffentliche Basisklasse, `BaseClass`, und eine weitere Klasse, `TestAccess`.</span><span class="sxs-lookup"><span data-stu-id="5e253-112">The first file contains a public base class, `BaseClass`, and another class, `TestAccess`.</span></span> <span data-ttu-id="5e253-113">`BaseClass` besitzt einen Member vom Typ „protected internal“, `myValue`, auf den über den Typ `TestAccess` zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="5e253-113">`BaseClass` owns a protected internal member, `myValue`, which is accessed by the `TestAccess` type.</span></span>
<span data-ttu-id="5e253-114">In der zweiten Datei verursacht ein Versuch, über eine `BaseClass`-Instanz auf `myValue` zuzugreifen, einen Fehler, während ein Zugriff auf diesen Member über eine Instanz einer abgeleiteten Klasse `DerivedClass` gelingt.</span><span class="sxs-lookup"><span data-stu-id="5e253-114">In the second file, an attempt to access `myValue` through an instance of `BaseClass` will produce an error, while an access to this member through an instance of a derived class, `DerivedClass` will succeed.</span></span>

<span data-ttu-id="5e253-115">Strukturmember können nicht vom Typ `protected internal` sein, da die Struktur nicht vererbt werden kann.</span><span class="sxs-lookup"><span data-stu-id="5e253-115">Struct members cannot be `protected internal` because the struct cannot be inherited.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="5e253-116">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="5e253-116">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="5e253-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5e253-117">See also</span></span>

- [<span data-ttu-id="5e253-118">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="5e253-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="5e253-119">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="5e253-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="5e253-120">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="5e253-120">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="5e253-121">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="5e253-121">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="5e253-122">Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="5e253-122">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="5e253-123">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="5e253-123">Modifiers</span></span>](index.md)
- [<span data-ttu-id="5e253-124">public</span><span class="sxs-lookup"><span data-stu-id="5e253-124">public</span></span>](public.md)
- [<span data-ttu-id="5e253-125">private</span><span class="sxs-lookup"><span data-stu-id="5e253-125">private</span></span>](private.md)
- [<span data-ttu-id="5e253-126">internal</span><span class="sxs-lookup"><span data-stu-id="5e253-126">internal</span></span>](internal.md)
- <span data-ttu-id="5e253-127">[Sicherheitsaspekte für interne virtuelle Schlüsselwörter](/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="5e253-127">[Security concerns for internal virtual keywords](/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span></span>
