---
title: Ausführliche Syntax (F#)
description: Erfahren Sie, den Unterschied zwischen ausführliche und einfache Syntax in der Programmiersprache f#.
ms.date: 05/16/2016
ms.openlocfilehash: e697c6fe619df7ffe12f7d4e2a234a5a5cb401ff
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50044762"
---
# <a name="verbose-syntax"></a><span data-ttu-id="beb57-103">Ausführliche Syntax</span><span class="sxs-lookup"><span data-stu-id="beb57-103">Verbose Syntax</span></span>

<span data-ttu-id="beb57-104">Es gibt zwei Formen der Syntax für viele Konstrukte in f# verfügbar: *ausführliche Syntax* und *einfache Syntax*.</span><span class="sxs-lookup"><span data-stu-id="beb57-104">There are two forms of syntax available for many constructs in the F# language: *verbose syntax* and *lightweight syntax*.</span></span> <span data-ttu-id="beb57-105">Die ausführliche Syntax ist nicht so häufig verwendet, aber Sie hat den Vorteil, dass weniger anfällig für den Einzug.</span><span class="sxs-lookup"><span data-stu-id="beb57-105">The verbose syntax is not as commonly used, but has the advantage of being less sensitive to indentation.</span></span> <span data-ttu-id="beb57-106">Die einfache Syntax ist kürzer und Einzüge verwendet, um Anfang und Ende von Konstrukten zu signalisieren, anstatt zusätzliche Schlüsselwörter wie `begin`, `end`, `in`und so weiter.</span><span class="sxs-lookup"><span data-stu-id="beb57-106">The lightweight syntax is shorter and uses indentation to signal the beginning and end of constructs, rather than additional keywords like `begin`, `end`, `in`, and so on.</span></span> <span data-ttu-id="beb57-107">Standardmäßig ist die einfache Syntax.</span><span class="sxs-lookup"><span data-stu-id="beb57-107">The default syntax is the lightweight syntax.</span></span> <span data-ttu-id="beb57-108">Dieses Thema beschreibt die Syntax für f#-Konstrukte, wenn die einfacher Syntax nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="beb57-108">This topic describes the syntax for F# constructs when lightweight syntax is not enabled.</span></span> <span data-ttu-id="beb57-109">Ausführlicher Syntax ist immer aktiviert, sodass auch, wenn Sie einfachen Syntax aktiviert haben, können Sie ausführlichen Syntax für einige Konstrukte weiterhin verwenden.</span><span class="sxs-lookup"><span data-stu-id="beb57-109">Verbose syntax is always enabled, so even if you enable lightweight syntax, you can still use verbose syntax for some constructs.</span></span> <span data-ttu-id="beb57-110">Sie können einfachen Syntax deaktivieren, indem Sie mit der `#light "off"` Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="beb57-110">You can disable lightweight syntax by using the `#light "off"` directive.</span></span>

## <a name="table-of-constructs"></a><span data-ttu-id="beb57-111">Tabelle der Konstrukte</span><span class="sxs-lookup"><span data-stu-id="beb57-111">Table of Constructs</span></span>

<span data-ttu-id="beb57-112">Die folgende Tabelle zeigt die einfache und ausführliche Syntax für F#-Konstrukte in Kontexten, ein Unterschied zwischen den beiden Formaten besteht.</span><span class="sxs-lookup"><span data-stu-id="beb57-112">The following table shows the lightweight and verbose syntax for F# language constructs in contexts where there is a difference between the two forms.</span></span> <span data-ttu-id="beb57-113">In dieser Tabelle spitze Klammern (&lt;&gt;) schließen Sie die benutzerdefinierte Syntaxelemente.</span><span class="sxs-lookup"><span data-stu-id="beb57-113">In this table, angle brackets (&lt;&gt;) enclose user-supplied syntax elements.</span></span> <span data-ttu-id="beb57-114">Finden Sie in der Dokumentation für jede Sprachkonstrukt Weitere ausführliche Informationen zur Syntax, die innerhalb dieser Konstrukte verwendet.</span><span class="sxs-lookup"><span data-stu-id="beb57-114">Refer to the documentation for each language construct for more detailed information about the syntax used within these constructs.</span></span>

<table>
<tr>
<th><span data-ttu-id="beb57-115">Sprachkonstrukt</span><span class="sxs-lookup"><span data-stu-id="beb57-115">Language construct</span></span></th>
<th><span data-ttu-id="beb57-116">Einfache syntax</span><span class="sxs-lookup"><span data-stu-id="beb57-116">Lightweight syntax</span></span></th>
<th><span data-ttu-id="beb57-117">Ausführliche syntax</span><span class="sxs-lookup"><span data-stu-id="beb57-117">Verbose syntax</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="beb57-118">zusammengesetzte Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="beb57-118">compound expressions</span></span>
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

<span data-ttu-id="beb57-119">geschachtelte `let` Bindungen</span><span class="sxs-lookup"><span data-stu-id="beb57-119">nested `let` bindings</span></span>

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
<span data-ttu-id="beb57-120">Codeblock</span><span class="sxs-lookup"><span data-stu-id="beb57-120">code block</span></span>
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

```
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
<tr><td><span data-ttu-id="beb57-121">record</span><span class="sxs-lookup"><span data-stu-id="beb57-121">record</span></span>
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
<tr><td><span data-ttu-id="beb57-122">Klasse</span><span class="sxs-lookup"><span data-stu-id="beb57-122">class</span></span>
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
<tr><td><span data-ttu-id="beb57-123">Struktur</span><span class="sxs-lookup"><span data-stu-id="beb57-123">structure</span></span></td><td>

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
<tr><td><span data-ttu-id="beb57-124">Unterscheidungs-union</span><span class="sxs-lookup"><span data-stu-id="beb57-124">discriminated union</span></span></td><td>

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
<tr><td><span data-ttu-id="beb57-125">interface</span><span class="sxs-lookup"><span data-stu-id="beb57-125">interface</span></span></td><td>

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
<tr><td><span data-ttu-id="beb57-126">Object-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="beb57-126">object expression</span></span></td><td>

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
<tr><td><span data-ttu-id="beb57-127">Schnittstellenimplementierung</span><span class="sxs-lookup"><span data-stu-id="beb57-127">interface implementation</span></span></td><td>

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
<tr><td><span data-ttu-id="beb57-128">typerweiterung</span><span class="sxs-lookup"><span data-stu-id="beb57-128">type extension</span></span></td><td>

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
<tr><td><span data-ttu-id="beb57-129">module</span><span class="sxs-lookup"><span data-stu-id="beb57-129">module</span></span></td><td>

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

## <a name="see-also"></a><span data-ttu-id="beb57-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="beb57-130">See also</span></span>

- [<span data-ttu-id="beb57-131">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="beb57-131">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="beb57-132">Compileranweisungen</span><span class="sxs-lookup"><span data-stu-id="beb57-132">Compiler Directives</span></span>](compiler-directives.md)
- [<span data-ttu-id="beb57-133">Richtlinien für das Formatieren von Code</span><span class="sxs-lookup"><span data-stu-id="beb57-133">Code Formatting Guidelines</span></span>](code-formatting-guidelines.md)
