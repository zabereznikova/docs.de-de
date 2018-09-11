---
title: Ausführliche Syntax (F#)
description: Erfahren Sie, den Unterschied zwischen ausführliche und einfache Syntax in der Programmiersprache f#.
ms.date: 05/16/2016
ms.openlocfilehash: b4f2354738da4692cb444e5e7dd9531d80d26664
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2018
ms.locfileid: "44367941"
---
# <a name="verbose-syntax"></a>Ausführliche Syntax

Es gibt zwei Formen der Syntax für viele Konstrukte in f# verfügbar: *ausführliche Syntax* und *einfache Syntax*. Die ausführliche Syntax ist nicht so häufig verwendet, aber Sie hat den Vorteil, dass weniger anfällig für den Einzug. Die einfache Syntax ist kürzer und Einzüge verwendet, um Anfang und Ende von Konstrukten zu signalisieren, anstatt zusätzliche Schlüsselwörter wie `begin`, `end`, `in`und so weiter. Standardmäßig ist die einfache Syntax. Dieses Thema beschreibt die Syntax für f#-Konstrukte, wenn die einfacher Syntax nicht aktiviert ist. Ausführlicher Syntax ist immer aktiviert, sodass auch, wenn Sie einfachen Syntax aktiviert haben, können Sie ausführlichen Syntax für einige Konstrukte weiterhin verwenden. Sie können einfachen Syntax deaktivieren, indem Sie mit der `#light "off"` Richtlinie.

## <a name="table-of-constructs"></a>Tabelle der Konstrukte

Die folgende Tabelle zeigt die einfache und ausführliche Syntax für F#-Konstrukte in Kontexten, ein Unterschied zwischen den beiden Formaten besteht. In dieser Tabelle spitze Klammern (&lt;&gt;) schließen Sie die benutzerdefinierte Syntaxelemente. Finden Sie in der Dokumentation für jede Sprachkonstrukt Weitere ausführliche Informationen zur Syntax, die innerhalb dieser Konstrukte verwendet.

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

```
<expression1>; <expression2>
```

</td>
</tr>
<tr><td>


geschachtelte `let` Bindungen

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
Codeblock
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
<tr><td>record
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
<tr><td>Klasse
</td><td>
```
type <class-name>(<params>) = ... ```

</td><td>

```
type <class-name>(<params>) =
    class
        ...
    end
```
</td>
</tr>
<tr><td>Struktur</td><td>

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
<tr><td>Unterscheidungs-union</td><td>

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
<tr><td>interface</td><td>

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
<tr><td>Object-Ausdruck</td><td>

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
<tr><td>Schnittstellenimplementierung</td><td>

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
<tr><td>typerweiterung</td><td>

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
<tr><td>module</td><td>

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

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
- [Compileranweisungen](compiler-directives.md)
- [Richtlinien für das Formatieren von Code](code-formatting-guidelines.md)
