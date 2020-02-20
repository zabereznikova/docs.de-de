---
title: Attributes
description: Erfahren Sie F# , wie Attribute das Anwenden von Metadaten auf ein Programmierkonstrukt ermöglichen.
ms.date: 05/16/2016
ms.openlocfilehash: 1e42dc61d44f31930a7b34799f28a68a2db69c8c
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/20/2020
ms.locfileid: "77504117"
---
# <a name="attributes"></a>Attributes

Attribute ermöglichen das Anwenden von Metadaten auf ein Programmierkonstrukt.

## <a name="syntax"></a>Syntax

```fsharp
[<target:attribute-name(arguments)>]
```

## <a name="remarks"></a>Bemerkungen

In der vorherigen Syntax ist das *Ziel* optional und gibt, sofern vorhanden, die Art der Programm Entität an, für die das Attribut gilt. Gültige Werte für das *Ziel* werden in der Tabelle angezeigt, die später in diesem Dokument angezeigt wird.

Der *Attribut Name* verweist auf den Namen (möglicherweise mit Namespaces qualifiziert) eines gültigen Attributtyps mit oder ohne das Suffix `Attribute`, der normalerweise in Attributtyp Namen verwendet wird. Beispielsweise kann der Typ `ObsoleteAttribute` in diesem Kontext nur `Obsolete` verkürzt werden.

Die *Argumente* sind die Argumente für den Konstruktor für den Attributtyp. Wenn ein Attribut über einen Parameter losen Konstruktor verfügt, können die Argumentliste und die Klammern ausgelassen werden. Attribute unterstützen sowohl positionelle Argumente als auch benannte Argumente. *Positions Argumente* sind Argumente, die in der Reihenfolge verwendet werden, in der Sie angezeigt werden. Benannte Argumente können verwendet werden, wenn das Attribut öffentliche Eigenschaften hat. Sie können diese mithilfe der folgenden Syntax in der Argumentliste festlegen.

```fsharp
property-name = property-value
```

Solche Eigenschafts Initialisierungen können in beliebiger Reihenfolge vorliegen, aber Sie müssen beliebige Positions Argumente einhalten. Im folgenden finden Sie ein Beispiel für ein Attribut, das Positions Argumente und Eigenschafts Initialisierungen verwendet:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6202.fs)]

In diesem Beispiel ist das-Attribut `DllImportAttribute`, das in kürzerer Form verwendet wird. Das erste Argument ist ein Positions Parameter, und das zweite Argument ist eine Eigenschaft.

Attribute sind ein .net-Programmierkonstrukt, mit dem ein Objekt, das als *Attribut* bezeichnet wird, einem Typ oder einem anderen Programmelement zugeordnet werden kann. Das Programmelement, auf das ein Attribut angewendet wird, wird als *Attribut Ziel*bezeichnet. Das Attribut enthält normalerweise Metadaten zum Ziel. In diesem Kontext können Metadaten beliebige Daten über den Typ sein, der nicht die Felder und Member ist.

Attribute in F# können angewendet werden, um die folgenden Konstrukte der Programmierung: Funktionen, Methoden, Assemblys, Modulen, Typen (Klassen, Datensätze, Strukturen, Schnittstellen, Delegaten, Enumerationen, Unions und So weiter), Konstruktoren, Eigenschaften, Felder, Parameter Geben Sie Parameter und Rückgabewerte. Attribute sind für `let` Bindungen innerhalb von Klassen, Ausdrücken oder Workflow Ausdrücken nicht zulässig.

In der Regel wird die Attribut Deklaration direkt vor der Deklaration des Attribut Ziels angezeigt. Mehrere Attribut Deklarationen können wie folgt verwendet werden:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6603.fs)]

Sie können Attribute zur Laufzeit mithilfe der .NET-Reflektion Abfragen.

Sie können mehrere Attribute einzeln deklarieren, wie im vorherigen Codebeispiel, oder Sie können Sie in einer Gruppe von Klammern deklarieren, wenn Sie die einzelnen Attribute und Konstruktoren mit einem Semikolon trennen, wie im folgenden dargestellt:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6604.fs)]

Zu den Attributen zählen in der Regel das `Obsolete` Attribut, Attribute für Sicherheitsüberlegungen, Attribute für COM-Unterstützung, Attribute, die sich auf den Besitz von Code beziehen, und Attribute, die angeben, ob ein Typ serialisiert werden kann. Im folgenden Beispiel wird die Verwendung des `Obsolete`-Attributs veranschaulicht.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6605.fs)]

Für die Attribut Ziele `assembly` und `module`wenden Sie die Attribute auf eine `do` Bindung der obersten Ebene in der Assembly an. Sie können das Wort `assembly` oder `module` wie folgt in die Attribut Deklaration einschließen:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6606.fs)]

Wenn Sie das Attribut Ziel für ein Attribut weglassen, das auf eine `do` Bindung angewendet F# wird, versucht der Compiler, das Attribut Ziel zu ermitteln, das für dieses Attribut sinnvoll ist. Viele Attribut Klassen verfügen über ein Attribut vom Typ `System.AttributeUsageAttribute`, das Informationen über die möglichen Ziele enthält, die für dieses Attribut unterstützt werden. Wenn die `System.AttributeUsageAttribute` angibt, dass das Attribut Funktionen als Ziele unterstützt, wird das Attribut für den Haupteinstiegspunkt des Programms übernommen. Wenn die `System.AttributeUsageAttribute` angibt, dass das Attribut Assemblys als Ziele unterstützt, übernimmt der Compiler das-Attribut, das auf die Assembly angewendet wird. Die meisten Attribute gelten nicht für Funktionen und Assemblys, aber in Fällen, in denen Sie dies tun, wird das Attribut für die Hauptfunktion des Programms übernommen. Wenn das Attribut Ziel explizit angegeben wird, wird das Attribut auf das angegebene Ziel angewendet.

Obwohl Sie in der Regel das Attribut Ziel nicht explizit angeben müssen, werden in der folgenden Tabelle gültige Werte für das *Ziel* in einem Attribut und Verwendungs Beispiele angezeigt:

<table>
  <tr>
    <th>Attribut Ziel</td>
    <th>Beispiel</td>
  </tr>
  <tr>
    <td>Assembly</td>
    <td><pre lang="fsharp"><code>[&lt;assembly: AssemblyVersionAttribute("1.0.0.0")&gt;]</code></pre></td>
  </tr>
  <tr>
    <td>return</td>
    <td><pre lang="fsharp"><code>let function1 x : [&lt;return: Obsolete&gt;] int = x + 1</code></pre></td>
  </tr>
  <tr>
    <td>Feld</td>
    <td><pre lang="fsharp"><code>[&lt;field: DefaultValue&gt;] val mutable x: int</code></pre></td>
  </tr>
  <tr>
    <td>property</td>
    <td><pre lang="fsharp"><code>[&lt;property: Obsolete&gt;] this.MyProperty = x</code></pre></td>
  </tr>
  <tr>
    <td>param</td>
    <td><pre lang="fsharp"><code>member this.MyMethod([&lt;param: Out&gt;] x : ref&lt;int&gt;) = x := 10</code></pre></td>
  </tr>
  <tr>
    <td>type</td>
    <td>
        <pre lang="fsharp"><code>
[&lt;type: StructLayout(LayoutKind.Sequential)&gt;]
type MyStruct =
  struct
    val x : byte
    val y : int
  end</code></pre>
    </td>
  </tr>
</table>

## <a name="see-also"></a>Weitere Informationen

- [F#-Sprachreferenz](index.md)
