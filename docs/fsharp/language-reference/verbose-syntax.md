---
title: Ausführliche Syntax
description: Erfahren Sie, den Unterschied zwischen ausführliche und einfache Syntax in der Programmiersprache F#.
ms.date: 05/16/2016
ms.openlocfilehash: d2459da60bba5d88bd23615c8bf09ba64f7c22c4
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2019
ms.locfileid: "71214037"
---
# <a name="verbose-syntax"></a><span data-ttu-id="27055-103">Ausführliche Syntax</span><span class="sxs-lookup"><span data-stu-id="27055-103">Verbose Syntax</span></span>

<span data-ttu-id="27055-104">Es gibt zwei Formen der Syntax für viele Konstrukte in F# verfügbar: *ausführliche Syntax* und *einfache Syntax*.</span><span class="sxs-lookup"><span data-stu-id="27055-104">There are two forms of syntax available for many constructs in the F# language: *verbose syntax* and *lightweight syntax*.</span></span> <span data-ttu-id="27055-105">Die ausführliche Syntax wird nicht wie üblich verwendet, hat jedoch den Vorteil, dass der Einzug weniger sensibel ist.</span><span class="sxs-lookup"><span data-stu-id="27055-105">The verbose syntax is not as commonly used, but has the advantage of being less sensitive to indentation.</span></span> <span data-ttu-id="27055-106">Die Lightweight-Syntax ist kürzer und verwendet Einzüge, um den Anfang und das Ende der Konstrukte zu signalisieren, `begin`anstatt `end`zusätzliche `in`Schlüsselwörter wie,, usw.</span><span class="sxs-lookup"><span data-stu-id="27055-106">The lightweight syntax is shorter and uses indentation to signal the beginning and end of constructs, rather than additional keywords like `begin`, `end`, `in`, and so on.</span></span> <span data-ttu-id="27055-107">Die Standard Syntax ist die Lightweight-Syntax.</span><span class="sxs-lookup"><span data-stu-id="27055-107">The default syntax is the lightweight syntax.</span></span> <span data-ttu-id="27055-108">Dieses Thema beschreibt die Syntax für F#-Konstrukte, wenn die einfacher Syntax nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="27055-108">This topic describes the syntax for F# constructs when lightweight syntax is not enabled.</span></span> <span data-ttu-id="27055-109">Die ausführliche Syntax ist immer aktiviert. auch wenn Sie die Lightweight-Syntax aktivieren, können Sie für einige Konstrukte weiterhin ausführliche Syntax verwenden.</span><span class="sxs-lookup"><span data-stu-id="27055-109">Verbose syntax is always enabled, so even if you enable lightweight syntax, you can still use verbose syntax for some constructs.</span></span> <span data-ttu-id="27055-110">Sie können die Lightweight-Syntax deaktivieren, `#light "off"` indem Sie die-Anweisung verwenden.</span><span class="sxs-lookup"><span data-stu-id="27055-110">You can disable lightweight syntax by using the `#light "off"` directive.</span></span>

## <a name="table-of-constructs"></a><span data-ttu-id="27055-111">Tabelle der Konstrukte</span><span class="sxs-lookup"><span data-stu-id="27055-111">Table of Constructs</span></span>

<span data-ttu-id="27055-112">Die folgende Tabelle zeigt die ausführliche und ausführliche Syntax für F# Sprachkonstrukte in Kontexten, in denen es einen Unterschied zwischen den beiden Formularen gibt.</span><span class="sxs-lookup"><span data-stu-id="27055-112">The following table shows the lightweight and verbose syntax for F# language constructs in contexts where there is a difference between the two forms.</span></span> <span data-ttu-id="27055-113">In dieser Tabelle schließen eckige Klammern (&lt;&gt;) die vom Benutzer bereitgestellten Syntax Elemente ein.</span><span class="sxs-lookup"><span data-stu-id="27055-113">In this table, angle brackets (&lt;&gt;) enclose user-supplied syntax elements.</span></span> <span data-ttu-id="27055-114">Ausführlichere Informationen zur Syntax, die in diesen Konstrukten verwendet wird, finden Sie in der Dokumentation zu den einzelnen sprach Konstrukten.</span><span class="sxs-lookup"><span data-stu-id="27055-114">Refer to the documentation for each language construct for more detailed information about the syntax used within these constructs.</span></span>

<table>
<tr>
<th><span data-ttu-id="27055-115">Sprachkonstrukt</span><span class="sxs-lookup"><span data-stu-id="27055-115">Language construct</span></span></th>
<th><span data-ttu-id="27055-116">Lightweight-Syntax</span><span class="sxs-lookup"><span data-stu-id="27055-116">Lightweight syntax</span></span></th>
<th><span data-ttu-id="27055-117">Ausführliche Syntax</span><span class="sxs-lookup"><span data-stu-id="27055-117">Verbose syntax</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="27055-118">Verbund Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="27055-118">compound expressions</span></span>
</td>
<td>

```xml
<expression1>
<expression2>
```

</td><td>

```fsharp
<expression1>; <expression2>
```

</td>
</tr>
<tr><td>

<span data-ttu-id="27055-119">Zuordnungs `let` Bindungen</span><span class="sxs-lookup"><span data-stu-id="27055-119">nested `let` bindings</span></span>

</td><td>

```fsharp
let f x =
    let a = 1
    let b = 2
    x + a + b
```

</td><td>

```fsharp
let f x =
    let a = 1 in
    let b = 2 in
    x + a + b
```

</td>
</tr>
<tr><td>
<span data-ttu-id="27055-120">Codeblock</span><span class="sxs-lookup"><span data-stu-id="27055-120">code block</span></span>
</td><td>

```fsharp
(
    <expression1>
    <expression2>
)
```

</td><td>

```fsharp
begin
    <expression1>;
    <expression2>;
end
```

</td>
</tr>
<tr><td>
`for...do`
</td><td>

```fsharp
for counter = start to finish do
    ...
```

</td><td>

```fsharp
for counter = start to finish do
    ...
done
```

</td>
</tr>
<tr><td>
`while...do`
</td><td>

```fsharp
while <condition> do
    ...
```

</td><td>

```fsharp
while <condition> do
    ...
done
```

</td>
</tr>
<tr><td>
`for...in`
</td><td>

```fsharp
for var in start .. finish do
    ...
```

</td><td>

```fsharp
for var in start .. finish do
    ...
done
```

</td>
</tr>
<tr><td>
`do`
</td><td>

```fsharp
do
    ...
```

</td><td>

```fsharp
do
    ...
in
```

</td>
</tr>
<tr><td><span data-ttu-id="27055-121">record</span><span class="sxs-lookup"><span data-stu-id="27055-121">record</span></span>
</td><td>

```fsharp
type <record-name> =
    {
        <field-declarations>
    }
    <value-or-member-definitions>
```

</td><td>

```fsharp
type <record-name> =
    {
        <field-declarations>
    }
    with
        <value-or-member-definitions>
    end
```

</td>
</tr>
<tr><td><span data-ttu-id="27055-122">class</span><span class="sxs-lookup"><span data-stu-id="27055-122">class</span></span>
</td><td>

```fsharp
type <class-name>(<params>) =
    ...
```

</td><td>

```fsharp
type <class-name>(<params>) =
    class
        ...
    end
```

</td>
</tr>
<tr><td><span data-ttu-id="27055-123">Struktur</span><span class="sxs-lookup"><span data-stu-id="27055-123">structure</span></span></td><td>

```fsharp
[<StructAttribute>]
type <structure-name> =
    ...
```

</td><td>

```fsharp
type <structure-name> =
    struct
        ...
    end
```

</td>
</tr>
<tr><td><span data-ttu-id="27055-124">Unterscheidungs-Union</span><span class="sxs-lookup"><span data-stu-id="27055-124">discriminated union</span></span></td><td>

```fsharp
type <union-name> =
    | ...
    | ...
    ...
    <value-or-member definitions>
```

</td><td>

```fsharp
type <union-name> =
    | ...
    | ...
    ...
    with
        <value-or-member-definitions>
    end
```

</td>
</tr>
<tr><td><span data-ttu-id="27055-125">interface</span><span class="sxs-lookup"><span data-stu-id="27055-125">interface</span></span></td><td>

```fsharp
type <interface-name> =
    ...
```

</td><td>

```fsharp
type <interface-name> =
    interface
        ...
    end
```

</td>
</tr>
<tr><td><span data-ttu-id="27055-126">Objekt Ausdruck</span><span class="sxs-lookup"><span data-stu-id="27055-126">object expression</span></span></td><td>

```fsharp
{ new <type-name>
    with
        <value-or-member-definitions>
        <interface-implementations>
}
```

</td><td>

```fsharp
{ new <type-name>
    with
        <value-or-member-definitions>
    end
    <interface-implementations>
}
```

</td>
</tr>
<tr><td><span data-ttu-id="27055-127">Schnittstellenimplementierung</span><span class="sxs-lookup"><span data-stu-id="27055-127">interface implementation</span></span></td><td>

```fsharp
interface <interface-name>
    with
        <value-or-member-definitions>
```

</td><td>

```fsharp
interface <interface-name>
    with
        <value-or-member-definitions>
    end
```

</td>
</tr>
<tr><td><span data-ttu-id="27055-128">Typerweiterung</span><span class="sxs-lookup"><span data-stu-id="27055-128">type extension</span></span></td><td>

```fsharp
type <type-name>
    with
        <value-or-member-definitions>
```

</td><td>

```fsharp
type <type-name>
    with
        <value-or-member-definitions>
    end
```

</td>
</tr>
<tr><td><span data-ttu-id="27055-129">module</span><span class="sxs-lookup"><span data-stu-id="27055-129">module</span></span></td><td>

```fsharp
module <module-name> =
    ...
```

</td><td>

```fsharp
module <module-name> =
    begin
        ...
    end
```

</td>
</tr>
</table>

## <a name="see-also"></a><span data-ttu-id="27055-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="27055-130">See also</span></span>

- [<span data-ttu-id="27055-131">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="27055-131">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="27055-132">Compileranweisungen</span><span class="sxs-lookup"><span data-stu-id="27055-132">Compiler Directives</span></span>](compiler-directives.md)
- [<span data-ttu-id="27055-133">Richtlinien für das Formatieren von Code</span><span class="sxs-lookup"><span data-stu-id="27055-133">Code Formatting Guidelines</span></span>](code-formatting-guidelines.md)
