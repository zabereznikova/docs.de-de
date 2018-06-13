---
title: F#-Typen
description: Erfahren Sie, bis die Typen, die verwendet werden, in F# erläutert werden und wie f#-Typen mit dem Namen beschrieben werden.
ms.date: 05/16/2016
ms.openlocfilehash: bdbb89dc751970ac31fe102df009f0bff6388e52
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33565585"
---
# <a name="f-types"></a>F#-Typen

Dieses Thema beschreibt die Typen, die verwendet werden, in F# erläutert werden und wie f#-Typen mit dem Namen beschrieben werden.


## <a name="summary-of-f-types"></a>Zusammenfassung der f#-Typen
Einige Typen gelten als *Grundtypen*, z. B. boolescher Typ `bool` und Ganzzahl- und Gleitkommatyps Verbindungspunkttypen mit verschiedenen Größen, die Typen für Bytes und Zeichen enthalten. Diese Typen werden in beschrieben [Grundtypen](primitive-types.md).

Andere Typen, die in der Sprache integrierte einschließen, Tupeln, Listen, Arrays, Sequenzen, Datensätze und Unterscheidungs-Unions. Wenn Sie verfügen über Erfahrung mit anderen .NET-Sprachen und lernen f# sind, sollten Sie für jeden dieser Typen in den Themen lesen. Links zu weiteren Informationen über diese Typen befinden sich die [Verwandte Themen](https://msdn.microsoft.com/library/#rel) Abschnitt dieses Themas. Die f#-Unterstützung für bestimmte Programmierstile, die für die funktionalen Programmiersprachen gelten. Viele dieser Typen sind Module in der F#-Bibliothek zugeordnet, die häufig verwendeter Vorgänge auf diese Typen zu unterstützen.

Der Typ einer Funktion enthält Informationen zu den Parametertypen und Rückgabetyp.

.NET Framework ist die Quelle von Objekttypen, Schnittstellentypen und Delegattypen. Sie können eigene Objekttypen definieren, ebenso wie Sie in jeder anderen.

F#-Code kann auch mit dem Namen sind Aliase definieren *typabkürzungen*, alternative Namen für Typen sind. Sie können typabkürzungen verwenden, wenn der Typ in der Zukunft ändern kann und Sie möchten, um zu vermeiden, ändern den Code, der hängt vom Typ. Oder Sie typabkürzung als einen Anzeigenamen für einen Typ, der Code leichter kann lesbar und verständlicher zu verwenden.

F# bietet nützliche Auflistungstypen, die mit der funktionalen Programmierung Bedenken vorgesehen sind. Verwenden diese Auflistungstypen können Sie Code schreiben, die im Format mehr funktionsfähig ist. Weitere Informationen finden Sie unter [f#-Auflistungstypen](fsharp-collection-types.md).


## <a name="syntax-for-types"></a>Syntax für Typen
In f#-Code müssen Sie häufig die Namen von Typen zu schreiben. Jeder Typ weist einen Syntaxform, und Sie verwenden diese syntaktischen Formen in abstrakten Methodendeklarationen, typanmerkungen, Delegatdeklarationen, Signaturen und andere Konstrukte. Wenn Sie ein neues Programmkonstrukt in den Interpreter deklarieren, gibt der Interpreter den Namen des Konstrukts und die Syntax für seinen Typ. Diese Syntax ist möglicherweise nur ein Bezeichner für einen benutzerdefinierten Typ oder ein integrierter Bezeichner, z. B. für `int` oder `string`, jedoch ist die Syntax für komplexere Typen komplexer.

Die folgende Tabelle zeigt die Aspekte der Type-Syntax für f#-Typen.



|Typ|Type-syntax|Beispiele|
|----|-----------|--------|
|Grundtyp|*Typname*|`int`<br /><br />`float`<br /><br />`string`|
|aggregierten Typs (Klasse, Struktur, Union, Datensatz, Enum, usw.)|*Typname*|`System.DateTime`<br /><br />`Color`|
|-typabkürzung|*Abkürzung Typnamen*|`bigint`|
|vollqualifizierte Typ|*Namespaces.Type-name*<br /><br />oder<br /><br />*Modules.Type-name*<br /><br />oder<br /><br />*Namespaces.Modules.Type-name*|`System.IO.StreamWriter`|
|array|*Typname*[] oder<br /><br />*Typname* Array|`int[]`<br /><br />`array<int>`<br /><br />`int array`|
|zweidimensionales array|*Typname*[,]|`int[,]`<br /><br />`float[,]`|
|dreidimensionale array|*Typname*[,]|`float[,,]`|
|tuple|*Typ-name1* &#42; *Typ name2* ...|Beispielsweise `(1,'b',3)` weist den Typ `int * char * int`|
|generischer Typ|*Typparameter* *generische-Type-Name*<br /><br />oder<br /><br />*generische Typnamen*&lt;*Typparameterliste*&gt;|`'a list`<br /><br />`list<'a>`<br /><br />`Dictionary<'key, 'value>`|
|konstruierter Typ (ein generischer Typ, die ein bestimmten angegebene Typargument aufweist)|*Argument vom Typ* *generische-Type-Name*<br /><br />oder<br /><br />*generische Typnamen*&lt;*Typargumentliste*&gt;|`int option`<br /><br />`string list`<br /><br />`int ref`<br /><br />`option<int>`<br /><br />`list<string>`<br /><br />`ref<int>`<br /><br />`Dictionary<int, string>`|
|Typ der Funktion, die einen einzelnen Parameter verfügt.|*Parameter-Typ1*  - &gt; *Return-Type*|Eine Funktion, übernimmt ein `int` und gibt eine `string` weist den Typ `int -> string`|
|Funktionstyp, der mehrere Parameter verfügt|*Parameter-Typ1*  - &gt; *Parameter Typ2*  - &gt; ... -&gt; *Return-Type*|Eine Funktion, übernimmt ein `int` und ein `float` und gibt eine `string` weist den Typ `int -> float -> string`|
|Funktion höherer Ordnung als parameter|(*Funktionstyp*)|`List.map` weist den Typ `('a -> 'b) -> 'a list -> 'b list`|
|delegate|Delegieren von *Funktionstyp*|`delegate of unit -> int`|
|Flexible Typ|#*Typname*|`#System.Windows.Forms.Control`<br /><br />`#seq<int>`|

## <a name="related-topics"></a>Verwandte Themen


|Thema|Beschreibung|
|-----|-----------|
|[Primitive Typen](primitive-types.md)|Beschreibt, wie z. B. ganzzahligen Typen, Boolean-Typ und Zeichentypen integrierte einfache Typen.|
|[Unit-Typ](unit-type.md)|Beschreibt die `unit` Typ, ein Typ, der einen Wert aufweist, und () angegeben wird, entspricht der `void` in C# geschrieben und `Nothing` in Visual Basic.|
|[Tupel](tuples.md)|Beschreibt den Tupeltyp, einen Typ, der zugehörigen Werte eines beliebigen Typs gruppiert in Paare, Tripel, Quadrupel usw. besteht.|
|[Optionen](options.md)|Beschreibt den Optionstyp, ein Typ, der möglicherweise entweder einen Wert oder leer sein.|
|[Listen](lists.md)|Beschreibt, Listen, die geordnete, unveränderliche Reihe von Elementen werden alle den gleichen Typ aufweisen.|
|[Arrays](arrays.md)|Beschreibt Arrays, die Sätze von änderbare-Elementen des gleichen Typs sortiert werden, die einen zusammenhängenden Block von Arbeitsspeicher belegen und haben eine feste Größe.|
|[Sequenzen](sequences.md)|Beschreibt die Sequence-Typs, die eine logische Reihe von Werten darstellt. einzelne Werte werden nur nach Bedarf berechnet.|
|[Datensätze](records.md)|Beschreibt den Datensatztyp, ein kleines Aggregat benannter Werte an.|
|[Unterscheidbare Unions](discriminated-unions.md)|Beschreibt den diskriminierten union-Typ, ein Typ, dessen Werte eines eine Gruppe möglicher Typen sein können.|
|[Funktionen](functions/index.md)|Beschreibt Funktionswerte an.|
|[Klassen](classes.md)|Beschreibt den Klassentyp, ein Objekttyp, der ein Verweistyp .NET entspricht. Klassentypen können Member, Eigenschaften, implementierten Schnittstellen und ein Basistyp enthalten.|
|[Strukturen](structures.md)|Beschreibt die `struct` Typ, ein Objekttyp, der einen Werttyp .NET entspricht. Die `struct` Typ in der Regel ein kleines Aggregat von Daten darstellt.|
|[Schnittstellen](interfaces.md)|Beschreibt, Schnittstellentypen, Typen, die eine Menge von Elementen darstellen, die bestimmte Funktionen bereitstellen, aber keine Daten enthalten. Ein Schnittstellentyp muss durch einen Objekttyp, aussagekräftige implementiert werden.|
|[Delegaten](delegates.md)|Beschreibt den Delegattyp, der eine Funktion als ein Objekt darstellt.|
|[Enumerationen](enumerations.md)|Beschreibt, Enumerationstypen,, deren Werte auf einen Satz benannter Werte gehören.|
|[Attribute](attributes.md)|Beschreibt die Attribute, die verwendet werden, um Metadaten für einen anderen Typ angeben.|
|[Ausnahmetypen](exception-handling/exception-types.md)|Beschreibt die Ausnahmen, die Fehlerinformationen angeben.|
