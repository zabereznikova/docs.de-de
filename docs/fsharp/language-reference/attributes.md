---
title: Attribute (F#)
description: Erfahren Sie, wie f# Attribute ermöglichen, dass Metadaten auf ein Programmiermodell angewendet werden soll.
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 95c001e6-3708-4d04-a850-d855f78eb51e
ms.openlocfilehash: 88098e51d19a86f501c35abe3408524378f147b3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="attributes"></a>Attribute

Attribute ermöglichen, Metadaten auf ein Programmiermodell angewendet werden soll.

## <a name="syntax"></a>Syntax

```fsharp
[<target:attribute-name(arguments)>]
```

## <a name="remarks"></a>Hinweise

In der vorherigen Syntax der *Ziel* ist optional und, falls vorhanden, gibt die Art der Programmentität, die auf das Attribut angewendet wird. Gültige Werte für *Ziel* werden in der Tabelle, die weiter unten in diesem Dokument genannten angezeigt.

Die *Attributnamen* bezieht sich auf den Namen (möglicherweise mit Namespaces qualifiziert) eines gültigen Attributtyps, mit oder ohne das Suffix `Attribute` , die in der Regel in Attributnamen-Typ verwendet wird. Z. B. den Typ `ObsoleteAttribute` gekürzt werden können, um den gerade `Obsolete` in diesem Kontext.

Die *Argumente* sind die Argumente des Konstruktors für den Typ des Attributs. Wenn ein Attribut über einen Standardkonstruktor verfügt, können der Argumentliste und die Klammern weggelassen werden. Attribute unterstützen sowohl Positionsargumente und benannte Argumente. *Positionsargumente* sind Argumente, die in der Reihenfolge verwendet werden, in der sie angezeigt werden. Benannte Argumente können verwendet werden, wenn das Attribut öffentliche Eigenschaften besitzt. Sie können diese Ereignisse mithilfe der folgenden Syntax in der Argumentliste festlegen.

```
*property-name* = *property-value*
```

Eine solche Eigenschaft Initialisierungen können in beliebiger Reihenfolge sein, aber sie müssen alle Positionsargumente entsprechen. Es folgt ein Beispiel für ein Attribut, das Positions- und Initialisierungen der Eigenschaft verwendet.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6202.fs)]

In diesem Beispiel wird das Attribut `DllImportAttribute`, hier in Kurzform verwendet. Das erste Argument ist ein Positionsparameter und die zweite ist eine Eigenschaft.

Attribute sind ein .NET Programmiermodell, das ein Objekt, das als bezeichnet ermöglicht eine *Attribut* einen Typ oder ein anderes Programmelement zugeordnet werden soll. Das Programmelement, das auf die ein Attribut angewendet wird, wird als bezeichnet den *Attributziel*. Das Attribut enthält normalerweise Metadaten zum Ziel. In diesem Kontext möglicherweise Metadaten Daten über den Typ als dessen Felder und Member.

Attribute in f# können auf die folgenden Programmierungskonstrukte angewendet werden: Funktionen, Methoden, Assemblys, Module, Typen (Klassen, Datensätze, Strukturen, Schnittstellen, Delegaten, Enumerationen, Unions und So weiter), Konstruktoren, Eigenschaften, Felder, Parameter Geben Sie die Parameter und Rückgabewerte. Attribute dürfen nicht auf `let` Bindungen in Klassen, Ausdrücke oder Ausdrücke für Workflows.

In der Regel wird die Attributdeklaration direkt vor der Deklaration des Attributziels angezeigt. Mehrere Attributdeklarationen können verwendet werden, zusammen, wie folgt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6603.fs)]

Sie können Attribute zur Laufzeit mithilfe der .NET-Spiegelung Abfragen.

Sie können mehrere Attribute einzeln deklarieren, wie im vorherigen Codebeispiel, oder Sie können diese in einem Satz von Klammern deklarieren, wenn Sie ein Semikolon verwenden, trennen Sie die einzelnen Attribute und Konstruktoren, wie hier gezeigt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6604.fs)]

In der Regel beim Attribute enthalten die `Obsolete` Attribut Attribute für Sicherheitsaspekte, Attribute, für COM-Unterstützung, Attribute, der Besitz des Codes in Bezug auf, und Attribute, die angibt, ob ein Typ serialisiert werden kann. Das folgende Beispiel veranschaulicht die Verwendung von der `Obsolete` Attribut.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6605.fs)]

Für das Attribut abzielt `assembly` und `module`, wenden Sie die Attribute auf einem der obersten Ebene `do` in Ihrer Assembly binden. Sie können das Wort einschließen `assembly` oder `module` in der Attributdeklaration wie folgt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6606.fs)]

Wenn Sie Attributziel für ein Attribut weglassen auf eine `do` binden, f#-Compiler versucht Attributziel zu ermitteln, die für dieses Attribut sinnvoll ist. Viele Attributklassen verfügen über ein Attribut des Typs `System.AttributeUsageAttribute` , enthält Informationen zu den möglichen Ziele für dieses Attribut unterstützt. Wenn die `System.AttributeUsageAttribute` gibt an, dass das Attribut Funktionen als Ziele unterstützt, das Attribut wird verwendet, um auf den Haupteinstiegspunkt des Programms anzuwenden. Wenn die `System.AttributeUsageAttribute` gibt an, dass das Attribut Assemblys als Ziele unterstützt, nimmt der Compiler das Attribut für die Assembly angewendet. Die meisten Attribute gelten nicht für Funktionen und Assemblys, aber in Fällen, in denen dies der Fall, wird das Attribut an, das Programm main-Funktion übernommen. Wenn das Attributziel explizit angegeben wird, wird das Attribut auf das angegebene Ziel angewendet.

Obwohl Sie nicht in der Regel benötigen, geben Sie das Attribut als Ziel explizit, gültige Werte für *Ziel* in einem Attribut werden in der folgenden Tabelle zusammen mit Beispielen, die Verwendung von angezeigt.

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
    <td>Param</td>
    <td>"Member dies. MyMethod ([<param: Out>] X: Ref<int>) = X: = 10'</td> 
  </tr>
  <tr>
    <td>Typ</td>
    <td>
        ```
        [<type: StructLayout(Sequential)>] geben MyStruct Struktur = X: Byte y: Int-Ende```
    </td> 
  </tr>
</table>

## <a name="see-also"></a>Siehe auch

[F#-Sprachreferenz](index.md)
