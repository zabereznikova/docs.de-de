---
title: Attribute (F#)
description: Erfahren Sie, wie F#--Attribute für Metadaten, die auf ein Programmierungskonstrukt angewendet werden können.
ms.date: 05/16/2016
ms.openlocfilehash: 3e7f1d0ff383e1070b3db72e633f80ea37150548
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2018
ms.locfileid: "46568062"
---
# <a name="attributes"></a>Attribute

Attribute ermöglichen, Metadaten, die auf ein Programmierungskonstrukt angewendet werden.

## <a name="syntax"></a>Syntax

```fsharp
[<target:attribute-name(arguments)>]
```

## <a name="remarks"></a>Hinweise

In der vorherigen Syntax wird die *Ziel* ist optional, und, falls vorhanden, gibt die Art der Programmentität, die auf das Attribut angewendet wird. Gültige Werte für *Ziel* werden angezeigt, in der Tabelle, die weiter unten in diesem Dokument angezeigt wird.

Die *Attributname* bezieht sich auf der (möglicherweise mit Namespaces qualifizierte) Name, der einen gültigen Attributtyp, mit oder ohne das Suffix `Attribute` , die in der Regel in den Typnamen des Attributs verwendet wird. Z. B. den Typ `ObsoleteAttribute` können verkürzt werden `Obsolete` in diesem Kontext.

Die *Argumente* sind die Argumente an den Konstruktor für den Attributtyp. Wenn ein Attribut einen Standardkonstruktor verfügt, können die Liste von Argumenten und die Klammern weggelassen werden. Attribute unterstützen sowohl Positionsargumente als auch benannte Argumente. *Positionelle Argumente* sind Argumente, die in der Reihenfolge verwendet werden, in der sie angezeigt werden. Benannte Argumente können verwendet werden, wenn das Attribut mit öffentliche Eigenschaften aufweist. Sie können diese mit der folgenden Syntax in der Argumentliste festlegen.

```
*property-name* = *property-value*
```

Solche eigenschafteninitialisierungen in beliebiger Reihenfolge möglich, aber sie müssen keine positionellen Argumente folgen. Es folgt ein Beispiel für ein Attribut, das positionelle Argumente und eigenschafteninitialisierungen verwendet.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6202.fs)]

In diesem Beispiel wird das Attribut `DllImportAttribute`, hier in Kurzform verwendet. Das erste Argument ist ein Positionsparameter, und die zweite ist eine Eigenschaft.

Attribute sind ein .NET programming Konstrukt, ein Objekt, bekannt als ein *Attribut* , einen Typ oder anderes Programmelement zugeordnet werden soll. Das Programmelement, das auf das ein Attribut angewendet wird, wird als bezeichnet die *Attributziel*. Das Attribut enthält in der Regel die Metadaten zum Ziel. In diesem Kontext möglicherweise Metadaten von Daten zu den anderen Typ als ihre Felder und Elemente.

Attribute in f# können angewendet werden, um die folgenden Konstrukte der Programmierung: Funktionen, Methoden, Assemblys, Modulen, Typen (Klassen, Datensätze, Strukturen, Schnittstellen, Delegaten, Enumerationen, Unions und So weiter), Konstruktoren, Eigenschaften, Felder, Parameter Geben Sie Parameter und Rückgabewerte. Attribute dürfen nicht auf `let` Bindungen in Klassen, Ausdrücke oder Ausdrücke für Workflows.

In der Regel wird die Deklaration des Attributs direkt vor der Deklaration des Attributziels angezeigt. Mehrere Attributdeklarationen können verwendet werden, zusammen, wie folgt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6603.fs)]

Sie können Attribute zur Laufzeit mit .NET-Reflektion Abfragen.

Sie können mehrere Attribute einzeln zu deklarieren, wie im vorherigen Codebeispiel, oder Sie können diese in einem Satz von Klammern deklarieren, wenn Sie ein Semikolon verwenden, den einzelnen Attributen und Konstruktoren, wie hier gezeigt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6604.fs)]

Gängigen Attributen zählen die `Obsolete` -Attribut, Attribute, sicherheitsüberlegungen, Attribute, für COM-Unterstützung, Attribute, die im Zusammenhang mit den Besitz des Codes und Attribute, die angibt, ob ein Typ serialisiert werden kann. Das folgende Beispiel zeigt die Verwendung der `Obsolete` Attribut.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6605.fs)]

Für das Attribut abzielt `assembly` und `module`, wenden Sie die Attribute auf oberster Ebene `do` in der Assembly binden. Sie können das Wort einschließen `assembly` oder `module` in der Attributdeklaration, wie folgt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6606.fs)]

Wenn Sie weglassen, dass das Attributziel für ein Attribut auf eine `do` Bindung, die f#-Compiler versucht, das Attributziel zu bestimmen, die sinnvoll für dieses Attribut ist. Viele Attributklassen verfügen über ein Attribut des Typs `System.AttributeUsageAttribute` , enthält Informationen zu den möglichen Zielen, die für dieses Attribut unterstützt. Wenn die `System.AttributeUsageAttribute` gibt an, dass das Attribut unterstützt die Funktionen als Ziele, die das Attribut verwendet, um auf den primären Einstiegspunkt des Programms anzuwenden. Wenn die `System.AttributeUsageAttribute` gibt an, dass das Attribut unterstützt Assemblys als Ziele, nimmt der Compiler das Attribut, auf die Assembly angewendet werden soll. Die meisten Attribute nicht für Funktionen und Assemblys, aber in Fällen, in denen dies der Fall, wird das Attribut zuweisen des Programms "main"-Funktion erstellt. Wenn das Attributziel explizit angegeben wird, wird das Attribut auf das angegebene Ziel angewendet.

Obwohl Sie nicht in der Regel benötigen, geben Sie das Attributziel explizit gültige Werte für *Ziel* werden in einem Attribut in der folgenden Tabelle, und Beispiele für die Nutzung angezeigt.

<table>
  <tr>
    <th>Attributziel</td>
    <th>Beispiel</td> 
  </tr>
  <tr>
    <td>Assembly</td>
    <td>`[<assembly: AssemblyVersionAttribute("1.0.0.0")>]`</td> 
  </tr>
  <tr>
    <td>return</td>
    <td>"Funktion1 können X: [<return: Obsolete>] Int = X + 1"</td> 
  </tr>
  <tr>
    <td>Feld</td>
    <td>"[<field: DefaultValue>] Val änderbare X: int"</td> 
  </tr>
  <tr>
    <td>property</td>
    <td>"[<property: Obsolete>] dies. MyProperty = X "</td> 
  </tr>
  <tr>
    <td>Parameter</td>
    <td>' Member dieser. MyMethod ([<param: Out>] X: Ref<int>) = X: = 10'</td> 
  </tr>
  <tr>
    <td>Typ</td>
    <td>
        ```
        [<type: StructLayout(Sequential)>] MyStruct geben Struktur = X: Byte-y: Int-Ende ```
    </td> 
  </tr>
</table>

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
