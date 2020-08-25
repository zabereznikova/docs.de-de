---
title: Typen
description: 'Erfahren Sie mehr über die Typen, die in f # verwendet werden, und wie f #-Typen benannt und beschrieben werden.'
ms.date: 08/15/2020
ms.openlocfilehash: a86d8e8f672d8399b02bb193ae04e1f0d46720b6
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2020
ms.locfileid: "88812067"
---
# <a name="f-types"></a>F#-Typen

In diesem Thema werden die Typen beschrieben, die in f # verwendet werden, und wie f #-Typen benannt und beschrieben werden.

## <a name="summary-of-f-types"></a>Zusammenfassung von F #-Typen

Einige Typen werden als *primitive Typen*betrachtet, z. b. der boolesche Typ und die ganzzahligen `bool` und Gleit Komma Typen verschiedener Größen, die Typen für Bytes und Zeichen einschließen. Diese Typen werden in [primitiven Typen](basic-types.md)beschrieben.

Andere Typen, die in die Sprache integriert sind, umfassen Tupel, Listen, Arrays, Sequenzen, Datensätze und Unterscheidungs-Unions. Wenn Sie mit anderen .NET-Sprachen arbeiten und F # erlernen möchten, lesen Sie die Themen für die einzelnen Typen. Diese F #-spezifischen Typen unterstützen Programmier Stile, die von funktionalen Programmiersprachen gemeinsam sind. Viele dieser Typen verfügen über zugeordnete Module in der F #-Bibliothek, die gängige Vorgänge für diese Typen unterstützen.

Der Typ einer Funktion enthält Informationen über die Parametertypen und den Rückgabetyp.

Der .NET Framework ist die Quelle von Objekttypen, Schnittstellentypen, Delegattypen und anderen. Sie können eigene Objekttypen genau wie in jeder anderen .NET-Sprache definieren.

F #-Code kann auch Aliase definieren, die benannte *typabkürzungen*sind, bei denen es sich um alternative Namen für Typen handelt. Sie können typabkürzungen verwenden, wenn sich der Typ in der Zukunft ändern kann, und Sie vermeiden möchten, den Code zu ändern, der vom Typ abhängt. Oder Sie können eine typabkürzung als anzeigen Amen für einen Typ verwenden, der den Code leichter lesbar und verständlich machen kann.

F # stellt nützliche Auflistungs Typen bereit, die im Hinblick auf funktionale Programmierung entworfen wurden. Mithilfe dieser Sammlungs Typen können Sie Code schreiben, der im Stil funktionaler ist. Weitere Informationen finden Sie unter [F #](fsharp-collection-types.md)-Auflistungs Typen.

## <a name="syntax-for-types"></a>Syntax für Typen

In F #-Code müssen Sie häufig die Namen von Typen schreiben. Jeder Typ verfügt über ein syntaktisches Formular, und Sie verwenden diese syntaktischen Formen in Typanmerkungen, abstrakten Methoden Deklarationen, Delegatdeklarationen, Signaturen und anderen Konstrukten. Wenn Sie ein neues Programm Konstrukt im Interpreter deklarieren, druckt der Interpreter den Namen des Konstrukts und die Syntax für seinen Typ. Diese Syntax kann nur ein Bezeichner für einen benutzerdefinierten Typ oder ein integrierter Bezeichner wie z. b. für `int` oder sein `string` , aber bei komplexeren Typen ist die Syntax komplexer.

In der folgenden Tabelle werden Aspekte der Typsyntax für F #-Typen angezeigt.

|type|Typsyntax|Beispiele|
|----|-----------|--------|
|primitiver Typ|*Typname*|`int`<br /><br />`float`<br /><br />`string`|
|Aggregattyp (Klasse, Struktur, Union, Datensatz, Enumeration usw.)|*Typname*|`System.DateTime`<br /><br />`Color`|
|typabkürzung|*Type-Abkürzung-Name*|`bigint`|
|voll qualifizierter Typ|*Namespaces. Type-Name*<br /><br />oder<br /><br />*Module. Type-Name*<br /><br />oder<br /><br />*Namespaces. modules. Type-Name*|`System.IO.StreamWriter`|
|array|*Type-Name*[] oder<br /><br />*Type-Name-* Array|`int[]`<br /><br />`array<int>`<br /><br />`int array`|
|zweidimensionales Array|*Typname*[,]|`int[,]`<br /><br />`float[,]`|
|dreidimensionales Array|*Typname*[,,]|`float[,,]`|
|tuple|*Type-Name1* &#42; *Type-name2* ...|Beispielsweise weist den Typ auf. `(1,'b',3)``int * char * int`|
|generischer Typ|*Type-Parameter* *Generic-Type-Name*<br /><br />oder<br /><br />*generischer Typname* &lt; *Type-Parameter-List*&gt;|`'a list`<br /><br />`list<'a>`<br /><br />`Dictionary<'key, 'value>`|
|konstruierter Typ (ein generischer Typ, für den ein bestimmtes Typargument angegeben ist)|*Type-Argument* *Generic-Type-Name*<br /><br />oder<br /><br />*generischer Typname* &lt; *Type-Argument-List*&gt;|`int option`<br /><br />`string list`<br /><br />`int ref`<br /><br />`option<int>`<br /><br />`list<string>`<br /><br />`ref<int>`<br /><br />`Dictionary<int, string>`|
|Funktionstyp, der über einen einzelnen Parameter verfügt|*Parameter-Typ1*  - &gt; *Rückgabetyp*|Eine Funktion, die einen `int` -Wert annimmt und einen has-Typ zurückgibt `string``int -> string`|
|Funktionstyp mit mehreren Parametern|*Parameter-Typ1*  - &gt; *Parameter-Typ2*  - &gt; ...- &gt; *Rückgabetyp*|Eine Funktion, die einen `int` und einen annimmt `float` und einen `string` has-Typ zurückgibt `int -> float -> string`|
|höhere Reihenfolge Funktion als Parameter|(*Funktionstyp*)|`List.map` hat Typ `('a -> 'b) -> 'a list -> 'b list`|
|delegate|Delegat von " *Function-Type* "|`delegate of unit -> int`|
|flexibler Typ|#*Typname*|`#System.Windows.Forms.Control`<br /><br />`#seq<int>`|

## <a name="related-topics"></a>Verwandte Themen

|Thema|BESCHREIBUNG|
|-----|-----------|
|[Primitive Typen](basic-types.md)|Beschreibt integrierte einfache Typen, z. b. ganzzahlige Typen, den booleschen Typ und Zeichen Typen.|
|[Unit-Typ](unit-type.md)|Beschreibt den `unit` Typ, einen Typ, der über einen Wert verfügt und der durch () angegeben wird `void` . entspricht in c# und `Nothing` in Visual Basic.|
|[Tupel](tuples.md)|Beschreibt den tupeltyp. dabei handelt es sich um einen Typ, der aus zugeordneten Werten eines beliebigen Typs besteht, der in Paaren, Paaren, verviereln usw. gruppiert ist.|
|[Optionen](options.md)|Beschreibt den Optionstyp, einen Typ, der möglicherweise entweder einen Wert oder leer ist.|
|[Listen](lists.md)|Beschreibt Listen, bei denen es sich um eine geordnete, unveränderliche Reihe von Elementen desselben Typs handelt.|
|[Arrays](arrays.md)|Beschreibt Arrays, bei denen es sich um geordnete Sätze änderbarer Elemente desselben Typs handelt, die einen zusammenhängenden Speicherblock belegen und eine festgelegte Größe haben.|
|[Sequenzen](sequences.md)|Beschreibt den Sequenztyp, der eine logische Reihenfolge von Werten darstellt. einzelne Werte werden nur bei Bedarf berechnet.|
|[Datensätze](records.md)|Beschreibt den Daten Satz Typen, ein kleines Aggregat benannter Werte.|
|[Unterscheidungs-Unions](discriminated-unions.md)|Beschreibt den Unterscheidungs-Union-Typ, einen Typ, dessen Werte einen beliebigen Satz möglicher Typen aufweisen können.|
|[Funktionen](./functions/index.md)|Beschreibt Funktions Werte.|
|[Klassen](classes.md)|Beschreibt den Klassentyp, einen Objekttyp, der einem .net-Verweistyp entspricht. Klassentypen können Member, Eigenschaften, implementierte Schnittstellen und einen Basistyp enthalten.|
|[Strukturen](structures.md)|Beschreibt den `struct` Typ, einen Objekttyp, der einem .net-Werttyp entspricht. Der- `struct` Typ stellt in der Regel ein kleines Aggregat von Daten dar.|
|[Schnittstellen](interfaces.md)|Beschreibt Schnittstellentypen, bei denen es sich um Typen handelt, die eine Reihe von Membern darstellen, die bestimmte Funktionen bereitstellen, aber keine Daten enthalten. Ein Schnittstellentyp muss von einem Objekttyp implementiert werden, um nützlich zu sein.|
|[Delegaten](delegates.md)|Beschreibt den Delegattyp, der eine Funktion als Objekt darstellt.|
|[Enumerationen](enumerations.md)|Beschreibt Enumerationstypen, deren Werte zu einem Satz benannter Werte gehören.|
|[Attribute](attributes.md)|Beschreibt Attribute, die verwendet werden, um Metadaten für einen anderen Typ anzugeben.|
|[Ausnahmetypen](./exception-handling/exception-types.md)|Beschreibt Ausnahmen, die Fehlerinformationen angeben.|
