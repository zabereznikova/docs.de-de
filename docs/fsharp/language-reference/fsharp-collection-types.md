---
title: Auflistungstypen
description: 'Erfahren Sie mehr über F #-Auflistungs Typen und deren Unterschiede zu den Sammlungs Typen .net.'
ms.date: 08/14/2020
ms.openlocfilehash: 197ba754d632051b5a0bf9c8364d45a1fb932f48
ms.sourcegitcommit: 0100be20fcf23f61dab672deced70059ed71bb2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/17/2020
ms.locfileid: "88267281"
---
# <a name="f-collection-types"></a>F#-Auflistungstypen

Wenn Sie dieses Thema überprüfen, können Sie bestimmen, welcher F #-Sammlungstyp am besten zu einem bestimmten Bedarf passt. Diese Auflistungs Typen unterscheiden sich von den Auflistungs Typen in .net, wie z. b. denen im- `System.Collections.Generic` Namespace, da die F #-Auflistungs Typen aus funktionaler Programmier Perspektive und nicht aus objektorientierter Sicht entworfen werden. Genauer gesagt hat nur die Array Auflistung änderbare Elemente. Wenn Sie also eine Sammlung ändern, erstellen Sie eine Instanz der geänderten Sammlung, anstatt die ursprüngliche Auflistung zu ändern.

Sammlungs Typen unterscheiden sich auch in dem Typ der Datenstruktur, in der-Objekte gespeichert werden. Datenstrukturen, wie z. b. Hash Tabellen, verknüpfte Listen und Arrays, haben unterschiedliche Leistungsmerkmale und einen anderen Satz verfügbarer Vorgänge.

## <a name="f-collection-types"></a>F#-Auflistungstypen

In der folgenden Tabelle sind die F #-Sammlungs Typen aufgeführt.

|type|BESCHREIBUNG|Verwandte Links|
|----|-----------|-------------|
|[Liste](https://msdn.microsoft.com/library/c627b668-477b-4409-91ed-06d7f1b3e4a7)|Eine geordnete, unveränderliche Reihe von Elementen desselben Typs. Wird als verknüpfte Liste implementiert.|[Listen](lists.md)<br /><br />[List-Modul](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788)|
|[Array](https://msdn.microsoft.com/library/0cda8040-9396-40dd-8dcd-cf48542165a1)|Eine Null basierte, änderbare Auflistung mit fester Größe von aufeinander folgenden Datenelementen, die alle denselben Typ haben.|[Arrays](arrays.md)<br /><br />[Array-Modul](https://msdn.microsoft.com/library/0cda8040-9396-40dd-8dcd-cf48542165a1)<br /><br />[Array2D-Modul](https://msdn.microsoft.com/library/ae1a9746-7817-4430-bcdb-a79c2411bbd3)<br /><br />[Array3D-Modul](https://msdn.microsoft.com/library/c8355e2d-add8-48a4-8aa6-1c57ae74c560)|
|[Seq](https://msdn.microsoft.com/library/2f0c87c6-8a0d-4d33-92a6-10d1d037ce75)|Eine logische Reihe von Elementen, die alle einen Typ haben. Sequenzen sind besonders nützlich, wenn Sie über eine große, geordnete Auflistung von Daten verfügen, aber nicht unbedingt alle Elemente erwarten. Einzelne Sequenz Elemente werden nur bei Bedarf berechnet, sodass eine Sequenz eine bessere Leistung als eine Liste erzielen kann, wenn nicht alle Elemente verwendet werden. Sequenzen werden durch den- `seq<'T>` Typ dargestellt, bei dem es sich um einen Alias für handelt `IEnumerable<T>` . Daher kann jeder .NET Framework Typ, der implementiert, `System.Collections.Generic.IEnumerable<'T>` als Sequenz verwendet werden.|[Sequenzen](sequences.md)<br /><br />[SQ-Modul](https://msdn.microsoft.com/library/54e8f059-ca52-4632-9ae9-49685ee9b684)|
|[Map](https://msdn.microsoft.com/library/975316ea-55e3-4987-9994-90897ad45664)|Ein unveränderliches Wörterbuch von Elementen. Der Zugriff auf Elemente erfolgt über den Schlüssel.|[Map-Modul](https://msdn.microsoft.com/library/bfe61ead-f16c-416f-af98-56dbcbe23e4f)|
|[Set](https://msdn.microsoft.com/library/50cebdce-0cd7-4c5c-8ebc-f3a9e90b38d8)|Eine unveränderliche Gruppe, die auf binären Strukturen basiert, wobei der Vergleich die strukturelle Vergleichsfunktion von F # ist, die potenziell Implementierungen der- `System.IComparable` Schnittstelle für Schlüsselwerte verwendet.|[Modul festlegen](https://msdn.microsoft.com/library/61efa732-d55d-4c32-993f-628e2f98e6a0)|

### <a name="table-of-functions"></a>Tabelle mit Funktionen

In diesem Abschnitt werden die Funktionen verglichen, die für F #-Auflistungs Typen verfügbar sind. Die Rechen Komplexität der Funktion wird angegeben, wobei N die Größe der ersten Auflistung und M die Größe der zweiten Auflistung (sofern vorhanden) ist. Ein Bindestrich (-) gibt an, dass diese Funktion für die Auflistung nicht verfügbar ist. Da Sequenzen verzögert ausgewertet werden, kann eine Funktion wie z. b. "*..." O (1) sein, da Sie sofort zurückgegeben wird, obwohl Sie sich bei der Enumeration weiterhin auf die Leistung der Sequenz auswirkt

|Funktion|Array|List|Sequenz|Karte|Set|BESCHREIBUNG|
|--------|-----|----|--------|---|---|-----------|
|append|O (N)|O (N)|O (N)|-|-|Gibt eine neue Auflistung zurück, die die Elemente der ersten Auflistung gefolgt von Elementen der zweiten Auflistung enthält.|
|add|-|-|-|O (Log (N))|O (Log (N))|Gibt eine neue Auflistung mit dem hinzugefügten Element zurück.|
|average|O (N)|O (N)|O (N)|-|-|Gibt den Durchschnitt der Elemente in der Auflistung zurück.|
|averageBy|O (N)|O (N)|O (N)|-|-|Gibt den Durchschnitt der Ergebnisse der bereitgestellten Funktion zurück, die auf jedes Element angewendet wird.|
|Blit|O (N)|-|-|-|-|Kopiert einen Abschnitt eines Arrays.|
|cache|-|-|O (N)|-|-|Berechnet und speichert Elemente einer Sequenz.|
|Umwandlung|-|-|O (N)|-|-|Konvertiert die Elemente in den angegebenen Typ.|
|choose|O (N)|O (N)|O (N)|-|-|Wendet die angegebene Funktion `f` auf jedes Element `x` der Liste an. Gibt die Liste zurück, die die Ergebnisse für jedes Element enthält, in dem die Funktion zurückgibt `Some(f(x))` .|
|collect|O (N)|O (N)|O (N)|-|-|Wendet die angegebene Funktion auf jedes Element der Auflistung an, verkettet alle Ergebnisse und gibt die kombinierte Liste zurück.|
|compareWith|-|-|O (N)|-|-|Vergleicht zwei Sequenzen mithilfe der angegebenen Vergleichsfunktion, Element by-Element.|
|concat|O (N)|O (N)|O (N)|-|-|Kombiniert die angegebene Enumeration von Enumerationen als einzelne verketteten Enumeration.|
|contains|-|-|-|-|O (Log (N))|Gibt true zurück, wenn der Satz das angegebene Element enthält.|
|ContainsKey|-|-|-|O (Log (N))|-|Testet, ob sich ein Element in der Domäne einer Karte befindet.|
|count|-|-|-|-|O (N)|Gibt die Anzahl der Elemente im Satz zurück.|
|countBy|-|-|O (N)|-|-|Wendet eine Schlüssel generierende Funktion auf jedes Element einer Sequenz an und gibt eine Sequenz zurück, die eindeutige Schlüssel und deren Anzahl von Vorkommen in der ursprünglichen Sequenz ergibt.|
|copy|O (N)|-|O (N)|-|-|Kopiert die Auflistung.|
|create|O (N)|-|-|-|-|Erstellt ein Array ganzer Elemente, die alle anfänglich den angegebenen Wert haben.|
|delay|-|-|O(1)|-|-|Gibt eine Sequenz zurück, die aus der angegebenen verzögerten Spezifikation einer Sequenz erstellt wird.|
|Unterschied|-|-|-|-|O (M \* Protokoll (N))|Gibt einen neuen Satz mit den Elementen des zweiten Satzes zurück, die aus der ersten Menge entfernt wurden.|
|distinct|||O(1)\*|||Gibt eine Sequenz zurück, die keine doppelten Einträge gemäß generischen Hash-und Gleichheits vergleichen für die Einträge enthält. Wenn ein Element mehrmals in der Sequenz auftritt, werden spätere Vorkommen verworfen.|
|distinctBy|||O(1)\*|||Gibt eine Sequenz zurück, die keine doppelten Einträge gemäß den generischen Hash-und Gleichheits vergleichen für die Schlüssel enthält, die die angegebene Schlüssel generierende Funktion zurückgibt. Wenn ein Element mehrmals in der Sequenz auftritt, werden spätere Vorkommen verworfen.|
|empty|O(1)|O(1)|O(1)|O(1)|O(1)|Erstellt eine leere Auflistung.|
|exists|O (N)|O (N)|O (N)|O (Log (N))|O (Log (N))|Testet, ob ein Element der Sequenz das angegebene Prädikat erfüllt.|
|exists2|O (min (N, M))|-|O (min (N, M))|||Testet, ob ein paar entsprechender Elemente der Eingabe Sequenzen dem angegebenen Prädikat entspricht.|
|fill|O (N)|||||Legt einen Bereich von Elementen des Arrays auf den angegebenen Wert fest.|
|filter|O (N)|O (N)|O (N)|O (N)|O (N)|Gibt eine neue Auflistung zurück, die nur die Elemente der Auflistung enthält, für die das angegebene Prädikat zurückgibt `true` .|
|Suchen|O (N)|O (N)|O (N)|O (Log (N))|-|Gibt das erste Element zurück, für das die angegebene Funktion zurückgibt `true` . Gibt zurück, `System.Collections.Generic.KeyNotFoundException` Wenn kein solches Element vorhanden ist.|
|FindIndex|O (N)|O (N)|O (N)|-|-|Gibt den Index des ersten Elements im Array zurück, das das angegebene Prädikat erfüllt. Wird ausgelöst, `System.Collections.Generic.KeyNotFoundException` Wenn kein Element das Prädikat erfüllt.|
|FindKey|-|-|-|O (Log (N))|-|Wertet die-Funktion für jede Zuordnung in der Auflistung aus und gibt den Schlüssel für die erste Zuordnung zurück, in der die Funktion zurückgibt `true` . Wenn kein solches Element vorhanden ist, löst diese Funktion aus `System.Collections.Generic.KeyNotFoundException` .|
|Fold|O (N)|O (N)|O (N)|O (N)|O (N)|Wendet eine Funktion auf jedes Element der Auflistung an, wobei ein akkumulatorargument durch die Berechnung Threading. Wenn die Eingabe Funktion f ist und die Elemente i0... iN berechnet diese Funktion f (... (f s I0)...) iN.|
|fold2|O (N)|O (N)|-|-|-|Wendet eine Funktion auf die entsprechenden Elemente von zwei Auflistungen an, wobei ein akkumulatorargument durch die Berechnung Threading. Die Auflistungen müssen dieselbe Größe aufweisen. Wenn die Eingabe Funktion f ist und die Elemente i0... iN und j0... jN, diese Funktion berechnet f (... (f s I0 J0)...) iN Joh.|
|Foldback|O (N)|O (N)|-|O (N)|O (N)|Wendet eine Funktion auf jedes Element der Auflistung an, wobei ein akkumulatorargument durch die Berechnung Threading. Wenn die Eingabe Funktion f ist und die Elemente i0... iN berechnet diese Funktion f i0 (... (f in s)).|
|foldBack2|O (N)|O (N)|-|-|-|Wendet eine Funktion auf die entsprechenden Elemente von zwei Auflistungen an, wobei ein akkumulatorargument durch die Berechnung Threading. Die Auflistungen müssen dieselbe Größe aufweisen. Wenn die Eingabe Funktion f ist und die Elemente i0... iN und j0... jN, diese Funktion berechnet f i0 j0 (... (f in Joh s)).|
|ForAll|O (N)|O (N)|O (N)|O (N)|O (N)|Testet, ob alle Elemente der Auflistung das angegebene Prädikat erfüllen.|
|forall2|O (N)|O (N)|O (N)|-|-|Testet, ob alle entsprechenden Elemente der Auflistung das angegebene Prädikat paarweise erfüllen.|
|Get/ten|O(1)|O (N)|O (N)|-|-|Gibt ein Element aus der Auflistung zurück, wenn der Index angegeben ist.|
|head|-|O(1)|O(1)|-|-|Gibt das erste Element der Auflistung zurück.|
|init|O (N)|O (N)|O(1)|-|-|Erstellt eine Auflistung mit der angegebenen Dimension und einer Generatorfunktion, um die Elemente zu berechnen.|
|initInfinite|-|-|O(1)|-|-|Generiert eine Sequenz, die beim Durchlaufen aufeinander folgende Elemente zurückgibt, indem die angegebene Funktion aufgerufen wird.|
|intersect|-|-|-|-|O (Protokoll (N) \* Log (M))|Berechnet die Schnittmenge von zwei Sätzen.|
|IntersectMany|-|-|-|-|O (N1 \* N2...)|Berechnet die Schnittmenge einer Sequenz von Sätzen. Die Sequenz darf nicht leer sein.|
|isEmpty|O(1)|O(1)|O(1)|O(1)|-|Gibt zurück, `true` Wenn die Auflistung leer ist.|
|IsProperSubset|-|-|-|-|O (M \* Protokoll (N))|Gibt zurück `true` , wenn alle Elemente der ersten Menge in der zweiten Menge sind und mindestens ein Element der zweiten Menge nicht in der ersten Menge ist.|
|IsProperSuperset|-|-|-|-|O (M \* Protokoll (N))|Gibt zurück `true` , wenn alle Elemente der zweiten Menge in der ersten Menge sind und mindestens ein Element der ersten Menge nicht in der zweiten Menge ist.|
|IsSubset|-|-|-|-|O (M \* Protokoll (N))|Gibt zurück, `true` Wenn alle Elemente der ersten Menge in der zweiten Menge sind.|
|IsSuperset|-|-|-|-|O (M \* Protokoll (N))|Gibt zurück, `true` Wenn alle Elemente der zweiten Menge in der ersten Menge sind.|
|verstärkt|O (N)|O (N)|O (N)|O (N)|O (N)|Wendet die angegebene Funktion auf jedes Element der Auflistung an.|
|iteri|O (N)|O (N)|O (N)|-|-|Wendet die angegebene Funktion auf jedes Element der Auflistung an. Die ganze Zahl, die an die Funktion übermittelt wird, gibt den Index des Elements an.|
|iteri2|O (N)|O (N)|-|-|-|Wendet die angegebene Funktion auf ein paar von Elementen an, die aus übereinstimmenden Indizes in zwei Arrays gezeichnet werden. Die ganze Zahl, die an die Funktion übermittelt wird, gibt den Index der Elemente an. Die beiden Arrays müssen die gleiche Länge aufweisen.|
|iter2|O (N)|O (N)|O (N)|-|-|Wendet die angegebene Funktion auf ein paar von Elementen an, die aus übereinstimmenden Indizes in zwei Arrays gezeichnet werden. Die beiden Arrays müssen die gleiche Länge aufweisen.|
|last|O(1)|O (N)|O (N)|-|-|Gibt das letzte Element in der anwendbaren Auflistung zurück.|
|length|O(1)|O (N)|O (N)|-|-|Gibt die Anzahl der Elemente in der Auflistung zurück.|
|map|O (N)|O (N)|O(1)|-|-|Erstellt eine Auflistung, deren Elemente die Ergebnisse der Anwendung der angegebenen Funktion auf die einzelnen Elemente des Arrays sind.|
|map2|O (N)|O (N)|O(1)|-|-|Erstellt eine Auflistung, deren Elemente das Ergebnis der Anwendung der angegebenen Funktion auf die entsprechenden Elemente der beiden Auflistungen sind. Die beiden Eingabe Arrays müssen die gleiche Länge aufweisen.|
|map3|-|O (N)|-|-|-|Erstellt eine Auflistung, deren Elemente die Ergebnisse der gleichzeitigen Anwendung der angegebenen Funktion auf die entsprechenden Elemente der drei Auflistungen sind.|
|MAPI|O (N)|O (N)|O (N)|-|-|Erstellt ein Array, dessen Elemente die Ergebnisse der Anwendung der angegebenen Funktion auf die einzelnen Elemente des Arrays sind. Der ganzzahlige Index, der an die Funktion übermittelt wird, gibt den Index des zu transformierenden Elements an.|
|mapi2|O (N)|O (N)|-|-|-|Erstellt eine Auflistung, deren Elemente das Ergebnis der Anwendung der angegebenen Funktion auf die entsprechenden Elemente der beiden Auflistungen sind, und übergibt auch den Index der Elemente. Die beiden Eingabe Arrays müssen die gleiche Länge aufweisen.|
|max|O (N)|O (N)|O (N)|-|-|Gibt das größte Element in der Auflistung zurück, verglichen mit dem [Max](https://msdn.microsoft.com/library/9a988328-00e9-467b-8dfa-e7a6990f6cce) -Operator.|
|maxBy|O (N)|O (N)|O (N)|-|-|Gibt das größte Element in der Auflistung zurück, verglichen mit [Max](https://msdn.microsoft.com/library/9a988328-00e9-467b-8dfa-e7a6990f6cce) im Funktionsergebnis.|
|maxElement|-|-|-|-|O (Log (N))|Gibt das größte Element in der Menge entsprechend der Reihenfolge zurück, die für die Menge verwendet wird.|
|Min.|O (N)|O (N)|O (N)|-|-|Gibt das kleinste Element in der Auflistung zurück, verglichen mit dem [Min](https://msdn.microsoft.com/library/adea4fd7-bfad-4834-989c-7878aca81fed) -Operator.|
|minBy|O (N)|O (N)|O (N)|-|-|Gibt das kleinste Element in der Auflistung zurück, verglichen mit dem [Min](https://msdn.microsoft.com/library/adea4fd7-bfad-4834-989c-7878aca81fed) -Operator für das Ergebnis der Funktion.|
|minElement|-|-|-|-|O (Log (N))|Gibt das niedrigste Element im Satz entsprechend der für den Satz verwendeten Reihenfolge zurück.|
|ofArray|-|O (N)|O(1)|O (N)|O (N)|Erstellt eine Auflistung, die die gleichen Elemente wie das angegebene Array enthält.|
|ofList|O (N)|-|O(1)|O (N)|O (N)|Erstellt eine Auflistung, die die gleichen Elemente wie die angegebene Liste enthält.|
|ofSeq|O (N)|O (N)|-|O (N)|O (N)|Erstellt eine Auflistung, die die gleichen Elemente wie die angegebene Sequenz enthält.|
|paar weisen|-|-|O (N)|-|-|Gibt eine Sequenz der einzelnen Elemente in der Eingabe Sequenz und deren Vorgänger zurück, mit Ausnahme des ersten Elements, das nur als Vorgänger des zweiten Elements zurückgegeben wird.|
|partition|O (N)|O (N)|-|O (N)|O (N)|Teilt die Auflistung in zwei Auflistungen auf. Die erste Auflistung enthält die Elemente, für die das angegebene Prädikat zurückgibt `true` , und die zweite Auflistung enthält die Elemente, für die das angegebene Prädikat zurückgibt `false` .|
|permute|O (N)|O (N)|-|-|-|Gibt ein Array mit allen Elementen zurück, die gemäß der angegebenen Permutation permutiert wurden.|
|Suchen|O (N)|O (N)|O (N)|O (Log (N))|-|Wendet die angegebene Funktion auf aufeinander folgende Elemente an und gibt das erste Ergebnis zurück, bei dem die Funktion einige zurückgibt. Wenn die Funktion nie einige zurückgibt, `System.Collections.Generic.KeyNotFoundException` wird ausgelöst.|
|readonly|-|-|O (N)|-|-|Erstellt ein Sequenz Objekt, das an das angegebene Sequenz Objekt delegiert. Mit diesem Vorgang wird sichergestellt, dass eine Typumwandlung die ursprüngliche Sequenz nicht wiederentdecken und verändern kann. Wenn z. b. ein Array angegeben wird, gibt die zurückgegebene Sequenz die Elemente des Arrays zurück, aber Sie können das zurückgegebene Sequenz Objekt nicht in ein Array umwandeln.|
|reduce|O (N)|O (N)|O (N)|-|-|Wendet eine Funktion auf jedes Element der Auflistung an, wobei ein akkumulatorargument durch die Berechnung Threading. Diese Funktion beginnt, indem Sie die-Funktion auf die ersten beiden Elemente anwendet, das Ergebnis zusammen mit dem dritten Element an die Funktion übergibt usw. Die-Funktion gibt das Endergebnis zurück.|
|reduceBack|O (N)|O (N)|-|-|-|Wendet eine Funktion auf jedes Element der Auflistung an, wobei ein akkumulatorargument durch die Berechnung Threading. Wenn die Eingabe Funktion f ist und die Elemente i0... iN berechnet diese Funktion f i0 (... (f in-1 in)).|
|remove|-|-|-|O (Log (N))|O (Log (N))|Entfernt ein Element aus der Domäne der Zuordnung. Wenn das Element nicht vorhanden ist, wird keine Ausnahme ausgelöst.|
|replizieren|-|O (N)|-|-|-|Erstellt eine Liste mit einer angegebenen Länge, wobei jedes Element auf den angegebenen Wert festgelegt ist.|
|6,9|O (N)|O (N)|-|-|-|Gibt eine neue Liste mit den Elementen in umgekehrter Reihenfolge zurück.|
|fein|O (N)|O (N)|O (N)|-|-|Wendet eine Funktion auf jedes Element der Auflistung an, wobei ein akkumulatorargument durch die Berechnung Threading. Mit diesem Vorgang wird die-Funktion auf das zweite Argument und das erste Element der Liste angewendet. Der Vorgang übergibt dann dieses Ergebnis zusammen mit dem zweiten Element an die Funktion usw. Schließlich gibt der Vorgang die Liste der Zwischenergebnisse und das Endergebnis zurück.|
|scanBack|O (N)|O (N)|-|-|-|Ähnelt dem foldBack-Vorgang, gibt jedoch die zwischen-und Endergebnisse zurück.|
|singleton|-|-|O(1)|-|O(1)|Gibt eine Sequenz zurück, die nur ein Element ergibt.|
|set|O(1)|-|-|-|-|Legt ein Element eines Arrays auf den angegebenen Wert fest.|
|skip|-|-|O (N)|-|-|Gibt eine Sequenz zurück, die N Elemente der zugrunde liegenden Sequenz überspringt und dann die restlichen Elemente der Sequenz ergibt.|
|SkipWhile|-|-|O (N)|-|-|Gibt eine Sequenz zurück, die beim Durchlaufen Elemente der zugrunde liegenden Sequenz überspringt, während das angegebene Prädikat zurückgegeben wird, `true` und dann die restlichen Elemente der Sequenz ergibt.|
|sort|E (n \* ) Durchschnitt (n)<br /><br />O (N ^ 2) Ungünstigster Fall|O (n \* Log (n))|O (n \* Log (n))|-|-|Sortiert die Auflistung nach Elementwert. Elemente werden mithilfe von [Compare](https://msdn.microsoft.com/library/295e1320-0955-4c3d-ac31-288fa80a658c)verglichen.|
|sortBy|E (n \* ) Durchschnitt (n)<br /><br />O (N ^ 2) Ungünstigster Fall|O (n \* Log (n))|O (n \* Log (n))|-|-|Sortiert die angegebene Liste mithilfe von Schlüsseln, die von der angegebenen Projektion bereitgestellt werden. Schlüssel werden mithilfe von [Compare](https://msdn.microsoft.com/library/295e1320-0955-4c3d-ac31-288fa80a658c)verglichen.|
|sortInPlace|E (n \* ) Durchschnitt (n)<br /><br />O (N ^ 2) Ungünstigster Fall|-|-|-|-|Sortiert die Elemente eines Arrays durch eine muteweise und Verwendung der angegebenen Vergleichsfunktion. Elemente werden mithilfe von [Compare](https://msdn.microsoft.com/library/295e1320-0955-4c3d-ac31-288fa80a658c)verglichen.|
|SortInPlaceBy|E (n \* ) Durchschnitt (n)<br /><br />O (N ^ 2) Ungünstigster Fall|-|-|-|-|Sortiert die Elemente eines Arrays durch eine muteweise und Verwendung der angegebenen Projektion für die Schlüssel. Elemente werden mithilfe von [Compare](https://msdn.microsoft.com/library/295e1320-0955-4c3d-ac31-288fa80a658c)verglichen.|
|sortInPlaceWith|E (n \* ) Durchschnitt (n)<br /><br />O (N ^ 2) Ungünstigster Fall|-|-|-|-|Sortiert die Elemente eines Arrays, indem es an der Stelle geändert und die angegebene Vergleichsfunktion als Reihenfolge verwendet wird.|
|sortWith|E (n \* ) Durchschnitt (n)<br /><br />O (N ^ 2) Ungünstigster Fall|O (n \* Log (n))|-|-|-|Sortiert die Elemente einer Auflistung, wobei die angegebene Vergleichsfunktion als Reihenfolge verwendet und eine neue Auflistung zurückgegeben wird.|
|sub|O (N)|-|-|-|-|Erstellt ein Array, das den angegebenen Unterbereich enthält, der durch Start Index und length angegeben wird.|
|Sum|O (N)|O (N)|O (N)|-|-|Gibt die Summe der Elemente in der Auflistung zurück.|
|sumBy|O (N)|O (N)|O (N)|-|-|Gibt die Summe der Ergebnisse zurück, die durch Anwenden der-Funktion auf jedes Element der Auflistung generiert werden.|
|Rohr|-|O(1)|-|-|-|Gibt die Liste ohne das erste Element zurück.|
|take|-|-|O (N)|-|-|Gibt die Elemente der Sequenz bis zu einer angegebenen Anzahl zurück.|
|TakeWhile|-|-|O(1)|-|-|Gibt eine Sequenz zurück, die beim Durchlaufen Elemente der zugrunde liegenden Sequenz ergibt, während das angegebene Prädikat zurückgibt `true` und dann keine weiteren Elemente zurückgibt.|
|ToArray|-|O (N)|O (N)|O (N)|O (N)|Erstellt ein Array aus der angegebenen Auflistung.|
|ToList|O (N)|-|O (N)|O (N)|O (N)|Erstellt eine Liste aus der angegebenen Auflistung.|
|toSeq|O(1)|O(1)|-|O(1)|O(1)|Erstellt eine Sequenz aus der angegebenen Auflistung.|
|truncate|-|-|O(1)|-|-|Gibt eine Sequenz zurück, die bei der Enumeration nicht mehr als N Elemente zurückgibt.|
|TryFind|O (N)|O (N)|O (N)|O (Log (N))|-|Sucht nach einem Element, das ein angegebenes Prädikat erfüllt.|
|tryFindIndex|O (N)|O (N)|O (N)|-|-|Sucht nach dem ersten Element, das ein angegebenes Prädikat erfüllt, und gibt den Index des übereinstimmenden Elements oder zurück, `None` Wenn kein solches Element vorhanden ist.|
|tryFindKey|-|-|-|O (Log (N))|-|Gibt den Schlüssel der ersten Zuordnung in der Auflistung zurück, die das angegebene Prädikat erfüllt, oder gibt zurück, `None` Wenn kein solches Element vorhanden ist.|
|tryPick|O (N)|O (N)|O (N)|O (Log (N))|-|Wendet die angegebene Funktion auf aufeinander folgende Elemente an und gibt das erste Ergebnis zurück, bei dem die Funktion `Some` einen Wert zurückgibt. Wenn kein solches Element vorhanden ist, gibt der Vorgang zurück `None` .|
|Erweitern|-|-|O (N)|-|-|Gibt eine Sequenz zurück, die die Elemente enthält, die durch die angegebene Berechnung generiert werden.|
|union|-|-|-|-|O (M \* Protokoll (N))|Berechnet die Union der beiden Sätze.|
|unionMany|-|-|-|-|O (N1 \* N2...)|Berechnet die Vereinigung einer Sequenz von Sätzen.|
|unzip|O (N)|O (N)|O (N)|-|-|Unterteilt eine Liste von Paaren in zwei Listen.|
|unzip3|O (N)|O (N)|O (N)|-|-|Teilt eine Liste von dreieln in drei Listen auf.|
|Fenster|-|-|O (N)|-|-|Gibt eine Sequenz zurück, die gleitende Fenster mit Elementen ergibt, die aus der Eingabe Sequenz gezeichnet werden. Jedes Fenster wird als ein neues Array zurückgegeben.|
|zip|O (N)|O (N)|O (N)|-|-|Kombiniert die beiden Auflistungen in einer Liste von Paaren. Die beiden Listen müssen die gleiche Länge aufweisen.|
|zip3|O (N)|O (N)|O (N)|-|-|Kombiniert die drei Auflistungen in einer Liste von dreieln. Die Listen müssen die gleiche Länge aufweisen.|

## <a name="see-also"></a>Weitere Informationen

- [F#-Typen](fsharp-types.md)
- [F#-Sprachreferenz](index.md)
