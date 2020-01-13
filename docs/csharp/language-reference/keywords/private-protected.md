---
title: private protected – C#-Referenz
ms.date: 11/15/2017
author: sputier
ms.openlocfilehash: a73d61712075cf24d2b94c505104df1fade629e9
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713208"
---
# <a name="private-protected-c-reference"></a><span data-ttu-id="b56a5-102">private protected (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="b56a5-102">private protected (C# Reference)</span></span>

<span data-ttu-id="b56a5-103">Die Schlüsselwortkombination `private protected` ist ein Zugriffsmodifizierer für Member.</span><span class="sxs-lookup"><span data-stu-id="b56a5-103">The `private protected` keyword combination is a member access modifier.</span></span> <span data-ttu-id="b56a5-104">Ein Member vom Typ „private protected“ kann von der von Typen aus zugegriffen werden, die von der enthaltenden Klasse abgeleitet werden, jedoch nur innerhalb der enthaltenden Assembly.</span><span class="sxs-lookup"><span data-stu-id="b56a5-104">A private protected member is accessible by types derived from the containing class, but only within its containing assembly.</span></span> <span data-ttu-id="b56a5-105">Einen Vergleich von `private protected` mit den anderen Zugriffsmodifizierern finden Sie unter [Zugriffsebenen](accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="b56a5-105">For a comparison of `private protected` with the other access modifiers, see [Accessibility Levels](accessibility-levels.md).</span></span>

> [!NOTE]
> <span data-ttu-id="b56a5-106">Der Zugriffsmodifizierer `private protected` ist in C# 7.2 und höher gültig.</span><span class="sxs-lookup"><span data-stu-id="b56a5-106">The `private protected` access modifier is valid in C# version 7.2 and later.</span></span>

## <a name="example"></a><span data-ttu-id="b56a5-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b56a5-107">Example</span></span>

<span data-ttu-id="b56a5-108">Ein Member vom Typ „private protected“ einer Basisklasse kann nur dann von abgeleiteten Typen innerhalb seiner enthaltenden Assembly aus zugegriffen werden, wenn der statische Typ der Variable der abgeleitete Klassentyp ist.</span><span class="sxs-lookup"><span data-stu-id="b56a5-108">A private protected member of a base class is accessible from derived types in its containing assembly only if the static type of the variable is the derived class type.</span></span> <span data-ttu-id="b56a5-109">Sehen Sie sich z.B. folgenden Codeabschnitt an:</span><span class="sxs-lookup"><span data-stu-id="b56a5-109">For example, consider the following code segment:</span></span>  

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

<span data-ttu-id="b56a5-110">Dieses Beispiel enthält zwei Dateien, `Assembly1.cs` und `Assembly2.cs`.</span><span class="sxs-lookup"><span data-stu-id="b56a5-110">This example contains two files, `Assembly1.cs` and `Assembly2.cs`.</span></span>
<span data-ttu-id="b56a5-111">Die erste Datei enthält eine öffentliche Basisklasse, `BaseClass`, und einen davon abgeleiteten Typ, `DerivedClass1`.</span><span class="sxs-lookup"><span data-stu-id="b56a5-111">The first file contains a public base class, `BaseClass`, and a type derived from it, `DerivedClass1`.</span></span> <span data-ttu-id="b56a5-112">`BaseClass` besitzt einen Member vom Typ „private protected“, `myValue`, auf den `DerivedClass1` auf zwei Arten zuzugreifen versucht.</span><span class="sxs-lookup"><span data-stu-id="b56a5-112">`BaseClass` owns a private protected member, `myValue`, which `DerivedClass1` tries to access in two ways.</span></span> <span data-ttu-id="b56a5-113">Der erste Versuch, über eine Instanz von `BaseClass` auf `myValue` zuzugreifen, führt zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="b56a5-113">The first attempt to access `myValue` through an instance of `BaseClass` will produce an error.</span></span> <span data-ttu-id="b56a5-114">Der Versuch, es als geerbten Member in `DerivedClass1` zu verwenden, gelingt jedoch.</span><span class="sxs-lookup"><span data-stu-id="b56a5-114">However, the attempt to use it as an inherited member in `DerivedClass1` will succeed.</span></span>
<span data-ttu-id="b56a5-115">In der zweiten Datei wird ein Versuch, auf `myValue` als geerbtes Mitglied von `DerivedClass2` zuzugreifen, einen Fehler erzeugen, da nur von abgeleiteten Typen in Assembly1 darauf zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="b56a5-115">In the second file, an attempt to access `myValue` as an inherited member of `DerivedClass2` will produce an error, as it is only accessible by derived types in Assembly1.</span></span>

<span data-ttu-id="b56a5-116">Strukturmember können nicht vom Typ `private protected` sein, da die Struktur nicht vererbt werden kann.</span><span class="sxs-lookup"><span data-stu-id="b56a5-116">Struct members cannot be `private protected` because the struct cannot be inherited.</span></span>  

## <a name="c-language-specification"></a><span data-ttu-id="b56a5-117">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="b56a5-117">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  

## <a name="see-also"></a><span data-ttu-id="b56a5-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b56a5-118">See also</span></span>

- [<span data-ttu-id="b56a5-119">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="b56a5-119">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="b56a5-120">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="b56a5-120">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="b56a5-121">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="b56a5-121">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="b56a5-122">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="b56a5-122">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="b56a5-123">Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="b56a5-123">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="b56a5-124">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="b56a5-124">Modifiers</span></span>](index.md)
- [<span data-ttu-id="b56a5-125">public</span><span class="sxs-lookup"><span data-stu-id="b56a5-125">public</span></span>](public.md)
- [<span data-ttu-id="b56a5-126">private</span><span class="sxs-lookup"><span data-stu-id="b56a5-126">private</span></span>](private.md)
- [<span data-ttu-id="b56a5-127">internal</span><span class="sxs-lookup"><span data-stu-id="b56a5-127">internal</span></span>](internal.md)
- <span data-ttu-id="b56a5-128">[Sicherheitsaspekte für interne virtuelle Schlüsselwörter](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b56a5-128">[Security concerns for internal virtual keywords](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span></span>
