---
title: F#-Typen
description: Erfahren Sie mehr über die Typen, die verwendet werden F# und wie F# Typen benannt und beschrieben.
ms.date: 05/16/2016
ms.openlocfilehash: b48376c80b48df210bf7bc699a769d40fec60864
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61934640"
---
# <a name="f-types"></a>F#-Typen

In diesem Thema wird beschrieben, die Typen, die verwendet werden F# und wie F# Typen benannt und beschrieben.

## <a name="summary-of-f-types"></a>Zusammenfassung der F# Typen
Einige Typen werden als *primitive Typen*, z. B. den booleschen Typ `bool` und ganzzahlige Typen und Gleitkommatypen mit verschiedenen Größen, die Typen für Bytes und Zeichen enthalten. Diese Typen werden in beschrieben [Primitive Typen](primitive-types.md).

Andere Typen, die in der Sprache integriert sind enthalten, Tupeln, Listen, Arrays, Sequenzen, Datensätze und Unterscheidungs-Unions. Wenn Sie über Erfahrungen mit anderen .NET-Sprachen und Learning F#, lesen Sie in den Themen für jeden dieser Typen. Links zu weiteren Informationen zu diesen Typen sind in enthalten die [Themen](https://msdn.microsoft.com/library/#rel) Abschnitt dieses Themas. Diese F#-Unterstützung für bestimmte Formate der Programmierung, die zu funktionaler Programmiersprachen gelten. Viele dieser Module im verknüpft haben die F# Bibliothek, die gängige Vorgänge für diese Typen unterstützen.

Der Typ einer Funktion enthält Informationen zu den Parametertypen und Rückgabetyp.

.NET Framework ist die Quelle der Objekte des Typs, Schnittstellentypen, Delegattypen und andere. Sie können Ihre eigenen Objekttypen definieren, ebenso wie in einer beliebigen anderen .NET-Sprache.

Darüber hinaus F# Code kann definieren, Aliase, die benannt werden *typabkürzungen*, alternative Namen für Typen sind. Sie können die typabkürzungen verwenden, wenn der Typ in Zukunft ändern kann und um zu vermeiden, ändern den Code, der vom Typ abhängt. Oder Sie können eine typabkürzung als Anzeigenamen für einen Typ, mit denen kann Code einfacher zu lesen und zu verstehen.

F#funktionale Programmierung, denken Sie daran bietet nützliche Auflistungstypen, die entwickelt wurden. Verwenden diese Auflistungstypen können Sie Code schreiben, der im Format mehr funktionsfähig ist. Weitere Informationen finden Sie unter [ F# Auflistungstypen](fsharp-collection-types.md).

## <a name="syntax-for-types"></a>Syntax für Typen
In F# Code häufig müssen Sie die Namen der Typen schreiben. Jeder Typ verfügt über eine syntaktischen Form, und Sie verwenden diese syntaktische Formulare in typanmerkungen, Abstrakte Methodendeklarationen, Delegatdeklarationen, Signaturen und andere Konstrukte. Wenn Sie ein neues Programmkonstrukt im Interpreter deklarieren, gibt der Interpreter den Namen des Konstrukts und die Syntax für den Typ an. Diese Syntax ist möglicherweise nur ein Bezeichner für einen benutzerdefinierten Typ oder ein integrierter Bezeichner, z. B. für `int` oder `string`, jedoch für komplexere Typen, die Syntax ist komplexer.

Die folgende Tabelle zeigt die Bestandteile der Type-Syntax für F# Typen.

|Typ|Type-syntax|Beispiele|
|----|-----------|--------|
|primitiver Typ|*type-name*|`int`<br /><br />`float`<br /><br />`string`|
|aggregierter Typ (Klasse, Struktur, Union, Datensatz, Enum, usw.)|*type-name*|`System.DateTime`<br /><br />`Color`|
|-typabkürzung|*type-abbreviation-name*|`bigint`|
|voll qualifizierte Typ|*namespaces.type-name*<br /><br />oder<br /><br />*modules.type-name*<br /><br />oder<br /><br />*namespaces.modules.type-name*|`System.IO.StreamWriter`|
|array|*Typname*[] oder<br /><br />*Typname* Array|`int[]`<br /><br />`array<int>`<br /><br />`int array`|
|zweidimensionales array|*type-name*[,]|`int[,]`<br /><br />`float[,]`|
|dreidimensionale array|*type-name*[,,]|`float[,,]`|
|tuple|*Typ: name1* &#42; *Typ-name2* ...|Z. B. `(1,'b',3)` weist den Typ `int * char * int`|
|generischer Typ|*type-parameter* *generic-type-name*<br /><br />oder<br /><br />*generic-type-name*&lt;*type-parameter-list*&gt;|`'a list`<br /><br />`list<'a>`<br /><br />`Dictionary<'key, 'value>`|
|konstruierter Typ (ein generischer Typ, der ein bestimmten Typargument verfügt)|*type-argument* *generic-type-name*<br /><br />oder<br /><br />*generic-type-name*&lt;*type-argument-list*&gt;|`int option`<br /><br />`string list`<br /><br />`int ref`<br /><br />`option<int>`<br /><br />`list<string>`<br /><br />`ref<int>`<br /><br />`Dictionary<int, string>`|
|Typ der Funktion, die einen einzelnen Parameter|*parameter-type1* -&gt; *return-type*|Eine Funktion, verwendet eine `int` und gibt eine `string` weist den Typ `int -> string`|
|Typ der Funktion, die über mehrere Parameter verfügt.|*Parameter-Typ1*  - &gt; *Parameter-type2*  - &gt; ... –&gt; *Rückgabetyp*|Eine Funktion, verwendet eine `int` und `float` und gibt eine `string` weist den Typ `int -> float -> string`|
|Funktion höherer Ordnung als parameter|(*function-type*)|`List.map` weist den Typ `('a -> 'b) -> 'a list -> 'b list`|
|delegate|Delegieren von *Funktionstyp:*|`delegate of unit -> int`|
|flexiblen Typ|#*type-name*|`#System.Windows.Forms.Control`<br /><br />`#seq<int>`|

## <a name="related-topics"></a>Verwandte Themen

|Thema|Beschreibung|
|-----|-----------|
|[Primitive Typen](primitive-types.md)|Beschreibt die integrierte einfache Typen wie z. B. ganzzahligen Typen, booleschen und Zeichentypen.|
|[Unit-Typ](unit-type.md)|Beschreibt die `unit` Typ, ein Typ, der einen Wert aufweist, und, () angegeben wird, entspricht der `void` in C# und `Nothing` in Visual Basic.|
|[Tupel](tuples.md)|Beschreibt den Tupeltyp, der ein Typ, der zugehörigen Werte eines beliebigen Typs, der in-Paare, -Tripel, Quadrupel und So weiter gruppiert besteht.|
|[Optionen](options.md)|Beschreibt den Optionstyp, ein Typ, der möglicherweise einen Wert haben oder leer sein.|
|[Listen](lists.md)|Beschreibt, Listen, die geordnete, unveränderliche Reihe von Elementen werden alle den gleichen Typ aufweisen.|
|[Arrays](arrays.md)|Beschreibt Arrays, die Sätze des änderbar Elemente desselben Typs sortiert werden, die einen zusammenhängenden Speicherblock zu belegen und mit fester Größe an.|
|[Sequenzen](sequences.md)|Beschreibt den Sequenz, die eine logische Reihe von Werten darstellt; einzelne Werte werden nur bei Bedarf berechnet.|
|[Datensätze](records.md)|Beschreibt, der Eintragstyp, ein kleines Aggregat benannter Werte.|
|[Unterscheidbare Unions](discriminated-unions.md)|Beschreibt die diskriminierte union-Typs ein Typ, dessen Werte eine einer Reihe von möglichen Typen sein können.|
|[Funktionen](functions/index.md)|Beschreibt die Werte von Funktionen.|
|[Klassen](classes.md)|Beschreibt den Klassentyp, einen Objekttyp, der in einen Verweistyp .NET entspricht. Klassentypen können Elemente, Eigenschaften, implementierten Schnittstellen und einen Basistyp enthalten.|
|[Strukturen](structures.md)|Beschreibt die `struct` Typ, der einen Objekttyp, der ein entspricht. Die `struct` Typ wird in der Regel ein kleines Aggregat der Daten darstellt.|
|[Schnittstellen](interfaces.md)|Beschreibt die Schnittstellentypen, die Typen, die eine Menge von Elementen darstellen, die bestimmte Funktionen bereitstellen, aber, die keine Daten enthalten. Ein Schnittstellentyp muss durch einen Objekttyp nützlich implementiert werden.|
|[Delegaten](delegates.md)|Beschreibt den Delegattyp, der eine Funktion als ein Objekt darstellt.|
|[Enumerationen](enumerations.md)|Beschreibt, Enumerationstypen, deren Werte zu einem Satz benannter Werte gehören.|
|[Attribute](attributes.md)|Beschreibt die Attribute, die verwendet werden, um Metadaten für einen anderen Typ anzugeben.|
|[Ausnahmetypen](exception-handling/exception-types.md)|Beschreibt die Ausnahmen, die Fehlerinformationen angeben.|
