---
title: Typen
description: Erfahren Sie mehr über die Typen, die F# in verwendet F# werden, und wie Typen benannt und beschrieben werden.
ms.date: 05/16/2016
ms.openlocfilehash: 70d79525318c8d2eb0711d6a1b50be1ac0cf0226
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75348212"
---
# <a name="f-types"></a>F#-Typen

In diesem Thema werden die Typen beschrieben, die F# in verwendet F# werden, und wie Typen benannt und beschrieben werden.

## <a name="summary-of-f-types"></a>Zusammenfassung F# der Typen

Einige Typen werden als *primitive Typen*betrachtet, wie z. b. der boolesche Typ `bool` und ganzzahlige Typen und Gleit Komma Typen mit unterschiedlichen Größen, die Typen für Bytes und Zeichen einschließen. Diese Typen werden in [primitiven Typen](basic-types.md)beschrieben.

Andere Typen, die in die Sprache integriert sind, umfassen Tupel, Listen, Arrays, Sequenzen, Datensätze und Unterscheidungs-Unions. Wenn Sie mit anderen .NET-Sprachen vertraut sind und lernen F#, lesen Sie die Themen für die einzelnen Typen. Links zu weiteren Informationen zu diesen Typen finden Sie im Abschnitt [Verwandte Themen](https://msdn.microsoft.com/library/#rel) dieses Themas. Diese F#spezifischen Typen unterstützen Programmier Stile, die von funktionalen Programmiersprachen gemeinsam sind. Viele dieser Typen verfügen über zugeordnete Module in F# der Bibliothek, die gängige Vorgänge für diese Typen unterstützen.

Der Typ einer Funktion enthält Informationen über die Parametertypen und den Rückgabetyp.

Der .NET Framework ist die Quelle von Objekttypen, Schnittstellentypen, Delegattypen und anderen. Sie können eigene Objekttypen genau wie in jeder anderen .NET-Sprache definieren.

F# Code kann auch Aliase definieren, die benannte *typabkürzungen*sind, die Alternative Namen für-Typen sind. Sie können typabkürzungen verwenden, wenn sich der Typ in der Zukunft ändern kann, und Sie vermeiden möchten, den Code zu ändern, der vom Typ abhängt. Oder Sie können eine typabkürzung als anzeigen Amen für einen Typ verwenden, der den Code leichter lesbar und verständlich machen kann.

F#bietet nützliche Auflistungs Typen, die mit der funktionalen Programmierung im Hinterkopf entworfen wurden. Mithilfe dieser Sammlungs Typen können Sie Code schreiben, der im Stil funktionaler ist. Weitere Informationen finden [ F# Sie unter Sammlungs Typen](fsharp-collection-types.md).

## <a name="syntax-for-types"></a>Syntax für Typen

Im F# Code müssen Sie häufig die Namen von Typen schreiben. Jeder Typ verfügt über ein syntaktisches Formular, und Sie verwenden diese syntaktischen Formen in Typanmerkungen, abstrakten Methoden Deklarationen, Delegatdeklarationen, Signaturen und anderen Konstrukten. Wenn Sie ein neues Programm Konstrukt im Interpreter deklarieren, druckt der Interpreter den Namen des Konstrukts und die Syntax für seinen Typ. Diese Syntax kann nur ein Bezeichner für einen benutzerdefinierten Typ oder ein integrierter Bezeichner wie z. b. für `int` oder `string`sein, aber bei komplexeren Typen ist die Syntax komplexer.

Die folgende Tabelle zeigt Aspekte der Typsyntax für F# -Typen.

|Typ|Typsyntax|Beispiele|
|----|-----------|--------|
|primitiver Typ|*type-name*|`int`<br /><br />`float`<br /><br />`string`|
|Aggregattyp (Klasse, Struktur, Union, Datensatz, Enumeration usw.)|*type-name*|`System.DateTime`<br /><br />`Color`|
|typabkürzung|*type-abbreviation-name*|`bigint`|
|voll qualifizierter Typ|*namespaces.type-name*<br /><br />oder<br /><br />*modules.type-name*<br /><br />oder<br /><br />*namespaces.modules.type-name*|`System.IO.StreamWriter`|
|-Array|*Type-Name*[] oder<br /><br />*Type-Name-* Array|`int[]`<br /><br />`array<int>`<br /><br />`int array`|
|zweidimensionales Array|*Typname*[,]|`int[,]`<br /><br />`float[,]`|
|dreidimensionales Array|*Typname*[,,]|`float[,,]`|
|tuple|*Type-Name1* &#42; *Type-name2* ...|`(1,'b',3)` hat z. b. den Typ `int * char * int`|
|generischer Typ|*Type-Parameter* *Generic-Type-Name*<br /><br />oder<br /><br />*generic-type-name*&lt;*type-parameter-list*&gt;|`'a list`<br /><br />`list<'a>`<br /><br />`Dictionary<'key, 'value>`|
|konstruierter Typ (ein generischer Typ, für den ein bestimmtes Typargument angegeben ist)|*Type-Argument* *Generic-Type-Name*<br /><br />oder<br /><br />*generic-type-name*&lt;*type-argument-list*&gt;|`int option`<br /><br />`string list`<br /><br />`int ref`<br /><br />`option<int>`<br /><br />`list<string>`<br /><br />`ref<int>`<br /><br />`Dictionary<int, string>`|
|Funktionstyp, der über einen einzelnen Parameter verfügt|*Parameter-Typ1* -&gt; *Rückgabetyp*|Eine Funktion, die eine `int` annimmt und eine `string` den Typ zurückgibt `int -> string`|
|Funktionstyp mit mehreren Parametern|*Parameter-Typ1* -&gt; *Parameter-Typ2* -&gt;...-&gt; *Rückgabetyp*|Eine Funktion, die eine `int` und eine `float` und eine `string` der den Typ zurückgibt `int -> float -> string`|
|höhere Reihenfolge Funktion als Parameter|(*Funktionstyp*)|`List.map` hat den Typ `('a -> 'b) -> 'a list -> 'b list`|
|Delegat|Delegat von " *Function-Type* "|`delegate of unit -> int`|
|flexibler Typ|#*Type-Name*|`#System.Windows.Forms.Control`<br /><br />`#seq<int>`|

## <a name="related-topics"></a>Verwandte Themen

|Topic|Beschreibung|
|-----|-----------|
|[Primitive Typen](basic-types.md)|Beschreibt integrierte einfache Typen, z. b. ganzzahlige Typen, den booleschen Typ und Zeichen Typen.|
|[Unit-Typ](unit-type.md)|Beschreibt den `unit` Typ, einen Typ, der über einen Wert verfügt und der durch () angegeben wird. entspricht `void` in C# und `Nothing` in Visual Basic.|
|[Tupel](tuples.md)|Beschreibt den tupeltyp. dabei handelt es sich um einen Typ, der aus zugeordneten Werten eines beliebigen Typs besteht, der in Paaren, Paaren, verviereln usw. gruppiert ist.|
|[Optionen](options.md)|Beschreibt den Optionstyp, einen Typ, der möglicherweise entweder einen Wert oder leer ist.|
|[Listen](lists.md)|Beschreibt Listen, bei denen es sich um eine geordnete, unveränderliche Reihe von Elementen desselben Typs handelt.|
|[Arrays](arrays.md)|Beschreibt Arrays, bei denen es sich um geordnete Sätze änderbarer Elemente desselben Typs handelt, die einen zusammenhängenden Speicherblock belegen und eine festgelegte Größe haben.|
|[Sequenzen](sequences.md)|Beschreibt den Sequenztyp, der eine logische Reihenfolge von Werten darstellt. einzelne Werte werden nur bei Bedarf berechnet.|
|[Datensätze](records.md)|Beschreibt den Daten Satz Typen, ein kleines Aggregat benannter Werte.|
|[Unterscheidbare Unions](discriminated-unions.md)|Beschreibt den Unterscheidungs-Union-Typ, einen Typ, dessen Werte einen beliebigen Satz möglicher Typen aufweisen können.|
|[Funktionen](./functions/index.md)|Beschreibt Funktions Werte.|
|[Klassen](classes.md)|Beschreibt den Klassentyp, einen Objekttyp, der einem .net-Verweistyp entspricht. Klassentypen können Member, Eigenschaften, implementierte Schnittstellen und einen Basistyp enthalten.|
|[Strukturen](structures.md)|Beschreibt den `struct` Typ, einen Objekttyp, der einem .net-Werttyp entspricht. Der `struct` Typ stellt in der Regel ein kleines Aggregat von Daten dar.|
|[Schnittstellen](interfaces.md)|Beschreibt Schnittstellentypen, bei denen es sich um Typen handelt, die eine Reihe von Membern darstellen, die bestimmte Funktionen bereitstellen, aber keine Daten enthalten. Ein Schnittstellentyp muss von einem Objekttyp implementiert werden, um nützlich zu sein.|
|[Delegaten](delegates.md)|Beschreibt den Delegattyp, der eine Funktion als Objekt darstellt.|
|[Enumerationen](enumerations.md)|Beschreibt Enumerationstypen, deren Werte zu einem Satz benannter Werte gehören.|
|[Attribute](attributes.md)|Beschreibt Attribute, die verwendet werden, um Metadaten für einen anderen Typ anzugeben.|
|[Ausnahmetypen](./exception-handling/exception-types.md)|Beschreibt Ausnahmen, die Fehlerinformationen angeben.|
