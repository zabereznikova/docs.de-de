---
title: Ausführliche Syntax
description: Erfahren Sie, den Unterschied zwischen ausführliche und einfache Syntax in der Programmiersprache F#.
ms.date: 05/16/2016
ms.openlocfilehash: c770f2843276619cb2878198a537dcfb9c054b6b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61902303"
---
# <a name="verbose-syntax"></a>Ausführliche Syntax

Es gibt zwei Formen der Syntax für viele Konstrukte in F# verfügbar: *ausführliche Syntax* und *einfache Syntax*. Die ausführliche Syntax ist nicht so häufig verwendet, aber Sie hat den Vorteil, dass weniger anfällig für den Einzug. Die einfache Syntax ist kürzer und Einzüge verwendet, um Anfang und Ende von Konstrukten zu signalisieren, anstatt zusätzliche Schlüsselwörter wie `begin`, `end`, `in`und so weiter. Standardmäßig ist die einfache Syntax. Dieses Thema beschreibt die Syntax für F#-Konstrukte, wenn die einfacher Syntax nicht aktiviert ist. Ausführlicher Syntax ist immer aktiviert, sodass auch, wenn Sie einfachen Syntax aktiviert haben, können Sie ausführlichen Syntax für einige Konstrukte weiterhin verwenden. Sie können einfachen Syntax deaktivieren, indem Sie mit der `#light "off"` Richtlinie.

## <a name="table-of-constructs"></a>Tabelle der Konstrukte

Die folgende Tabelle zeigt die einfache und ausführliche Syntax für F# Sprachkonstrukte in Kontexten, ein Unterschied zwischen den beiden Formaten besteht. In dieser Tabelle spitze Klammern (&lt;&gt;) schließen Sie die benutzerdefinierte Syntaxelemente. Finden Sie in der Dokumentation für jede Sprachkonstrukt Weitere ausführliche Informationen zur Syntax, die innerhalb dieser Konstrukte verwendet.

<table>
<tr>
<th>Sprachkonstrukt</th>
<th>Einfache syntax</th>
<th>Ausführliche syntax</th>
</tr>
<tr>
<td>
zusammengesetzte Ausdrücke
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

geschachtelte `let` Bindungen

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
Codeblock
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
<tr><td>record
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
<tr><td>Klasse
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
<tr><td>Struktur</td><td>

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
<tr><td>Unterscheidungs-union</td><td>

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
<tr><td>interface</td><td>

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
<tr><td>Object-Ausdruck</td><td>

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
<tr><td>Schnittstellenimplementierung</td><td>

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
<tr><td>typerweiterung</td><td>

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
<tr><td>module</td><td>

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

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
- [Compileranweisungen](compiler-directives.md)
- [Richtlinien für das Formatieren von Code](code-formatting-guidelines.md)