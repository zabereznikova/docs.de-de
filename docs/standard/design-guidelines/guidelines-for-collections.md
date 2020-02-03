---
title: Richtlinien für Auflistungen
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: 297b8f1d-b11f-4dc6-960a-8e990817304e
ms.openlocfilehash: 50497de6569b448ab036af8a1fbf76a47565e2bb
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741868"
---
# <a name="guidelines-for-collections"></a>Richtlinien für Auflistungen
Jeder Typ, der speziell zum Bearbeiten einer Gruppe von Objekten entworfen wurde, die über ein gemeinsames Merkmal verfügen, kann als Sammlung angesehen werden. Es ist fast immer für solche Typen geeignet, <xref:System.Collections.IEnumerable> oder <xref:System.Collections.Generic.IEnumerable%601>zu implementieren. daher berücksichtigen wir in diesem Abschnitt nur Typen, die eine oder beide dieser Schnittstellen implementieren, um Auflistungen zu sein.

 ❌ nicht schwach typisierte Auflistungen in öffentlichen APIs verwenden.

 Der Typ aller Rückgabewerte und Parameter, die Sammel Elemente darstellen, sollte der exakte Elementtyp und nicht einer seiner Basis Typen sein (Dies gilt nur für öffentliche Member der Auflistung).

 ❌ nicht <xref:System.Collections.ArrayList> oder <xref:System.Collections.Generic.List%601> in öffentlichen APIs verwenden.

 Bei diesen Typen handelt es sich um Datenstrukturen, die in der internen Implementierung, nicht in öffentlichen APIs verwendet werden sollen. `List<T>` ist für die Leistung und die Leistung auf Kosten der Bereinigung der APIs und Flexibilität optimiert. Wenn Sie z. b. `List<T>`zurückgeben, sind Sie nicht mehr in der Lage, Benachrichtigungen zu empfangen, wenn der Client Code die Auflistung ändert. Außerdem werden `List<T>` viele Member, z. b. <xref:System.Collections.Generic.List%601.BinarySearch%2A>, verfügbar machen, die in vielen Szenarios nicht nützlich oder anwendbar sind. In den folgenden beiden Abschnitten werden Typen (Abstraktionen) beschrieben, die speziell für die Verwendung in öffentlichen APIs entworfen wurden.

 ❌ nicht `Hashtable` oder `Dictionary<TKey,TValue>` in öffentlichen APIs verwenden.

 Diese Typen sind Datenstrukturen, die für die Verwendung in der internen Implementierung entwickelt wurden. Öffentliche APIs sollten <xref:System.Collections.IDictionary>, `IDictionary <TKey, TValue>`oder einen benutzerdefinierten Typ verwenden, der eine oder beide Schnittstellen implementiert.

 ❌ nicht <xref:System.Collections.Generic.IEnumerator%601>, <xref:System.Collections.IEnumerator>oder einen anderen Typ verwenden, der eine dieser Schnittstellen implementiert, außer als Rückgabetyp einer `GetEnumerator` Methode.

 Typen, die Enumeratoren von anderen Methoden als `GetEnumerator` zurückgeben, können nicht mit der `foreach`-Anweisung verwendet werden.

 ❌ nicht sowohl `IEnumerator<T>` als auch `IEnumerable<T>` für denselben Typ implementieren. Das gleiche gilt für die nicht generischen Schnittstellen `IEnumerator` und `IEnumerable`.

## <a name="collection-parameters"></a>Sammlungs Parameter
 ✔️ Verwenden Sie den am wenigsten spezialisierten Typ, der als Parametertyp möglich ist. Die meisten Member, die Auflistungen als Parameter verwenden, verwenden die `IEnumerable<T>` Schnittstelle

 ❌ vermeiden Sie, <xref:System.Collections.Generic.ICollection%601> oder <xref:System.Collections.ICollection> als Parameter zu verwenden, um nur auf die `Count`-Eigenschaft zuzugreifen.

 Verwenden Sie stattdessen `IEnumerable<T>` oder `IEnumerable`, und überprüfen Sie, ob das Objekt `ICollection<T>` oder `ICollection`implementiert.

## <a name="collection-properties-and-return-values"></a>Sammlungs Eigenschaften und Rückgabewerte
 ❌ keine festleg baren Sammlungs Eigenschaften bereitstellen.

 Benutzer können den Inhalt der Auflistung ersetzen, indem Sie zuerst die Auflistung löschen und dann den neuen Inhalt hinzufügen. Wenn das Ersetzen der gesamten Sammlung ein gängiges Szenario ist, sollten Sie die `AddRange`-Methode für die Auflistung bereitstellen.

 ✔️ verwenden `Collection<T>` oder eine Unterklasse von `Collection<T>` für Eigenschaften oder Rückgabewerte, die Lese-/schreibauflistungen darstellen.

 Wenn `Collection<T>` eine bestimmte Anforderung nicht erfüllt (z. b., dass die Sammlung <xref:System.Collections.IList>nicht implementieren darf), verwenden Sie eine benutzerdefinierte Auflistung, indem Sie `IEnumerable<T>`, `ICollection<T>`oder <xref:System.Collections.Generic.IList%601>implementieren.

 ✔️ Verwenden Sie <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>, eine Unterklasse von `ReadOnlyCollection<T>`oder in seltenen Fällen `IEnumerable<T>` für Eigenschaften oder Rückgabewerte, die schreibgeschützte Auflistungen darstellen.

 Im allgemeinen bevorzugen Sie `ReadOnlyCollection<T>`. Wenn dies nicht der Fall ist (z. b. wenn die Sammlung `IList`nicht implementieren darf), verwenden Sie eine benutzerdefinierte Auflistung, indem Sie `IEnumerable<T>`, `ICollection<T>`oder `IList<T>`implementieren. Wenn Sie eine benutzerdefinierte schreibgeschützte Auflistung implementieren, implementieren Sie `ICollection<T>.IsReadOnly`, um `true`zurückzugeben.

 In Fällen, in denen Sie sicher sind, dass das einzige Szenario, das Sie unterstützen möchten, eine vorwärts-Iterations-Iterations-ist, können Sie einfach `IEnumerable<T>`verwenden.

 ✔️ sollten die Verwendung von Unterklassen generischer Basis Auflistungen in Erwägung gezogen werden, anstatt die Auflistungen

 Dies ermöglicht einen besseren Namen und das Hinzufügen von hilfselmembern, die in den Basis Auflistungs Typen nicht vorhanden sind. Dies gilt insbesondere für APIs auf hoher Ebene.

 ✔️ sollten Sie eine Unterklasse von `Collection<T>` oder `ReadOnlyCollection<T>` von sehr häufig verwendeten Methoden und Eigenschaften zurückgeben.

 Auf diese Weise können Sie Hilfsmethoden hinzufügen oder die Auflistungs Implementierung in Zukunft ändern.

 ✔️ sollten Sie eine Schlüssel gebundene Sammlung verwenden, wenn die in der Auflistung gespeicherten Elemente eindeutige Schlüssel (Namen, IDs usw.) aufweisen. Schlüssel gebundene Auflistungen sind Auflistungen, die mit einer ganzen Zahl und einem Schlüssel indiziert werden können und in der Regel durch Vererbung von `KeyedCollection<TKey,TItem>`implementiert werden.

 Schlüssel gebundene Sammlungen verfügen in der Regel über eine größere Speicherauslastung und sollten nicht verwendet werden, wenn der Arbeitsspeicher Aufwand die Vorteile der Schlüssel auswiegt.

 ❌ keine NULL-Werte aus Sammlungs Eigenschaften oder Methoden zurückgeben, die Auflistungen zurückgeben. Gibt stattdessen eine leere Auflistung oder ein leeres Array zurück.

 Die allgemeine Regel ist, dass NULL-und leere (0 Element) Auflistungen oder Arrays gleich behandelt werden sollen.

### <a name="snapshots-versus-live-collections"></a>Momentaufnahmen im Vergleich zu Live Sammlungen
 Sammlungen, die einen Zustand zu einem bestimmten Zeitpunkt darstellen, werden als Momentaufnahme Auflistungen bezeichnet. Beispielsweise wäre eine Auflistung, die Zeilen enthält, die von einer Datenbankabfrage zurückgegeben werden, eine Momentaufnahme. Sammlungen, die den aktuellen Zustand immer darstellen, werden als Live Auflistungen bezeichnet. Eine Auflistung von `ComboBox` Elementen ist beispielsweise eine Live Auflistung.

 ❌ keine Momentaufnahme Sammlungen von Eigenschaften zurückgeben. Eigenschaften sollten Live Auflistungen zurückgeben.

 Eigenschaften Getter sollten sehr einfach sein. Zum Zurückgeben einer Momentaufnahme muss eine Kopie einer internen Sammlung in einem O (n)-Vorgang erstellt werden.

 ✔️ entweder eine Momentaufnahme Auflistung oder eine Live `IEnumerable<T>` (oder den Untertyp) verwenden, um Auflistungen darzustellen, die flüchtig sind (d. h., Sie können sich ändern, ohne die Auflistung explizit zu ändern).

 Im Allgemeinen sind alle Sammlungen, die eine freigegebene Ressource darstellen (z. b. Dateien in einem Verzeichnis), flüchtig. Solche Auflistungen sind sehr schwierig oder unmöglich, als Live Auflistungen zu implementieren, es sei denn, die Implementierung ist einfach ein vorwärts-Enumerator.

## <a name="choosing-between-arrays-and-collections"></a>Auswählen zwischen Arrays und Sammlungen
 ✔️ bevorzugen Sammlungen vor Arrays.

 Sammlungen bieten mehr Kontrolle über Inhalte, können sich im Laufe der Zeit weiterentwickeln und sind besser verwendbar. Außerdem wird davon abgeraten, Arrays für schreibgeschützte Szenarien zu verwenden, da die Kosten für das Klonen des Arrays unersetzen. Nutzbarkeits Studien haben gezeigt, dass einige Entwickler die Verwendung von Sammlungs basierten APIs besser fühlen.

 Wenn Sie jedoch Low-Level-APIs entwickeln, ist es möglicherweise besser, Arrays für Szenarien mit Lese-/Schreibzugriff zu verwenden. Arrays haben einen geringeren Speicherbedarf, wodurch das Workingset reduziert werden kann, und der Zugriff auf Elemente in einem Array ist schneller, da es von der Laufzeit optimiert wird.

 ✔️ in Erwägung gezogen, Arrays in Low-Level-APIs zu verwenden, um den Speicherverbrauch zu minimieren und die

 ✔️ verwenden Byte Arrays anstelle von Byte Auflistungen.

 ❌ keine Arrays für Eigenschaften verwenden, wenn die Eigenschaft jedes Mal, wenn der Eigenschaften Getter aufgerufen wird, ein neues Array (z. b. eine Kopie eines internen Arrays) zurückgeben muss.

## <a name="implementing-custom-collections"></a>Implementieren von benutzerdefinierten Sammlungen
 ✔️ sollten beim Entwerfen neuer Sammlungen eine Vererbung von `Collection<T>`, `ReadOnlyCollection<T>`oder `KeyedCollection<TKey,TItem>` in Erwägung gezogen werden.

 ✔️ Implementieren Sie `IEnumerable<T>`, wenn Sie neue Sammlungen entwerfen. Implementieren Sie `ICollection<T>` oder sogar `IList<T>`, wo es sinnvoll ist.

 Beachten Sie beim Implementieren einer solchen benutzerdefinierten Sammlung das API-Muster, das von `Collection<T>` festgelegt wurde, und `ReadOnlyCollection<T>` so genau wie möglich. Das heißt, Sie müssen dieselben Member explizit implementieren, benennen Sie die Parameter wie diese zwei Auflistungen, und so weiter.

 ✔️ sollten Sie die Implementierung von nicht generischen Auflistungs Schnittstellen (`IList` und `ICollection`) in Erwägung ziehen, wenn die Auflistung häufig an APIs übermittelt wird, die diese Schnittstellen

 ❌ vermeiden Sie das Implementieren von Auflistungs Schnittstellen für Typen mit komplexen APIs, die nicht mit dem Konzept einer Auflistung zusammenhängen

 ❌ erben nicht von nicht generischen Basis Auflistungen, z. b. `CollectionBase`. Verwenden Sie stattdessen `Collection<T>`, `ReadOnlyCollection<T>`und `KeyedCollection<TKey,TItem>`.

### <a name="naming-custom-collections"></a>Benennen von benutzerdefinierten Sammlungen
 Auflistungen (Typen, die `IEnumerable`implementieren) werden hauptsächlich aus zwei Gründen erstellt: (1) zum Erstellen einer neuen Datenstruktur mit Struktur spezifischen Vorgängen und oft unterschiedlichen Leistungsmerkmalen als vorhandene Datenstrukturen (z. b. <xref:System.Collections.Generic.List%601>, <xref:System.Collections.Generic.LinkedList%601>, <xref:System.Collections.Generic.Stack%601>) und (2) zum Erstellen einer spezialisierten Sammlung zum Speichern eines bestimmten Satzes von Elementen (z. b. <xref:System.Collections.Specialized.StringCollection>). Datenstrukturen werden am häufigsten in der internen Implementierung von Anwendungen und Bibliotheken verwendet. Spezialisierte Sammlungen werden hauptsächlich in APIs verfügbar gemacht (als Eigenschaften-und Parametertypen).

 ✔️ Verwenden Sie das Suffix "Dictionary" in Namen von Abstraktionen, die `IDictionary` oder `IDictionary<TKey,TValue>`implementieren.

 ✔️ Verwenden Sie das Suffix "Collection" in Namen von Typen, die `IEnumerable` (oder einen beliebigen Nachfolger) implementieren und eine Liste von Elementen darstellen.

 ✔️ den passenden Datenstruktur Namen für benutzerdefinierte Datenstrukturen verwenden.

 ❌ vermeiden Sie die Verwendung von Suffixen, die eine bestimmte Implementierung implizieren, wie z. b. "LinkedList" oder "Hashtable" in Namen von Sammlungs Abstraktionen.

 ✔️ in Erwägung gezogen, Sammlungsnamen mit dem Namen des Elementtyps vorab zu beheben. Beispielsweise sollte eine Auflistung, die Elemente vom Typ `Address` speichert (`IEnumerable<Address>`implementiert), `AddressCollection`benannt werden. Wenn der Elementtyp eine Schnittstelle ist, kann das Präfix "I" des Elementtyps ausgelassen werden. Daher kann eine Auflistung von <xref:System.IDisposable> Elementen `DisposableCollection`aufgerufen werden.

 ✔️ sollten Sie das Präfix "schreibgeschützt" in Namen von schreibgeschützten Auflistungen verwenden, wenn eine entsprechende beschreibbare Auflistung im Framework hinzugefügt oder bereits vorhanden sein kann.

 So sollte z. b. eine schreibgeschützte Auflistung von Zeichen folgen `ReadOnlyStringCollection`aufgerufen werden.

 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*

## <a name="see-also"></a>Weitere Informationen

- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
- [Verwendungsrichtlinien](../../../docs/standard/design-guidelines/usage-guidelines.md)
