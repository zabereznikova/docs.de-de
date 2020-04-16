---
title: Ausführliche Syntax
description: Lernen Sie den Unterschied zwischen ausführlicher und leichter Syntax in der Programmiersprache F-Programmiersprache.
ms.date: 05/16/2016
ms.openlocfilehash: 722807695c56beb0d681b95a78ed8cb8c1df3ddf
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463908"
---
# <a name="verbose-syntax"></a><span data-ttu-id="30608-103">Ausführliche Syntax</span><span class="sxs-lookup"><span data-stu-id="30608-103">Verbose Syntax</span></span>

<span data-ttu-id="30608-104">Für viele Konstrukte in der Sprache F- stehen zwei Syntaxformen zur Verfügung: *ausführliche Syntax* und *Lightweight-Syntax*.</span><span class="sxs-lookup"><span data-stu-id="30608-104">There are two forms of syntax available for many constructs in the F# language: *verbose syntax* and *lightweight syntax*.</span></span> <span data-ttu-id="30608-105">Die ausführliche Syntax wird nicht so häufig verwendet, hat aber den Vorteil, dass sie weniger empfindlich auf Einzug reagiert.</span><span class="sxs-lookup"><span data-stu-id="30608-105">The verbose syntax is not as commonly used, but has the advantage of being less sensitive to indentation.</span></span> <span data-ttu-id="30608-106">Die lightweight Syntax ist kürzer und verwendet Einzug, um den Anfang und das `begin` `end`Ende `in`von Konstrukten zu signalisieren, anstatt zusätzliche Schlüsselwörter wie , , , usw.</span><span class="sxs-lookup"><span data-stu-id="30608-106">The lightweight syntax is shorter and uses indentation to signal the beginning and end of constructs, rather than additional keywords like `begin`, `end`, `in`, and so on.</span></span> <span data-ttu-id="30608-107">Die Standardsyntax ist die lightweight Syntax.</span><span class="sxs-lookup"><span data-stu-id="30608-107">The default syntax is the lightweight syntax.</span></span> <span data-ttu-id="30608-108">In diesem Thema wird die Syntax für F-Konstrukte beschrieben, wenn die lightweight Syntax nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="30608-108">This topic describes the syntax for F# constructs when lightweight syntax is not enabled.</span></span> <span data-ttu-id="30608-109">Die ausführliche Syntax ist immer aktiviert, sodass Sie selbst dann, wenn Sie eine einfache Syntax aktivieren, für einige Konstrukte weiterhin ausführliche Syntax verwenden können.</span><span class="sxs-lookup"><span data-stu-id="30608-109">Verbose syntax is always enabled, so even if you enable lightweight syntax, you can still use verbose syntax for some constructs.</span></span> <span data-ttu-id="30608-110">Sie können die Lightweight-Syntax mithilfe der `#light "off"` Direktive deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="30608-110">You can disable lightweight syntax by using the `#light "off"` directive.</span></span>

## <a name="table-of-constructs"></a><span data-ttu-id="30608-111">Tabelle der Konstrukte</span><span class="sxs-lookup"><span data-stu-id="30608-111">Table of Constructs</span></span>

<span data-ttu-id="30608-112">Die folgende Tabelle zeigt die einfache und ausführliche Syntax für F-Sprachkonstrukte in Kontexten, in denen ein Unterschied zwischen den beiden Formularen besteht.</span><span class="sxs-lookup"><span data-stu-id="30608-112">The following table shows the lightweight and verbose syntax for F# language constructs in contexts where there is a difference between the two forms.</span></span> <span data-ttu-id="30608-113">In dieser Tabelle schließen&lt;&gt;spitze Klammern ( ) vom Benutzer bereitgestellte Syntaxelemente ein.</span><span class="sxs-lookup"><span data-stu-id="30608-113">In this table, angle brackets (&lt;&gt;) enclose user-supplied syntax elements.</span></span> <span data-ttu-id="30608-114">Ausführlichere Informationen zur Syntax, die in diesen Konstrukten verwendet wird, finden Sie in der Dokumentation für jedes Sprachkonstrukt.</span><span class="sxs-lookup"><span data-stu-id="30608-114">Refer to the documentation for each language construct for more detailed information about the syntax used within these constructs.</span></span>

<table>
<tr>
<th><span data-ttu-id="30608-115">Sprachkonstrukt</span><span class="sxs-lookup"><span data-stu-id="30608-115">Language construct</span></span></th>
<th><span data-ttu-id="30608-116">Leichte Syntax</span><span class="sxs-lookup"><span data-stu-id="30608-116">Lightweight syntax</span></span></th>
<th><span data-ttu-id="30608-117">Verbose Syntax</span><span class="sxs-lookup"><span data-stu-id="30608-117">Verbose syntax</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="30608-118">Zusammengesetzte Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="30608-118">compound expressions</span></span>
</td>
<td>

```xml
<expression1 />
<expression2 />
```

</td><td>

```fsharp
<expression1>; <expression2>
```

</td>
</tr>
<tr><td>

<span data-ttu-id="30608-119">verschachtelte `let` Bindungen</span><span class="sxs-lookup"><span data-stu-id="30608-119">nested `let` bindings</span></span>

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
<span data-ttu-id="30608-120">Codeblock</span><span class="sxs-lookup"><span data-stu-id="30608-120">code block</span></span>
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
<tr><td><span data-ttu-id="30608-121">Datensatz (record)</span><span class="sxs-lookup"><span data-stu-id="30608-121">record</span></span>
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
<tr><td><span data-ttu-id="30608-122">class</span><span class="sxs-lookup"><span data-stu-id="30608-122">class</span></span>
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
<tr><td><span data-ttu-id="30608-123">structure</span><span class="sxs-lookup"><span data-stu-id="30608-123">structure</span></span></td><td>

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
<tr><td><span data-ttu-id="30608-124">diskriminierte Gewerkschaft</span><span class="sxs-lookup"><span data-stu-id="30608-124">discriminated union</span></span></td><td>

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
<tr><td><span data-ttu-id="30608-125">interface</span><span class="sxs-lookup"><span data-stu-id="30608-125">interface</span></span></td><td>

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
<tr><td><span data-ttu-id="30608-126">Objektausdruck</span><span class="sxs-lookup"><span data-stu-id="30608-126">object expression</span></span></td><td>

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
<tr><td><span data-ttu-id="30608-127">Schnittstellenimplementierung</span><span class="sxs-lookup"><span data-stu-id="30608-127">interface implementation</span></span></td><td>

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
<tr><td><span data-ttu-id="30608-128">Typerweiterung</span><span class="sxs-lookup"><span data-stu-id="30608-128">type extension</span></span></td><td>

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
<tr><td><span data-ttu-id="30608-129">module</span><span class="sxs-lookup"><span data-stu-id="30608-129">module</span></span></td><td>

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

## <a name="see-also"></a><span data-ttu-id="30608-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="30608-130">See also</span></span>

- [<span data-ttu-id="30608-131">Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="30608-131">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="30608-132">Compileranweisungen</span><span class="sxs-lookup"><span data-stu-id="30608-132">Compiler Directives</span></span>](compiler-directives.md)
- [<span data-ttu-id="30608-133">Richtlinien für das Formatieren von Code</span><span class="sxs-lookup"><span data-stu-id="30608-133">Code Formatting Guidelines</span></span>](../style-guide/formatting.md)
