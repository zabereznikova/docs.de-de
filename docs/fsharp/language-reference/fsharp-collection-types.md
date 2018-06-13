---
title: F#-Auflistungstypen
description: Informationen Sie zu f#-Auflistungstypen und Unterschieden gegenüber Auflistungstypen in .NET Framework.
ms.date: 05/16/2016
ms.openlocfilehash: a94dc300d984ca31baf1eb7d1073e23b51ebd030
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33566846"
---
# <a name="f-collection-types"></a>F#-Auflistungstypen

Anhand der in diesem Thema können Sie bestimmen, welche F#-Auflistungstyp bewährte eine bestimmte Situation geeignet ist. Diese Auflistungstypen unterscheiden sich von der Auflistungstypen in .NET Framework, z. B. die in der `System.Collections.Generic` -Namespace, die f#-Auflistungstypen aus der funktionalen Programmierung her, anstatt eine Perspektive mit dem objektorientierten vorgesehen sind. Genauer gesagt, ist nur für die Sammlung der Array änderbare Elemente. Aus diesem Grund, wenn Sie eine Auflistung ändern, erstellen Sie eine Instanz der geänderten Auflistung anstelle die ursprüngliche Auflistung ändern.

Auflistungstypen unterscheiden sich auch in den Typ der Datenstruktur, die in dem Objekte gespeichert werden. Datenstrukturen wie Hashtabellen, verknüpfte Listen und Arrays haben unterschiedlichen Leistungsmerkmalen und einen anderen Satz der verfügbaren Vorgänge aus.


## <a name="f-collection-types"></a>F#-Auflistungstypen
Die folgende Tabelle zeigt die f#-Auflistungstypen.



|Typ|Beschreibung|Verwandte Links|
|----|-----------|-------------|
|[List](https://msdn.microsoft.com/library/c627b668-477b-4409-91ed-06d7f1b3e4a7)|Eine geordnete, unveränderliche Reihe von Elementen des gleichen Typs. Implementiert eine verknüpfte Liste.|[Listen](lists.md)<br /><br />[List-Modul](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788)|
|[Array](https://msdn.microsoft.com/library/0cda8040-9396-40dd-8dcd-cf48542165a1)|Eine nullbasierte, änderbare Sequenzen fester Größe der Auflistung von aufeinander folgenden Datenelementen, die alle vom selben Typ sind.|[Arrays](arrays.md)<br /><br />[Array-Modul](https://msdn.microsoft.com/library/0cda8040-9396-40dd-8dcd-cf48542165a1)<br /><br />[Array2D-Modul](https://msdn.microsoft.com/library/ae1a9746-7817-4430-bcdb-a79c2411bbd3)<br /><br />[Array3D-Modul](https://msdn.microsoft.com/library/c8355e2d-add8-48a4-8aa6-1c57ae74c560)|
|[Seq](https://msdn.microsoft.com/library/2f0c87c6-8a0d-4d33-92a6-10d1d037ce75)|Eine logische Reihe von Elementen, die alle vom selben Typ sind. Sequenzen sind besonders nützlich, wenn Sie über eine große geordnete Auflistung von Daten reicht jedoch nicht notwendigerweise erwarten, dass alle Elemente zu verwenden. Einzelne Sequenz, die Elemente, nur als berechnet werden erforderlich, damit eine Sequenz kann eine bessere Leistung als eine Liste, wenn nicht alle Elemente werden verwendet. Sequenzen werden dargestellt, indem die `seq<'T>` Typ, der einen Alias für `IEnumerable<T>`. Aus diesem Grund alle .NET Framework-Typ, der implementiert `System.Collections.Generic.IEnumerable<'T>` als Sequenz verwendet werden können.|[Sequenzen](sequences.md)<br /><br />[Seq-Modul](https://msdn.microsoft.com/library/54e8f059-ca52-4632-9ae9-49685ee9b684)|
|[Zuordnung](https://msdn.microsoft.com/library/975316ea-55e3-4987-9994-90897ad45664)|Ein unveränderliches Wörterbuch von Elementen. Elemente werden über Schlüssel zugegriffen werden.|[Map-Modul](https://msdn.microsoft.com/library/bfe61ead-f16c-416f-af98-56dbcbe23e4f)|
|[Set](https://msdn.microsoft.com/library/50cebdce-0cd7-4c5c-8ebc-f3a9e90b38d8)|Eine unveränderliche Gruppe, die auf binären Strukturen basieren, in dem Vergleich die F#-strukturvergleichsfunktion erfolgt-Funktion wird, potenziell Implementierungen von verwendet die `System.IComparable` -Schnittstelle für Schlüsselwerte.|[Set-Moduls](https://msdn.microsoft.com/library/61efa732-d55d-4c32-993f-628e2f98e6a0)|

### <a name="table-of-functions"></a>Tabelle von Funktionen
In diesem Abschnitt vergleicht die Funktionen, die für f#-Auflistungstypen verfügbar sind. Die Komplexität der Berechnung der Funktion wird angegeben, wobei N die Größe der FIFO-Auflistung, und M ist die Größe der zweiten Sammlung aus, falls vorhanden. Ein Bindestrich (-) gibt an, dass diese Funktion nicht in der Auflistung verfügbar ist. Da Sequenzen verzögert ausgewertet werden, eine Funktion, z. B. Seq.distinct O(1) möglicherweise daran, dass wird sofort zurückgegeben, obwohl es weiterhin die Leistung der Sequenz bei der Enumeration beeinflusst.



|Funktion|Array|Liste|Sequenz|Zuordnung|Set|Beschreibung|
|--------|-----|----|--------|---|---|-----------|
|append|O(M)|O(N)|O(N)|-|-|Gibt eine neue Auflistung, die die Elemente der ersten Sammlung gefolgt von der zweiten Auflistung Elemente enthält.|
|Hinzufügen|-|-|-|O (Log N)|O (Log N)|Gibt eine neue Sammlung mit dem hinzugefügten Element zurück.|
|Durchschnitt|O(N)|O(N)|O(N)|-|-|Gibt den Durchschnitt der Elemente in der Auflistung zurück.|
|averageBy|O(N)|O(N)|O(N)|-|-|Gibt den Durchschnitt der Ergebnisse der die angegebene Funktion auf jedes Element angewendet.|
|blit|O(N)|-|-|-|-|Kopiert einen Abschnitt eines Arrays.|
|Cache|-|-|O(N)|-|-|Berechnet und speichert die Elemente einer Sequenz.|
|Umwandlung|-|-|O(N)|-|-|Konvertiert die Elemente in den angegebenen Typ.|
|Wählen Sie|O(N)|O(N)|O(N)|-|-|Wendet die angegebene Funktion `f` auf jedes Element `x` der Liste. Gibt die Liste, die die Ergebnisse für jedes Element enthält, in dem die Funktion gibt `Some(f(x))`.|
|Sammeln|O(N)|O(N)|O(N)|-|-|Wendet die angegebene Funktion auf jedes Element der Auflistung verkettet alle Ergebnisse und gibt die kombinierte Liste zurück.|
|compareWith|-|-|O(N)|-|-|Vergleicht zwei Sequenzen unter Verwendung der angegebenen Vergleichsfunktion elementweise an.|
|concat|O(N)|O(N)|O(N)|-|-|Kombiniert die angegebenen Enumeration von Enumerationen als eine einzelne verketteten-Enumeration.|
|enthält|-|-|-|-|O (Log N)|Gibt true zurück, wenn der Satz das angegebene Element enthält.|
|containsKey|-|-|-|O (Log N)|-|Testet, ob ein Element in der Domäne einer Zuordnung.|
|count|-|-|-|-|O(N)|Gibt die Anzahl der Elemente im Satz zurück.|
|countBy|-|-|O(N)|-|-|Wendet eine Funktion auf jedes Element einer Sequenz und gibt eine Sequenz, die eindeutige Schlüssel und deren Anzahl von Vorkommen in der ursprünglichen Sequenz ergibt.|
|copy|O(N)|-|O(N)|-|-|Kopiert die Auflistung.|
|Erstellen|O(N)|-|-|-|-|Erstellt ein Array von ganzen Elementen, die alle dem angegebenen Wert haben.|
|Verzögerung|-|-|O(1)|-|-|Gibt eine Sequenz, die erstellt wird aus der angegebenen verzögerten Spezifikation einer Sequenz zurück.|
|Unterschied|-|-|-|-|O (M &#42; Log N)|Gibt einen neuen Satz mit den Elementen des zweiten Satzes aus dem ersten Satz entfernt.|
|DISTINCT|||O(1)&AMP;#42;|||Gibt eine Sequenz, die keine doppelten Einträge entsprechend generischen Hash- und Gleichheitsvergleichen Vergleiche für die Einträge enthält. Wenn ein Element in der Sequenz mehrfach auftritt, werden nachfolgende Vorkommen verworfen.|
|distinctBy|||O(1)&AMP;#42;|||Gibt eine Sequenz, die keine doppelten Einträge entsprechend die generischen Hash- und Gleichheitsvergleichen Vergleiche auf die Schlüssel enthält, die die angegebene Funktion zurückgibt. Wenn ein Element in der Sequenz mehrfach auftritt, werden nachfolgende Vorkommen verworfen.|
|Leer|O(1)|O(1)|O(1)|O(1)|O(1)|Erstellt eine leere Auflistung.|
|exists|O(N)|O(N)|O(N)|O (Log N)|O (Log N)|Testet, ob ein Element der Sequenz das angegebene Prädikat erfüllt.|
|exists2|O(min(N,M))|-|O(min(N,M))|||Testet, ob ein beliebiges Paar entsprechender Elemente der Eingabesequenzen das angegebene Prädikat erfüllt.|
|fill|O(N)|||||Legt einen Bereich von Elementen im Array auf den angegebenen Wert fest.|
|Filter|O(N)|O(N)|O(N)|O(N)|O(N)|Gibt eine neue Auflistung, die nur die Elemente der Auflistung enthält, für die das angegebene Prädikat wieder `true`.|
|find|O(N)|O(N)|O(N)|O (Log N)|-|Gibt das erste Element, das für die angegebene Funktion zurückgibt `true`. Gibt `System.Collections.Generic.KeyNotFoundException` Wenn kein solches Element vorhanden ist.|
|findIndex|O(N)|O(N)|O(N)|-|-|Gibt den Index des ersten Elements im Array, das das angegebene Prädikat erfüllt. Löst `System.Collections.Generic.KeyNotFoundException` Wenn kein Element das Prädikat erfüllt.|
|findKey|-|-|-|O (Log N)|-|Wertet die Funktion für jede Zuordnung in der Auflistung und gibt den Schlüssel für die erste Zuordnung zurück, in dem die Funktion gibt `true`. Wenn kein solches Element vorhanden ist, löst diese Funktion `System.Collections.Generic.KeyNotFoundException`.|
|fold-|O(N)|O(N)|O(N)|O(N)|O(N)|Wendet eine Funktion auf jedes Element der Auflistung ein Akkumulatorargument über die Berechnung an. Wenn die Eingabefunktion f und die Elemente i0... iN sind, berechnet dieser Funktion f (...) (f s i0)...) iN.|
|fold2|O(N)|O(N)|-|-|-|Wendet eine Funktion auf den entsprechenden Elementen von zwei Auflistungen, die ein Akkumulatorargument über die Berechnung an. Die Auflistungen müssen identische Größen aufweisen. Wenn die Eingabefunktion f und die Elemente i0... iN und j0 sind... berechnet jN, diese Funktion f (...) (f s i0 j0)...) iN jN.|
|foldBack|O(N)|O(N)|-|O(N)|O(N)|Wendet eine Funktion auf jedes Element der Auflistung ein Akkumulatorargument über die Berechnung an. Wenn die Eingabefunktion f und die Elemente i0... iN sind, berechnet dieser Funktion f i0 (...) (f iN s)).|
|foldBack2|O(N)|O(N)|-|-|-|Wendet eine Funktion auf den entsprechenden Elementen von zwei Auflistungen, die ein Akkumulatorargument über die Berechnung an. Die Auflistungen müssen identische Größen aufweisen. Wenn die Eingabefunktion f und die Elemente i0... iN und j0 sind... berechnet jN, diese Funktion f i0 j0 (...) (f jN s)).|
|ForAll|O(N)|O(N)|O(N)|O(N)|O(N)|Testet, ob alle Elemente der Auflistung das angegebene Prädikat erfüllen.|
|forall2|O(N)|O(N)|O(N)|-|-|Testet, ob alle zugehörigen Elemente der Auflistung das angegebene Prädikat paarweise erfüllen.|
|Abrufen / n-te|O(1)|O(N)|O(N)|-|-|Gibt ein Element aus der Auflistung, wenn dessen Index zurück.|
|Kopf|-|O(1)|O(1)|-|-|Gibt das erste Element der Auflistung zurück.|
|init|O(N)|O(N)|O(1)|-|-|Erstellt eine Auflistung, erhält der Dimension und einer Generatorfunktion, mit die Elemente berechnet.|
|initInfinite|-|-|O(1)|-|-|Generiert eine Sequenz, die beim Durchlaufen aufeinander folgende Elemente zurückgibt, durch die angegebene Funktion aufrufen.|
|Intersect|-|-|-|-|O (Log N &#42; Protokoll M)|Berechnet die Schnittmenge zweier Mengen.|
|intersectMany|-|-|-|-|O (N1 &AMP;#42; N2...)|Berechnet die Schnittmenge einer Sequenz von Sätzen. Die Sequenz darf nicht leer sein.|
|IsEmpty|O(1)|O(1)|O(1)|O(1)|-|Gibt `true` , wenn die Auflistung leer ist.|
|isProperSubset|-|-|-|-|O (M &#42; Log N)|Gibt `true` , wenn alle Elemente der ersten Menge in der zweiten Menge enthalten sind und mindestens ein Element der zweiten Menge nicht in der ersten Menge.|
|isProperSuperset|-|-|-|-|O (M &#42; Log N)|Gibt `true` , wenn alle Elemente der zweiten Menge in der ersten Menge enthalten sind und mindestens ein Element der ersten Menge nicht in der zweiten Menge.|
|isSubset|-|-|-|-|O (M &#42; Log N)|Gibt `true` Wenn alle Elemente der ersten Menge in der zweiten Menge sind.|
|isSuperset|-|-|-|-|O (M &#42; Log N)|Gibt `true` , wenn alle Elemente des zweiten Satzes im ersten Satz enthalten sind.|
|iter|O(N)|O(N)|O(N)|O(N)|O(N)|Wendet die angegebene Funktion auf jedes Element der Auflistung an.|
|iteri|O(N)|O(N)|O(N)|-|-|Wendet die angegebene Funktion auf jedes Element der Auflistung an. Die ganze Zahl, die an die Funktion übergeben wird, gibt den Index des Elements an.|
|iteri2|O(N)|O(N)|-|-|-|Wendet die angegebene Funktion auf ein Paar von Elementen, die von übereinstimmenden Indizes in zwei Arrays gezeichnet werden. Die ganze Zahl, die an die Funktion übergeben wird, gibt den Index der Elemente an. Beide Arrays müssen dieselbe Länge haben.|
|iter2|O(N)|O(N)|O(N)|-|-|Wendet die angegebene Funktion auf ein Paar von Elementen, die von übereinstimmenden Indizes in zwei Arrays gezeichnet werden. Beide Arrays müssen dieselbe Länge haben.|
|Länge|O(1)|O(N)|O(N)|-|-|Gibt die Anzahl der Elemente in der Auflistung zurück.|
|Zuordnung|O(N)|O(N)|O(1)|-|-|Erstellt eine Auflistung, deren Elemente das Ergebnis der wendet die angegebene Funktion auf jedes Element des Arrays sind.|
|map2|O(N)|O(N)|O(1)|-|-|Erstellt eine Auflistung, deren Elemente das Ergebnis der paarweise wendet die angegebene Funktion auf die entsprechenden Elemente der beiden Auflistungen sind. Die zwei Eingabearrays müssen dieselbe Länge haben.|
|map3|-|O(N)|-|-|-|Erstellt eine Auflistung, deren Elemente das Ergebnis der gleichzeitig wendet die angegebene Funktion auf die entsprechenden Elemente der drei Auflistungen sind.|
|MAPI|O(N)|O(N)|O(N)|-|-|Erstellt ein Array, dessen Elemente das Ergebnis der wendet die angegebene Funktion auf jedes Element des Arrays sind. Der ganzzahlige Index, der an die Funktion übergeben wird, gibt den Index des Elements, das transformiert wird, an.|
|mapi2|O(N)|O(N)|-|-|-|Erstellt eine Auflistung, deren Elemente das Ergebnis der wendet die angegebene Funktion auf die entsprechenden Elemente der beiden Auflistungen paarweisen, übergibt den Index der Elemente sind. Die zwei Eingabearrays müssen dieselbe Länge haben.|
|max|O(N)|O(N)|O(N)|-|-|Gibt das größte Element in der Auflistung, die im Vergleich mit der [max](https://msdn.microsoft.com/library/9a988328-00e9-467b-8dfa-e7a6990f6cce) Operator.|
|maxBy|O(N)|O(N)|O(N)|-|-|Gibt das größte Element in der Auflistung, die im Vergleich mit [max](https://msdn.microsoft.com/library/9a988328-00e9-467b-8dfa-e7a6990f6cce) auf das Ergebnis der Funktion.|
|maxElement|-|-|-|-|O (Log N)|Gibt das größte Element im Satz entsprechend der Sortierung, das für die Gruppe verwendet wird.|
|Min.|O(N)|O(N)|O(N)|-|-|Gibt den geringsten Element zurück, in der Auflistung, die im Vergleich mit der [min](https://msdn.microsoft.com/library/adea4fd7-bfad-4834-989c-7878aca81fed) Operator.|
|minBy|O(N)|O(N)|O(N)|-|-|Gibt den geringsten Element zurück, in der Auflistung, die im Vergleich mit der [min](https://msdn.microsoft.com/library/adea4fd7-bfad-4834-989c-7878aca81fed) Operator das Ergebnis der Funktion.|
|minElement|-|-|-|-|O (Log N)|Gibt das niedrigste Element im Satz entsprechend der Sortierung, das für die Gruppe verwendet wird.|
|ofArray|-|O(N)|O(1)|O(N)|O(N)|Erstellt eine Auflistung, die die gleichen Elemente wie das angegebene Array enthält.|
|ofList|O(N)|-|O(1)|O(N)|O(N)|Erstellt eine Auflistung, die die gleichen Elemente wie die angegebene Liste enthält.|
|ofSeq|O(N)|O(N)|-|O(N)|O(N)|Erstellt eine Auflistung, die die gleichen Elemente wie der angegebenen Sequenz enthält.|
|paarweise|-|-|O(N)|-|-|Gibt eine Sequenz von jedem Element in der Eingabesequenz und seinem Vorgänger außer das erste Element, das nur als Vorgänger des zweiten Elements zurückgegeben wird.|
|partition|O(N)|O(N)|-|O(N)|O(N)|Teilt die Auflistung in zwei Auflistungen. Die erste Auflistung enthält die Elemente, die für die das angegebene Prädikat wieder `true`, und die zweite Auflistung enthält die Elemente, die für die das angegebene Prädikat wieder `false`.|
|permute-|O(N)|O(N)|-|-|-|Gibt ein Array mit allen Elementen zurück, die entsprechend der angegebenen Permutation permutiert wurden.|
|Wählen Sie|O(N)|O(N)|O(N)|O (Log N)|-|Wendet die angegebene Funktion auf aufeinander folgende Elemente an und gibt das erste Ergebnis zurück, die Funktion einige. Wenn die Funktion nie wieder zurückgibt `System.Collections.Generic.KeyNotFoundException` ausgelöst wird.|
|readonly|-|-|O(N)|-|-|Erstellt ein Sequenzobjekt, das an das angegebene Sequenzobjekt delegiert. Dieser Vorgang wird sichergestellt, dass eine Typumwandlung kann nicht finden kann, und verändert die ursprüngliche Sequenz wird. Z. B. wenn ein Array angegeben, gibt die zurückgegebene Sequenz der Elemente des Arrays zurück, aber Sie können jedoch stattdessen das zurückgegebene Sequenz in ein Array können nicht umgewandelt.|
|reduce|O(N)|O(N)|O(N)|-|-|Wendet eine Funktion auf jedes Element der Auflistung ein Akkumulatorargument über die Berechnung an. Diese Funktion beginnt mit dem die Funktion auf die ersten beiden Elemente angewendet, übergibt das Ergebnis in die Funktion zusammen mit dem dritten Element und So weiter. Die Funktion gibt das endgültige Ergebnis zurück.|
|reduceBack|O(N)|O(N)|-|-|-|Wendet eine Funktion auf jedes Element der Auflistung ein Akkumulatorargument über die Berechnung an. Wenn die Eingabefunktion f und die Elemente i0... iN sind, berechnet dieser Funktion f i0 (...) (f iN – 1 im)).|
|remove|-|-|-|O (Log N)|O (Log N)|Entfernt ein Element aus der Domäne der Zuordnung. Es wird keine Ausnahme ausgelöst, wenn das Element nicht vorhanden ist.|
|Replizieren|-|O(N)|-|-|-|Erstellt eine Liste mit einer angegebenen Länge mit jedem Element auf den angegebenen Wert festgelegt.|
|Rev|O(N)|O(N)|-|-|-|Gibt eine neue Liste mit den Elementen in umgekehrter Reihenfolge an.|
|Überprüfung|O(N)|O(N)|O(N)|-|-|Wendet eine Funktion auf jedes Element der Auflistung ein Akkumulatorargument über die Berechnung an. Dieser Vorgang wendet die Funktion das zweite Argument und das erste Element der Liste. Klicken Sie dann der Vorgang übergibt dieses Ergebnis in die Funktion zusammen mit dem zweiten Element und so weiter. Schließlich gibt der Vorgang die Liste von Zwischenergebnissen und das Endergebnis.|
|scanBack|O(N)|O(N)|-|-|-|Ähnelt den FoldBack-Vorgang, aber die intermediate und letzte Ergebnisse zurückgegeben werden.|
|Singleton|-|-|O(1)|-|O(1)|Gibt eine Sequenz, die nur ein Element ergibt.|
|set|O(1)|-|-|-|-|Legt ein Element eines Arrays mit dem angegebenen Wert fest.|
|überspringen|-|-|O(N)|-|-|Gibt eine Sequenz, die N Elemente der zugrunde liegenden Sequenz überspringt und dann die verbleibenden Elemente der Sequenz ergibt.|
|skipWhile|-|-|O(N)|-|-|Gibt eine Sequenz zurück, die beim durchlaufen, überspringt Elemente der zugrunde liegenden Sequenz das angegebene Prädikat zurückgibt, solange `true` , und klicken Sie dann die verbleibenden Elemente der Sequenz ergibt.|
|sort|Durchschnitt O (N Log N)<br /><br />O(N^2) schlimmsten Fall|O (N Log N)|O (N Log N)|-|-|Wert des Elements sortiert die Auflistung. Elemente sind im Vergleich mit [vergleichen](https://msdn.microsoft.com/library/295e1320-0955-4c3d-ac31-288fa80a658c).|
|sortBy|Durchschnitt O (N Log N)<br /><br />O(N^2) schlimmsten Fall|O (N Log N)|O (N Log N)|-|-|Sortiert die angegebene Liste mit Schlüsseln, die die angegebene Projektion bereitstellt. Schlüssel werden verglichen mit [vergleichen](https://msdn.microsoft.com/library/295e1320-0955-4c3d-ac31-288fa80a658c).|
|sortInPlace|Durchschnitt O (N Log N)<br /><br />O(N^2) schlimmsten Fall|-|-|-|-|Sortiert die Elemente eines Arrays durch veränderliche er vorhanden und verwenden die angegebene Vergleichsfunktion. Elemente werden verglichen mit [vergleichen](https://msdn.microsoft.com/library/295e1320-0955-4c3d-ac31-288fa80a658c).|
|sortInPlaceBy|Durchschnitt O (N Log N)<br /><br />O(N^2) schlimmsten Fall|-|-|-|-|Sortiert die Elemente eines Arrays durch veränderliche er vorhanden und die Verwendung der angegebenen Projektion für die Schlüssel. Elemente werden verglichen mit [vergleichen](https://msdn.microsoft.com/library/295e1320-0955-4c3d-ac31-288fa80a658c).|
|sortInPlaceWith|Durchschnitt O (N Log N)<br /><br />O(N^2) schlimmsten Fall|-|-|-|-|Sortiert die Elemente eines Arrays durch veränderliche er vorhanden und die Verwendung der angegebenen Vergleichsfunktion als Reihenfolge.|
|sortWith|Durchschnitt O (N Log N)<br /><br />O(N^2) schlimmsten Fall|O (N Log N)|-|-|-|Sortiert die Elemente einer Auflistung und die Verwendung der angegebenen Vergleichsfunktion als Reihenfolge und eine neue Auflistung zurückgeben.|
|sub|O(N)|-|-|-|-|Erstellt ein Array, das den angegebenen Unterbereich enthält, der durch startIndex und Länge angegeben wird.|
|sum|O(N)|O(N)|O(N)|-|-|Gibt die Summe der Elemente in der Auflistung zurück.|
|sumBy|O(N)|O(N)|O(N)|-|-|Gibt die Summe der Ergebnisse, die durch Anwenden der Funktion auf jedes Element der Auflistung generiert werden.|
|Ende|-|O(1)|-|-|-|Gibt die Liste ohne das erste Element zurück.|
|Take|-|-|O(N)|-|-|Gibt die Elemente der Sequenz bis zu einer angegebenen Anzahl zurück.|
|takeWhile|-|-|O(1)|-|-|Gibt eine Sequenz zurück, die beim Durchlaufen ergibt Elemente der zugrunde liegenden Sequenz das angegebene Prädikat zurückgibt, solange `true` und gibt dann keine weiteren Elemente zurück.|
|ToArray|-|O(N)|O(N)|O(N)|O(N)|Erstellt ein Array aus der angegebenen Auflistung.|
|ToList|O(N)|-|O(N)|O(N)|O(N)|Erstellt eine Liste aus der angegebenen Auflistung.|
|toSeq|O(1)|O(1)|-|O(1)|O(1)|Erstellt eine Sequenz aus der angegebenen Auflistung.|
|Abschneiden|-|-|O(1)|-|-|Gibt einer Sequenz zurück, wenn aufgelistet, gibt nicht mehr als N Elemente.|
|tryFind|O(N)|O(N)|O(N)|O (Log N)|-|Sucht nach einem Element, das ein angegebenes Prädikat erfüllt.|
|tryFindIndex|O(N)|O(N)|O(N)|-|-|Sucht das erste Element, das ein angegebenes Prädikat erfüllt, und gibt den Index des entsprechenden Elements oder `None` Wenn kein solches Element vorhanden ist.|
|tryFindKey|-|-|-|O (Log N)|-|Gibt den Schlüssel der ersten Zuordnung in der Auflistung, die das angegebene Prädikat erfüllt, oder gibt `None` Wenn kein solches Element vorhanden ist.|
|tryPick|O(N)|O(N)|O(N)|O (Log N)|-|Wendet die angegebene Funktion auf aufeinander folgenden Elementen, gibt das erste Ergebnis zurück, die Funktion `Some` für einen entsprechenden Wert. Wenn kein solches Element vorhanden ist, gibt der Vorgang `None`.|
|Erweitern|-|-|O(N)|-|-|Gibt eine Sequenz, die Elemente enthält, die die angegebene Berechnung generiert.|
|union|-|-|-|-|O (M &#42; Log N)|Berechnet die Union der beiden Sätze.|
|unionMany|-|-|-|-|O (N1 &AMP;#42; N2...)|Berechnet die Union einer Sequenz von Sätzen.|
|unzip|O(N)|O(N)|O(N)|-|-|Teilt eine Liste von Paaren in zwei Listen.|
|unzip3|O(N)|O(N)|O(N)|-|-|Teilt eine Liste von Tripeln in drei Listen.|
|Fensterfunktionen|-|-|O(N)|-|-|Gibt eine Sequenz, die liefert gleitende Fenster mit Elementen, die aus der Eingabesequenz gezeichnet werden. Jedes Fenster wird als neues Array zurückgegeben.|
|PLZ|O(N)|O(N)|O(N)|-|-|Kombiniert die beiden Auflistungen in eine Liste von Paaren. Die zwei Listen müssen die gleiche Länge aufweisen.|
|zip3|O(N)|O(N)|O(N)|-|-|Kombiniert die drei Auflistungen in eine Liste von Tripeln. Die Listen müssen die gleiche Länge aufweisen.|

## <a name="see-also"></a>Siehe auch
[F#-Typen](fsharp-types.md)

[F#-Sprachreferenz](index.md)

