---
title: Ausführliche Syntax (F#)
description: Erläutert den Unterschied zwischen ausführliche und einfache Syntax in der Programmiersprache f#.
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: fd040a66a789bc6717fd14e6a9f28274c9e3542b
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="verbose-syntax"></a><span data-ttu-id="ef720-103">Ausführliche Syntax</span><span class="sxs-lookup"><span data-stu-id="ef720-103">Verbose Syntax</span></span>

<span data-ttu-id="ef720-104">Es gibt zwei Formen der Syntax für viele Konstrukte der Programmiersprache f# verfügbar: *ausführliche Syntax* und *einfache Syntax*.</span><span class="sxs-lookup"><span data-stu-id="ef720-104">There are two forms of syntax available for many constructs in the F# language: *verbose syntax* and *lightweight syntax*.</span></span> <span data-ttu-id="ef720-105">Die ausführliche Syntax ist nicht so häufig verwendet, aber hat den Vorteil, dass weniger empfindlich gegenüber Einzug.</span><span class="sxs-lookup"><span data-stu-id="ef720-105">The verbose syntax is not as commonly used, but has the advantage of being less sensitive to indentation.</span></span> <span data-ttu-id="ef720-106">Die einfache Syntax ist kürzer und Einzug verwendet, um Anfang und Ende von Konstrukten zu signalisieren, anstatt zusätzliche Schlüsselwörter wie `begin`, `end`, `in`und so weiter.</span><span class="sxs-lookup"><span data-stu-id="ef720-106">The lightweight syntax is shorter and uses indentation to signal the beginning and end of constructs, rather than additional keywords like `begin`, `end`, `in`, and so on.</span></span> <span data-ttu-id="ef720-107">Standardmäßig ist die einfache Syntax.</span><span class="sxs-lookup"><span data-stu-id="ef720-107">The default syntax is the lightweight syntax.</span></span> <span data-ttu-id="ef720-108">Dieses Thema beschreibt die Syntax für F#-Konstrukte, wenn einfacher Syntax nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="ef720-108">This topic describes the syntax for F# constructs when lightweight syntax is not enabled.</span></span> <span data-ttu-id="ef720-109">Ausführlicher Syntax ist immer aktiviert, damit auch, wenn Sie einfachen Syntax aktiviert haben, können Sie ausführlichen Syntax für einigen Konstrukten weiterhin verwenden.</span><span class="sxs-lookup"><span data-stu-id="ef720-109">Verbose syntax is always enabled, so even if you enable lightweight syntax, you can still use verbose syntax for some constructs.</span></span> <span data-ttu-id="ef720-110">Sie können einfachen Syntax deaktivieren, indem Sie mit der `#light "off"` Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="ef720-110">You can disable lightweight syntax by using the `#light "off"` directive.</span></span>


## <a name="table-of-constructs"></a><span data-ttu-id="ef720-111">Tabelle von Konstrukten</span><span class="sxs-lookup"><span data-stu-id="ef720-111">Table of Constructs</span></span>
<span data-ttu-id="ef720-112">Die folgende Tabelle zeigt die einfache und ausführliche Syntax für f#-Sprachkonstrukte in Kontexten besteht ein Unterschied zwischen den beiden Formaten.</span><span class="sxs-lookup"><span data-stu-id="ef720-112">The following table shows the lightweight and verbose syntax for F# language constructs in contexts where there is a difference between the two forms.</span></span> <span data-ttu-id="ef720-113">In dieser Tabelle spitze Klammern (&lt;&gt;) schließen Sie benutzerdefinierte Syntaxelemente.</span><span class="sxs-lookup"><span data-stu-id="ef720-113">In this table, angle brackets (&lt;&gt;) enclose user-supplied syntax elements.</span></span> <span data-ttu-id="ef720-114">Finden Sie in der Dokumentation für jede Sprachkonstrukt Weitere ausführliche Informationen zur Syntax, die innerhalb dieser Konstrukte verwendet.</span><span class="sxs-lookup"><span data-stu-id="ef720-114">Refer to the documentation for each language construct for more detailed information about the syntax used within these constructs.</span></span>



<table>
<tr>
<th><span data-ttu-id="ef720-115">Sprachkonstrukt</span><span class="sxs-lookup"><span data-stu-id="ef720-115">Language construct</span></span></th>
<th><span data-ttu-id="ef720-116">Einfache syntax</span><span class="sxs-lookup"><span data-stu-id="ef720-116">Lightweight syntax</span></span></th>
<th><span data-ttu-id="ef720-117">Ausführliche syntax</span><span class="sxs-lookup"><span data-stu-id="ef720-117">Verbose syntax</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="ef720-118">zusammengesetzte Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="ef720-118">compound expressions</span></span>
</td>
<td>

```xml
<expression1>
<expression2>
```
</td><td>

```
<expression1>; <expression2>
```

</td>
</tr>
<tr><td>


<span data-ttu-id="ef720-119">geschachtelte `let` Bindungen</span><span class="sxs-lookup"><span data-stu-id="ef720-119">nested `let` bindings</span></span>

</td><td>
```
let f x =
    let a = 1
    let b = 2
    x + a + b
```

</td><td>

```
let f x =
    let a = 1 in
    let b = 2 in
    x + a + b
```

</td>
</tr>
<tr><td>
<span data-ttu-id="ef720-120">Code-block</span><span class="sxs-lookup"><span data-stu-id="ef720-120">code block</span></span>
</td><td>

```
(
    <expression1>
    <expression2>
)
```

</td><td>

```
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

```
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

```
while <condition> do
    ...
```

</td><td>

```
while <condition> do
    ...
done
```

</td>
</tr>
<tr><td>
`for...in`
</td><td>

```
for var in start .. finish do
    ...
```

</td><td>

```
for var in start .. finish do
    ...
done
```

</td>
</tr>
<tr><td>
`do`
</td><td>

```
do
    ...
```

</td><td>

```
do
    ...
in
```

</td>
</tr>
<tr><td><span data-ttu-id="ef720-121">record</span><span class="sxs-lookup"><span data-stu-id="ef720-121">record</span></span>
</td><td>

```
type <record-name> =
    {
        <field-declarations>
    }
    <value-or-member-definitions>
```

</td><td>

```
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
<tr><td><span data-ttu-id="ef720-122">Klasse</span><span class="sxs-lookup"><span data-stu-id="ef720-122">class</span></span>
</td><td><span data-ttu-id="ef720-123">
```
type <class-name>(<params>) = ... ```

</span><span class="sxs-lookup"><span data-stu-id="ef720-123">
```
type <class-name>(<params>) = ... ```

</span></span></td><td>

```
type <class-name>(<params>) =
    class
        ...
    end
```
</td>
</tr>
<tr><td><span data-ttu-id="ef720-124">Struktur</span><span class="sxs-lookup"><span data-stu-id="ef720-124">structure</span></span></td><td>

```
[<StructAttribute>]
type <structure-name> =
    ...
```
</td><td>

```
type <structure-name> =
    struct
        ...
    end
```

</td>
</tr>
<tr><td><span data-ttu-id="ef720-125">Unterscheidungs-union</span><span class="sxs-lookup"><span data-stu-id="ef720-125">discriminated union</span></span></td><td>

```
type <union-name> =
    | ...
    | ...
    ...
    <value-or-member definitions>
```
</td><td>

```
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
<tr><td><span data-ttu-id="ef720-126">interface</span><span class="sxs-lookup"><span data-stu-id="ef720-126">interface</span></span></td><td>

```
type <interface-name> =
    ...
```
</td><td>

```
type <interface-name> =
    interface
        ...
    end
```

</td>
</tr>
<tr><td><span data-ttu-id="ef720-127">Object-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="ef720-127">object expression</span></span></td><td>

```
{ new <type-name>
    with
        <value-or-member-definitions>
        <interface-implementations>
}
```

</td><td>

```
{ new <type-name>
    with
        <value-or-member-definitions>
    end
    <interface-implementations>
}
```

</td>
</tr>
<tr><td><span data-ttu-id="ef720-128">Schnittstellenimplementierung</span><span class="sxs-lookup"><span data-stu-id="ef720-128">interface implementation</span></span></td><td>

```
interface <interface-name>
    with
        <value-or-member-definitions>
```

</td><td>

```
interface <interface-name>
    with
        <value-or-member-definitions>
    end
```

</td>
</tr>
<tr><td><span data-ttu-id="ef720-129">typerweiterung</span><span class="sxs-lookup"><span data-stu-id="ef720-129">type extension</span></span></td><td>

```
type <type-name>
    with
        <value-or-member-definitions>
```

</td><td>

```
type <type-name>
    with
        <value-or-member-definitions>
    end
```

</td>
</tr>
<tr><td><span data-ttu-id="ef720-130">module</span><span class="sxs-lookup"><span data-stu-id="ef720-130">module</span></span></td><td>

```
module <module-name> =
    ...
```

</td><td>

```
module <module-name> =
    begin
        ...
    end
```

</td>
</tr>
</table>



## <a name="see-also"></a><span data-ttu-id="ef720-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ef720-131">See Also</span></span>
[<span data-ttu-id="ef720-132">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="ef720-132">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="ef720-133">Compileranweisungen</span><span class="sxs-lookup"><span data-stu-id="ef720-133">Compiler Directives</span></span>](compiler-directives.md)

[<span data-ttu-id="ef720-134">Richtlinien für das Formatieren von Code</span><span class="sxs-lookup"><span data-stu-id="ef720-134">Code Formatting Guidelines</span></span>](code-formatting-guidelines.md)
