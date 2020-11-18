---
title: Richtlinien für Auflistungen
ms.date: 10/22/2008
ms.assetid: 297b8f1d-b11f-4dc6-960a-8e990817304e
ms.openlocfilehash: 2306462d933e71d0d23021a0e036e8cc23100c68
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94821085"
---
# <a name="guidelines-for-collections"></a>Richtlinien für Auflistungen
Jeder Typ, der speziell zum Bearbeiten einer Gruppe von Objekten entworfen wurde, die über ein gemeinsames Merkmal verfügen, kann als Sammlung angesehen werden. Es ist fast immer für solche Typen geeignet, oder zu implementieren <xref:System.Collections.IEnumerable> <xref:System.Collections.Generic.IEnumerable%601> , daher berücksichtigen wir in diesem Abschnitt nur Typen, die eine oder beide dieser Schnittstellen implementieren, um Auflistungen zu sein.

 ❌ Verwenden Sie keine schwach typisierten Auflistungen in öffentlichen APIs.

 Der Typ aller Rückgabewerte und Parameter, die Sammel Elemente darstellen, sollte der exakte Elementtyp und nicht einer seiner Basis Typen sein (Dies gilt nur für öffentliche Member der Auflistung).

 ❌ Verwenden Sie <xref:System.Collections.ArrayList> <xref:System.Collections.Generic.List%601> in öffentlichen APIs nicht oder.

 Bei diesen Typen handelt es sich um Datenstrukturen, die in der internen Implementierung, nicht in öffentlichen APIs verwendet werden sollen. `List<T>` ist für die Leistung und die Leistung auf Kosten der Bereinigung der APIs und Flexibilität optimiert. Wenn Sie z `List<T>` . b. zurückgeben, sind Sie nicht mehr in der Lage, Benachrichtigungen zu empfangen, wenn der Client Code die Auflistung ändert. Darüber hinaus macht viele Member verfügbar `List<T>` , z <xref:System.Collections.Generic.List%601.BinarySearch%2A> . b., die in vielen Szenarios nicht nützlich oder anwendbar sind. In den folgenden beiden Abschnitten werden Typen (Abstraktionen) beschrieben, die speziell für die Verwendung in öffentlichen APIs entworfen wurden.

 ❌ Verwenden Sie `Hashtable` `Dictionary<TKey,TValue>` in öffentlichen APIs nicht oder.

 Diese Typen sind Datenstrukturen, die für die Verwendung in der internen Implementierung entwickelt wurden. Öffentliche APIs sollten <xref:System.Collections.IDictionary> , `IDictionary <TKey, TValue>` oder einen benutzerdefinierten Typ verwenden, der eine oder beide Schnittstellen implementiert.

 ❌ Verwenden Sie nicht <xref:System.Collections.Generic.IEnumerator%601> , <xref:System.Collections.IEnumerator> oder einen anderen Typ, der eine dieser Schnittstellen implementiert, außer als Rückgabetyp einer `GetEnumerator` Methode.

 Typen, die Enumeratoren von anderen Methoden als zurück `GetEnumerator` geben, können nicht mit der-Anweisung verwendet werden `foreach` .

 ❌ Implementieren Sie nicht sowohl `IEnumerator<T>` als auch `IEnumerable<T>` für denselben Typ. Das gleiche gilt für die nicht generischen Schnittstellen `IEnumerator` und `IEnumerable` .

## <a name="collection-parameters"></a>Sammlungs Parameter
 ✔️ Verwenden Sie den am wenigsten spezialisierten Typ, der als Parametertyp möglich ist. Die meisten Member, die Sammlungen als Parameter verwenden, verwenden die- `IEnumerable<T>` Schnittstelle

 ❌ Vermeiden Sie <xref:System.Collections.Generic.ICollection%601> <xref:System.Collections.ICollection> die Verwendung von oder als Parameter nur für den Zugriff auf die- `Count` Eigenschaft.

 Verwenden Sie stattdessen oder, und überprüfen Sie, `IEnumerable<T>` `IEnumerable` ob das Objekt `ICollection<T>` oder implementiert `ICollection` .

## <a name="collection-properties-and-return-values"></a>Sammlungs Eigenschaften und Rückgabewerte
 ❌ Stellen Sie keine festleg baren Sammlungs Eigenschaften bereit.

 Benutzer können den Inhalt der Auflistung ersetzen, indem Sie zuerst die Auflistung löschen und dann den neuen Inhalt hinzufügen. Wenn das Ersetzen der gesamten Auflistung ein gängiges Szenario ist, sollten Sie die- `AddRange` Methode in der Auflistung bereitstellen.

 ✔️ verwenden `Collection<T>` oder eine Unterklasse von `Collection<T>` für Eigenschaften oder Rückgabewerte, die Lese-/schreibauflistungen darstellen.

 Wenn `Collection<T>` eine bestimmte Anforderung nicht erfüllt (z. b. wenn die Auflistung nicht implementieren darf <xref:System.Collections.IList> ), verwenden Sie eine benutzerdefinierte Auflistung, indem Sie `IEnumerable<T>` , `ICollection<T>` oder implementieren <xref:System.Collections.Generic.IList%601> .

 ✔️ verwenden <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> , eine Unterklasse von `ReadOnlyCollection<T>` oder in seltenen Fällen `IEnumerable<T>` für Eigenschaften oder Rückgabewerte, die schreibgeschützte Auflistungen darstellen.

 Im allgemeinen bevorzugen Sie `ReadOnlyCollection<T>` . Wenn dies nicht der Fall ist (z. b. wenn die Auflistung nicht implementieren darf `IList` ), verwenden Sie eine benutzerdefinierte Auflistung, indem Sie `IEnumerable<T>` , `ICollection<T>` oder implementieren `IList<T>` . Wenn Sie eine benutzerdefinierte schreibgeschützte Auflistung implementieren, implementieren Sie `ICollection<T>.IsReadOnly` , um zurückzugeben `true` .

 In Fällen, in denen Sie sicher sind, dass das einzige Szenario, das Sie unterstützen möchten, eine vorwärts Iterations iterierung ist, können Sie einfach verwenden `IEnumerable<T>` .

 ✔️ sollten die Verwendung von Unterklassen generischer Basis Auflistungen in Erwägung gezogen werden, anstatt die Auflistungen

 Dies ermöglicht einen besseren Namen und das Hinzufügen von hilfselmembern, die in den Basis Auflistungs Typen nicht vorhanden sind. Dies gilt insbesondere für APIs auf hoher Ebene.

 ✔️ sollten eine Unterklasse von `Collection<T>` oder `ReadOnlyCollection<T>` von sehr häufig verwendeten Methoden und Eigenschaften zurückgeben.

 Auf diese Weise können Sie Hilfsmethoden hinzufügen oder die Auflistungs Implementierung in Zukunft ändern.

 ✔️ sollten Sie eine Schlüssel gebundene Sammlung verwenden, wenn die in der Auflistung gespeicherten Elemente eindeutige Schlüssel (Namen, IDs usw.) aufweisen. Schlüssel gebundene Auflistungen sind Auflistungen, die sowohl durch eine ganze Zahl als auch durch einen Schlüssel indiziert werden können und in der Regel durch Erben von implementiert werden `KeyedCollection<TKey,TItem>` .

 Schlüssel gebundene Sammlungen verfügen in der Regel über eine größere Speicherauslastung und sollten nicht verwendet werden, wenn der Arbeitsspeicher Aufwand die Vorteile der Schlüssel auswiegt.

 ❌ Geben Sie keine NULL-Werte aus Sammlungs Eigenschaften oder Methoden zurück, die Auflistungen zurückgeben. Gibt stattdessen eine leere Auflistung oder ein leeres Array zurück.

 Die allgemeine Regel ist, dass NULL-und leere (0 Element) Auflistungen oder Arrays gleich behandelt werden sollen.

### <a name="snapshots-versus-live-collections"></a>Momentaufnahmen im Vergleich zu Live Sammlungen
 Sammlungen, die einen Zustand zu einem bestimmten Zeitpunkt darstellen, werden als Momentaufnahme Auflistungen bezeichnet. Beispielsweise wäre eine Auflistung, die Zeilen enthält, die von einer Datenbankabfrage zurückgegeben werden, eine Momentaufnahme. Sammlungen, die den aktuellen Zustand immer darstellen, werden als Live Auflistungen bezeichnet. Eine Auflistung von `ComboBox` Elementen ist beispielsweise eine Live Auflistung.

 ❌ Momentaufnahme Auflistungen von Eigenschaften nicht zurückgeben. Eigenschaften sollten Live Auflistungen zurückgeben.

 Eigenschaften Getter sollten sehr einfach sein. Zum Zurückgeben einer Momentaufnahme muss eine Kopie einer internen Sammlung in einem O (n)-Vorgang erstellt werden.

 ✔️ verwenden entweder eine Momentaufnahme Auflistung oder eine Live `IEnumerable<T>` (oder einen Untertyp), um Auflistungen darzustellen, die flüchtig sind (d. h., Sie können sich ändern, ohne die Auflistung explizit zu ändern).

 Im Allgemeinen sind alle Sammlungen, die eine freigegebene Ressource darstellen (z. b. Dateien in einem Verzeichnis), flüchtig. Solche Auflistungen sind sehr schwierig oder unmöglich, als Live Auflistungen zu implementieren, es sei denn, die Implementierung ist einfach ein vorwärts-Enumerator.

## <a name="choosing-between-arrays-and-collections"></a>Auswählen zwischen Arrays und Sammlungen
 ✔️ bevorzugen Sammlungen vor Arrays.

 Sammlungen bieten mehr Kontrolle über Inhalte, können sich im Laufe der Zeit weiterentwickeln und sind besser verwendbar. Außerdem wird davon abgeraten, Arrays für schreibgeschützte Szenarien zu verwenden, da die Kosten für das Klonen des Arrays unersetzen. Nutzbarkeits Studien haben gezeigt, dass einige Entwickler die Verwendung von Sammlungs basierten APIs besser fühlen.

 Wenn Sie jedoch Low-Level-APIs entwickeln, ist es möglicherweise besser, Arrays für Szenarien mit Lese-/Schreibzugriff zu verwenden. Arrays haben einen geringeren Speicherbedarf, wodurch das Workingset reduziert werden kann, und der Zugriff auf Elemente in einem Array ist schneller, da es von der Laufzeit optimiert wird.

 ✔️ in Erwägung gezogen, Arrays in Low-Level-APIs zu verwenden, um den Speicherverbrauch zu minimieren und die

 ✔️ verwenden Byte Arrays anstelle von Byte Auflistungen.

 ❌ Verwenden Sie keine Arrays für Eigenschaften, wenn die Eigenschaft jedes Mal, wenn der Eigenschaften Getter aufgerufen wird, ein neues Array (z. b. eine Kopie eines internen Arrays) zurückgeben muss.

## <a name="implementing-custom-collections"></a>Implementieren von benutzerdefinierten Sammlungen
 ✔️ sollten beim Entwerfen von neuen Auflistungen von `Collection<T>` , `ReadOnlyCollection<T>` oder Erben `KeyedCollection<TKey,TItem>` .

 ✔️ implementieren, `IEnumerable<T>` Wenn neue Sammlungen entworfen werden. Sie sollten die Implementierung von `ICollection<T>` oder sogar den `IList<T>` Sinn machen.

 Befolgen Sie bei der Implementierung einer solchen benutzerdefinierten Sammlung das API-Muster, das von `Collection<T>` und `ReadOnlyCollection<T>` so genau wie möglich hergestellt wird. Das heißt, Sie müssen dieselben Member explizit implementieren, benennen Sie die Parameter wie diese zwei Auflistungen, und so weiter.

 ✔️ sollten Sie die Implementierung von nicht generischen Auflistungs Schnittstellen ( `IList` und `ICollection` ) in Erwägung ziehen, wenn die Auflistung häufig an APIs übermittelt wird, die diese Schnittstellen

 ❌ Vermeiden Sie das Implementieren von Auflistungs Schnittstellen für Typen mit komplexen APIs, die nicht mit dem Konzept einer Auflistung zusammenhängen

 ❌ Erben nicht von nicht generischen Basis Auflistungen wie z `CollectionBase` . b.. Verwenden `Collection<T>` Sie `ReadOnlyCollection<T>` stattdessen, und `KeyedCollection<TKey,TItem>` .

### <a name="naming-custom-collections"></a>Benennen von benutzerdefinierten Sammlungen
 Auflistungen (Typen, die implementieren `IEnumerable` ) werden hauptsächlich aus zwei Gründen erstellt: (1) zum Erstellen einer neuen Datenstruktur mit Struktur spezifischen Vorgängen und oft unterschiedlichen Leistungsmerkmalen als vorhandene Datenstrukturen (z. b.,  <xref:System.Collections.Generic.List%601> <xref:System.Collections.Generic.LinkedList%601> , <xref:System.Collections.Generic.Stack%601> ) und (2) zum Erstellen einer spezialisierten Sammlung zum Speichern eines bestimmten Satzes von Elementen (z. b.  <xref:System.Collections.Specialized.StringCollection> ). Datenstrukturen werden am häufigsten in der internen Implementierung von Anwendungen und Bibliotheken verwendet. Spezialisierte Sammlungen werden hauptsächlich in APIs verfügbar gemacht (als Eigenschaften-und Parametertypen).

 ✔️ Verwenden Sie das Suffix "Dictionary" in Namen von Abstraktionen, die `IDictionary` oder implementieren `IDictionary<TKey,TValue>` .

 ✔️ Verwenden Sie das Suffix "Collection" in Namen von Typen, die `IEnumerable` (oder einen beliebigen Nachfolger) implementieren und eine Liste von Elementen darstellen.

 ✔️ den passenden Datenstruktur Namen für benutzerdefinierte Datenstrukturen verwenden.

 ❌ Vermeiden Sie die Verwendung von Suffixen, die eine bestimmte Implementierung implizieren, wie z. b. "LinkedList" oder "Hashtable" in Namen von Sammlungs Abstraktionen.

 ✔️ in Erwägung gezogen, Sammlungsnamen mit dem Namen des Elementtyps vorab zu beheben. Beispielsweise sollte eine Auflistung, die Elemente des Typs `Address` (implementiert) speichert, `IEnumerable<Address>` benannt werden `AddressCollection` . Wenn der Elementtyp eine Schnittstelle ist, kann das Präfix "I" des Elementtyps ausgelassen werden. Daher kann eine Auflistung von <xref:System.IDisposable> Elementen aufgerufen werden `DisposableCollection` .

 ✔️ sollten Sie das Präfix "schreibgeschützt" in Namen von schreibgeschützten Auflistungen verwenden, wenn eine entsprechende beschreibbare Auflistung im Framework hinzugefügt oder bereits vorhanden sein kann.

 Beispielsweise muss eine schreibgeschützte Auflistung von Zeichen folgen aufgerufen werden `ReadOnlyStringCollection` .

 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*

## <a name="see-also"></a>Siehe auch

- [Framework-Entwurfs Richtlinien](index.md)
- [Verwendungs Richtlinien](usage-guidelines.md)
