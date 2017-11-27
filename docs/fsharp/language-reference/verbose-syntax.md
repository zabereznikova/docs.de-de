---
title: "Ausführliche Syntax (F#)"
description: "Erläutert den Unterschied zwischen ausführliche und einfache Syntax in der Programmiersprache f#."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 0a6792b3-b312-4453-a025-21d9760eee5d
ms.openlocfilehash: 2cef359a879897825733a3186be97b38896f5953
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="verbose-syntax"></a><span data-ttu-id="acce2-104">Ausführliche Syntax</span><span class="sxs-lookup"><span data-stu-id="acce2-104">Verbose Syntax</span></span>

<span data-ttu-id="acce2-105">Es gibt zwei Formen der Syntax für viele Konstrukte der Programmiersprache f# verfügbar: *ausführliche Syntax* und *einfache Syntax*.</span><span class="sxs-lookup"><span data-stu-id="acce2-105">There are two forms of syntax available for many constructs in the F# language: *verbose syntax* and *lightweight syntax*.</span></span> <span data-ttu-id="acce2-106">Die ausführliche Syntax ist nicht so häufig verwendet, aber hat den Vorteil, dass weniger empfindlich gegenüber Einzug.</span><span class="sxs-lookup"><span data-stu-id="acce2-106">The verbose syntax is not as commonly used, but has the advantage of being less sensitive to indentation.</span></span> <span data-ttu-id="acce2-107">Die einfache Syntax ist kürzer und Einzug verwendet, um Anfang und Ende von Konstrukten zu signalisieren, anstatt zusätzliche Schlüsselwörter wie `begin`, `end`, `in`und so weiter.</span><span class="sxs-lookup"><span data-stu-id="acce2-107">The lightweight syntax is shorter and uses indentation to signal the beginning and end of constructs, rather than additional keywords like `begin`, `end`, `in`, and so on.</span></span> <span data-ttu-id="acce2-108">Standardmäßig ist die einfache Syntax.</span><span class="sxs-lookup"><span data-stu-id="acce2-108">The default syntax is the lightweight syntax.</span></span> <span data-ttu-id="acce2-109">Dieses Thema beschreibt die Syntax für F#-Konstrukte, wenn einfacher Syntax nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="acce2-109">This topic describes the syntax for F# constructs when lightweight syntax is not enabled.</span></span> <span data-ttu-id="acce2-110">Ausführlicher Syntax ist immer aktiviert, damit auch, wenn Sie einfachen Syntax aktiviert haben, können Sie ausführlichen Syntax für einigen Konstrukten weiterhin verwenden.</span><span class="sxs-lookup"><span data-stu-id="acce2-110">Verbose syntax is always enabled, so even if you enable lightweight syntax, you can still use verbose syntax for some constructs.</span></span> <span data-ttu-id="acce2-111">Sie können einfachen Syntax deaktivieren, indem Sie mit der `#light "off"` Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="acce2-111">You can disable lightweight syntax by using the `#light "off"` directive.</span></span>


## <a name="table-of-constructs"></a><span data-ttu-id="acce2-112">Tabelle von Konstrukten</span><span class="sxs-lookup"><span data-stu-id="acce2-112">Table of Constructs</span></span>
<span data-ttu-id="acce2-113">Die folgende Tabelle zeigt die einfache und ausführliche Syntax für f#-Sprachkonstrukte in Kontexten besteht ein Unterschied zwischen den beiden Formaten.</span><span class="sxs-lookup"><span data-stu-id="acce2-113">The following table shows the lightweight and verbose syntax for F# language constructs in contexts where there is a difference between the two forms.</span></span> <span data-ttu-id="acce2-114">In dieser Tabelle spitze Klammern (&lt;&gt;) schließen Sie benutzerdefinierte Syntaxelemente.</span><span class="sxs-lookup"><span data-stu-id="acce2-114">In this table, angle brackets (&lt;&gt;) enclose user-supplied syntax elements.</span></span> <span data-ttu-id="acce2-115">Finden Sie in der Dokumentation für jede Sprachkonstrukt Weitere ausführliche Informationen zur Syntax, die innerhalb dieser Konstrukte verwendet.</span><span class="sxs-lookup"><span data-stu-id="acce2-115">Refer to the documentation for each language construct for more detailed information about the syntax used within these constructs.</span></span>



<table>
<tr>
<th><span data-ttu-id="acce2-116">Sprachkonstrukt</span><span class="sxs-lookup"><span data-stu-id="acce2-116">Language construct</span></span></th>
<th><span data-ttu-id="acce2-117">Einfache syntax</span><span class="sxs-lookup"><span data-stu-id="acce2-117">Lightweight syntax</span></span></th>
<th><span data-ttu-id="acce2-118">Ausführliche syntax</span><span class="sxs-lookup"><span data-stu-id="acce2-118">Verbose syntax</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="acce2-119">zusammengesetzte Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="acce2-119">compound expressions</span></span>
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


<span data-ttu-id="acce2-120">geschachtelte `let` Bindungen</span><span class="sxs-lookup"><span data-stu-id="acce2-120">nested `let` bindings</span></span>

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
<span data-ttu-id="acce2-121">Code-block</span><span class="sxs-lookup"><span data-stu-id="acce2-121">code block</span></span>
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
<tr><td><span data-ttu-id="acce2-122">record</span><span class="sxs-lookup"><span data-stu-id="acce2-122">record</span></span>
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
<tr><td><span data-ttu-id="acce2-123">Klasse</span><span class="sxs-lookup"><span data-stu-id="acce2-123">class</span></span>
</td><td><span data-ttu-id="acce2-124">
```
type <class-name>(<params>) = ... ```

</span><span class="sxs-lookup"><span data-stu-id="acce2-124">
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
<tr><td><span data-ttu-id="acce2-125">Struktur</span><span class="sxs-lookup"><span data-stu-id="acce2-125">structure</span></span></td><td>

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
<tr><td><span data-ttu-id="acce2-126">Unterscheidungs-union</span><span class="sxs-lookup"><span data-stu-id="acce2-126">discriminated union</span></span></td><td>

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
<tr><td><span data-ttu-id="acce2-127">interface</span><span class="sxs-lookup"><span data-stu-id="acce2-127">interface</span></span></td><td>

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
<tr><td><span data-ttu-id="acce2-128">Object-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="acce2-128">object expression</span></span></td><td>

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
<tr><td><span data-ttu-id="acce2-129">Schnittstellenimplementierung</span><span class="sxs-lookup"><span data-stu-id="acce2-129">interface implementation</span></span></td><td>

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
<tr><td><span data-ttu-id="acce2-130">typerweiterung</span><span class="sxs-lookup"><span data-stu-id="acce2-130">type extension</span></span></td><td>

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
<tr><td><span data-ttu-id="acce2-131">module</span><span class="sxs-lookup"><span data-stu-id="acce2-131">module</span></span></td><td>

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



## <a name="see-also"></a><span data-ttu-id="acce2-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="acce2-132">See Also</span></span>
[<span data-ttu-id="acce2-133">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="acce2-133">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="acce2-134">Compileranweisungen</span><span class="sxs-lookup"><span data-stu-id="acce2-134">Compiler Directives</span></span>](compiler-directives.md)

[<span data-ttu-id="acce2-135">Richtlinien für das Formatieren von Code</span><span class="sxs-lookup"><span data-stu-id="acce2-135">Code Formatting Guidelines</span></span>](code-formatting-guidelines.md)
