---
title: Ausführliche Syntax
description: 'Informieren Sie sich über den Unterschied zwischen ausführlicher und schlanker Syntax in der Programmiersprache F #.'
ms.date: 05/16/2016
ms.openlocfilehash: 4e1725b58c8cb67c074ba12fd4ca25ce0c000a1e
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/16/2020
ms.locfileid: "97595176"
---
# <a name="verbose-syntax"></a>Ausführliche Syntax

Es gibt zwei Arten von Syntax für viele Konstrukte in der Programmiersprache F #: Ausführliche *Syntax* und *Lightweight-Syntax*. Die ausführliche Syntax wird nicht wie üblich verwendet, hat jedoch den Vorteil, dass der Einzug weniger sensibel ist. Die Lightweight-Syntax ist kürzer und verwendet Einzüge, um den Anfang und das Ende der Konstrukte zu signalisieren, anstatt zusätzliche Schlüsselwörter wie `begin` , `end` , `in` usw. Die Standard Syntax ist die Lightweight-Syntax. In diesem Thema wird die Syntax für F #-Konstrukte beschrieben, wenn die Lightweight-Syntax nicht aktiviert ist. Die ausführliche Syntax ist immer aktiviert. auch wenn Sie die Lightweight-Syntax aktivieren, können Sie für einige Konstrukte weiterhin ausführliche Syntax verwenden. Sie können die Lightweight-Syntax deaktivieren, indem Sie die- `#light "off"` Anweisung verwenden.

## <a name="table-of-constructs"></a>Tabelle der Konstrukte

Die folgende Tabelle zeigt die ausführliche und ausführliche Syntax für F #-Sprachkonstrukte in Kontexten, in denen es einen Unterschied zwischen den beiden Formen gibt. In dieser Tabelle schließen eckige Klammern () die vom &lt; &gt; Benutzer bereitgestellten Syntax Elemente ein. Ausführlichere Informationen zur Syntax, die in diesen Konstrukten verwendet wird, finden Sie in der Dokumentation zu den einzelnen sprach Konstrukten.

<table>
<tr>
<th>Sprachkonstrukt</th>
<th>Lightweight-Syntax</th>
<th>Ausführliche Syntax</th>
</tr>
<tr>
<td>
Verbund Ausdrücke
</td>
<td>

```fsharp
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

Zuordnungs `let` Bindungen

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
<tr><td>Datensatz (record)
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
<tr><td>class
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
<tr><td>structure</td><td>

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
<tr><td>Unterscheidungs-Union</td><td>

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
<tr><td>Objekt Ausdruck</td><td>

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
<tr><td>Typerweiterung</td><td>

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

## <a name="see-also"></a>Weitere Informationen

- [F#-Sprachreferenz](index.md)
- [Compileranweisungen](compiler-directives.md)
- [Richtlinien für das Formatieren von Code](../style-guide/formatting.md)
