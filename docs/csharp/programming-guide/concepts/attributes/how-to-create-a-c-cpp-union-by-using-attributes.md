---
title: Erstellen einer Union in C/C++ mithilfe von Attributen (C#)
description: Hier erfahren Sie, wie Sie in C# mithilfe von Attributen anpassen können, wie Strukturen im Arbeitsspeicher angeordnet werden. In diesem Beispiel wird die Entsprechung einer Union in C/C++ implementiert.
ms.date: 07/20/2015
ms.assetid: 85f35e56-26e0-4d31-9f3a-89bd4005e71a
ms.openlocfilehash: 766a070105441630dfd8fecf7b9f68fa6818fe50
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925071"
---
# <a name="how-to-create-a-cc-union-by-using-attributes-c"></a><span data-ttu-id="d6cbd-104">Erstellen einer Union in C/C++ mithilfe von Attributen (C#)</span><span class="sxs-lookup"><span data-stu-id="d6cbd-104">How to create a C/C++ union by using attributes (C#)</span></span>

<span data-ttu-id="d6cbd-105">Mithilfe von Attributen können Sie anpassen, wie Strukturen im Arbeitsspeicher angeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="d6cbd-105">By using attributes, you can customize how structs are laid out in memory.</span></span> <span data-ttu-id="d6cbd-106">Sie können z.B. das erstellen, was als eine Union in C/C++ bekannt ist, indem Sie die mit `StructLayout(LayoutKind.Explicit)`- und `FieldOffset`-Attribute verwenden.</span><span class="sxs-lookup"><span data-stu-id="d6cbd-106">For example, you can create what is known as a union in C/C++ by using the `StructLayout(LayoutKind.Explicit)` and `FieldOffset` attributes.</span></span>

## <a name="example"></a><span data-ttu-id="d6cbd-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d6cbd-107">Example</span></span>

<span data-ttu-id="d6cbd-108">In diesem Codesegment beginnen alle Felder von `TestUnion` an derselben Position im Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="d6cbd-108">In this code segment, all of the fields of `TestUnion` start at the same location in memory.</span></span>

```csharp
// Add a using directive for System.Runtime.InteropServices.

[System.Runtime.InteropServices.StructLayout(LayoutKind.Explicit)]
struct TestUnion
{
    [System.Runtime.InteropServices.FieldOffset(0)]
    public int i;

    [System.Runtime.InteropServices.FieldOffset(0)]
    public double d;

    [System.Runtime.InteropServices.FieldOffset(0)]
    public char c;

    [System.Runtime.InteropServices.FieldOffset(0)]
    public byte b;
}
```

## <a name="example"></a><span data-ttu-id="d6cbd-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d6cbd-109">Example</span></span>

<span data-ttu-id="d6cbd-110">Im Folgenden finden Sie ein weiteres Beispiel, in dem Felder an verschiedenen, explizit festgelegten Orten beginnen.</span><span class="sxs-lookup"><span data-stu-id="d6cbd-110">The following is another example where fields start at different explicitly set locations.</span></span>

```csharp
// Add a using directive for System.Runtime.InteropServices.

[System.Runtime.InteropServices.StructLayout(LayoutKind.Explicit)]
struct TestExplicit
{
    [System.Runtime.InteropServices.FieldOffset(0)]
    public long lg;

    [System.Runtime.InteropServices.FieldOffset(0)]
    public int i1;

    [System.Runtime.InteropServices.FieldOffset(4)]
    public int i2;

    [System.Runtime.InteropServices.FieldOffset(8)]
    public double d;

    [System.Runtime.InteropServices.FieldOffset(12)]
    public char c;

    [System.Runtime.InteropServices.FieldOffset(14)]
    public byte b;
}
```

<span data-ttu-id="d6cbd-111">Die zwei Ganzzahlfelder `i1` und `i2` teilen die gleichen Speicheradressen wie `lg`.</span><span class="sxs-lookup"><span data-stu-id="d6cbd-111">The two integer fields, `i1` and `i2`, share the same memory locations as `lg`.</span></span> <span data-ttu-id="d6cbd-112">Diese Art der Kontrolle über das Strukturlayout ist nützlich, wenn Sie Plattformaufrufe nutzen.</span><span class="sxs-lookup"><span data-stu-id="d6cbd-112">This sort of control over struct layout is useful when using platform invocation.</span></span>

## <a name="see-also"></a><span data-ttu-id="d6cbd-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d6cbd-113">See also</span></span>

- <xref:System.Reflection>
- <xref:System.Attribute>
- [<span data-ttu-id="d6cbd-114">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="d6cbd-114">C# Programming Guide</span></span>](../../index.md)
- [<span data-ttu-id="d6cbd-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="d6cbd-115">Attributes</span></span>](../../../../standard/attributes/index.md)
- [<span data-ttu-id="d6cbd-116">Reflektion (C#)</span><span class="sxs-lookup"><span data-stu-id="d6cbd-116">Reflection (C#)</span></span>](../reflection.md)
- [<span data-ttu-id="d6cbd-117">Attribute (C#)</span><span class="sxs-lookup"><span data-stu-id="d6cbd-117">Attributes (C#)</span></span>](index.md)
- [<span data-ttu-id="d6cbd-118">Erstellen benutzerdefinierter Attribute (C#)</span><span class="sxs-lookup"><span data-stu-id="d6cbd-118">Creating Custom Attributes (C#)</span></span>](creating-custom-attributes.md)
- [<span data-ttu-id="d6cbd-119">Accessing Attributes by Using Reflection (C#) (Zugriff auf Attribute mit Reflektion (C#))</span><span class="sxs-lookup"><span data-stu-id="d6cbd-119">Accessing Attributes by Using Reflection (C#)</span></span>](accessing-attributes-by-using-reflection.md)
