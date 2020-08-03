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
# <a name="protected-internal-c-reference"></a><span data-ttu-id="62f3e-102">protected internal (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="62f3e-102">protected internal (C# Reference)</span></span>

<span data-ttu-id="62f3e-103">Die Schlüsselwortkombination `protected internal` ist ein Zugriffsmodifizierer für Member.</span><span class="sxs-lookup"><span data-stu-id="62f3e-103">The `protected internal` keyword combination is a member access modifier.</span></span> <span data-ttu-id="62f3e-104">Ein Member vom Typ „protected internal“ kann von der aktuellen Assembly oder von Typen aus zugegriffen werden, die von der enthaltenden Klasse abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="62f3e-104">A protected internal member is accessible from the current assembly or from types that are derived from the containing class.</span></span> <span data-ttu-id="62f3e-105">Einen Vergleich von `protected internal` mit den anderen Zugriffsmodifizierern finden Sie unter [Zugriffsebenen](accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="62f3e-105">For a comparison of `protected internal` with the other access modifiers, see [Accessibility Levels](accessibility-levels.md).</span></span>

## <a name="example"></a><span data-ttu-id="62f3e-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="62f3e-106">Example</span></span>

<span data-ttu-id="62f3e-107">Ein Member vom Typ „protected internal“ einer Basisklasse kann von jedem Typ innerhalb seiner enthaltenden Assembly aus zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="62f3e-107">A protected internal member of a base class is accessible from any type within its containing assembly.</span></span> <span data-ttu-id="62f3e-108">Sie kann auch von einer abgeleiteten Klasse zugegriffen werden, die sich in einer anderen Assembly befindet, jedoch nur, wenn der Zugriff über eine Variable des abgeleiteten Klassentyps erfolgt.</span><span class="sxs-lookup"><span data-stu-id="62f3e-108">It is also accessible in a derived class located in another assembly only if the access occurs through a variable of the derived class type.</span></span> <span data-ttu-id="62f3e-109">Sehen Sie sich z.B. folgenden Codeabschnitt an:</span><span class="sxs-lookup"><span data-stu-id="62f3e-109">For example, consider the following code segment:</span></span>

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

<span data-ttu-id="62f3e-110">Dieses Beispiel enthält zwei Dateien, `Assembly1.cs` und `Assembly2.cs`.</span><span class="sxs-lookup"><span data-stu-id="62f3e-110">This example contains two files, `Assembly1.cs` and `Assembly2.cs`.</span></span>
<span data-ttu-id="62f3e-111">Die erste Datei enthält eine öffentliche Basisklasse, `BaseClass`, und eine weitere Klasse, `TestAccess`.</span><span class="sxs-lookup"><span data-stu-id="62f3e-111">The first file contains a public base class, `BaseClass`, and another class, `TestAccess`.</span></span> <span data-ttu-id="62f3e-112">`BaseClass` besitzt einen Member vom Typ „protected internal“, `myValue`, auf den über den Typ `TestAccess` zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="62f3e-112">`BaseClass` owns a protected internal member, `myValue`, which is accessed by the `TestAccess` type.</span></span>
<span data-ttu-id="62f3e-113">In der zweiten Datei verursacht ein Versuch, über eine `BaseClass`-Instanz auf `myValue` zuzugreifen, einen Fehler, während ein Zugriff auf diesen Member über eine Instanz einer abgeleiteten Klasse `DerivedClass` gelingt.</span><span class="sxs-lookup"><span data-stu-id="62f3e-113">In the second file, an attempt to access `myValue` through an instance of `BaseClass` will produce an error, while an access to this member through an instance of a derived class, `DerivedClass` will succeed.</span></span>

<span data-ttu-id="62f3e-114">Strukturmember können nicht vom Typ `protected internal` sein, da die Struktur nicht vererbt werden kann.</span><span class="sxs-lookup"><span data-stu-id="62f3e-114">Struct members cannot be `protected internal` because the struct cannot be inherited.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="62f3e-115">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="62f3e-115">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="62f3e-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="62f3e-116">See also</span></span>

- [<span data-ttu-id="62f3e-117">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="62f3e-117">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="62f3e-118">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="62f3e-118">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="62f3e-119">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="62f3e-119">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="62f3e-120">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="62f3e-120">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="62f3e-121">Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="62f3e-121">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="62f3e-122">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="62f3e-122">Modifiers</span></span>](index.md)
- [<span data-ttu-id="62f3e-123">public</span><span class="sxs-lookup"><span data-stu-id="62f3e-123">public</span></span>](public.md)
- [<span data-ttu-id="62f3e-124">private</span><span class="sxs-lookup"><span data-stu-id="62f3e-124">private</span></span>](private.md)
- [<span data-ttu-id="62f3e-125">internal</span><span class="sxs-lookup"><span data-stu-id="62f3e-125">internal</span></span>](internal.md)
- <span data-ttu-id="62f3e-126">[Sicherheitsaspekte für interne virtuelle Schlüsselwörter](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="62f3e-126">[Security concerns for internal virtual keywords](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span></span>
