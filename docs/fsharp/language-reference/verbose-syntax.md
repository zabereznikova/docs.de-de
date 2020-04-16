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
# <a name="verbose-syntax"></a>Ausführliche Syntax

Für viele Konstrukte in der Sprache F- stehen zwei Syntaxformen zur Verfügung: *ausführliche Syntax* und *Lightweight-Syntax*. Die ausführliche Syntax wird nicht so häufig verwendet, hat aber den Vorteil, dass sie weniger empfindlich auf Einzug reagiert. Die lightweight Syntax ist kürzer und verwendet Einzug, um den Anfang und das `begin` `end`Ende `in`von Konstrukten zu signalisieren, anstatt zusätzliche Schlüsselwörter wie , , , usw. Die Standardsyntax ist die lightweight Syntax. In diesem Thema wird die Syntax für F-Konstrukte beschrieben, wenn die lightweight Syntax nicht aktiviert ist. Die ausführliche Syntax ist immer aktiviert, sodass Sie selbst dann, wenn Sie eine einfache Syntax aktivieren, für einige Konstrukte weiterhin ausführliche Syntax verwenden können. Sie können die Lightweight-Syntax mithilfe der `#light "off"` Direktive deaktivieren.

## <a name="table-of-constructs"></a>Tabelle der Konstrukte

Die folgende Tabelle zeigt die einfache und ausführliche Syntax für F-Sprachkonstrukte in Kontexten, in denen ein Unterschied zwischen den beiden Formularen besteht. In dieser Tabelle schließen&lt;&gt;spitze Klammern ( ) vom Benutzer bereitgestellte Syntaxelemente ein. Ausführlichere Informationen zur Syntax, die in diesen Konstrukten verwendet wird, finden Sie in der Dokumentation für jedes Sprachkonstrukt.

<table>
<tr>
<th>Sprachkonstrukt</th>
<th>Leichte Syntax</th>
<th>Verbose Syntax</th>
</tr>
<tr>
<td>
Zusammengesetzte Ausdrücke
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

verschachtelte `let` Bindungen

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
<tr><td>diskriminierte Gewerkschaft</td><td>

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
<tr><td>Objektausdruck</td><td>

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

- [Sprachreferenz](index.md)
- [Compileranweisungen](compiler-directives.md)
- [Richtlinien für das Formatieren von Code](../style-guide/formatting.md)
