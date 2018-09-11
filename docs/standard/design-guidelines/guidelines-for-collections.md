---
title: Richtlinien für Auflistungen
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 297b8f1d-b11f-4dc6-960a-8e990817304e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3571ebb2fdd2bcdfd8be1f0087d096e01f18790a
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44272945"
---
# <a name="guidelines-for-collections"></a>Richtlinien für Auflistungen
Jeder Typ speziell dazu entwickelt, bearbeiten eine Gruppe von Objekten, die einige gemeinsame Merkmale haben, kann eine Auflistung betrachtet werden. Es ist fast immer für solche Typen implementieren <xref:System.Collections.IEnumerable> oder <xref:System.Collections.Generic.IEnumerable%601>, sodass in diesem Abschnitt nur Typen, die Implementierung einer oder beide dieser Schnittstellen, die Sammlungen sein betrachten wir.  
  
 **X DO NOT** schwach typisierte Auflistungen in öffentlichen APIs verwenden.  
  
 Der Typ aller Rückgabewerte und Parameter, die sammelhäufigkeit (Sek) darstellen sollte der genaue Elementtyp, ohne seine Basistypen (Dies gilt nur für öffentliche Member der Auflistung).  
  
 **X DO NOT** verwenden <xref:System.Collections.ArrayList> oder <xref:System.Collections.Generic.List%601> in öffentlichen APIs.  
  
 Diese Typen sind Datenstrukturen, die in der internen Implementierung, die nicht in öffentlichen APIs, die verwendet werden soll. `List<T>` ist für Leistung und Energie auf Kosten der Voraussichten der APIs und Flexibilität optimiert. Wenn Sie zurückkehren, z. B. `List<T>`, es werden nicht immer möglich, Benachrichtigungen zu empfangen, wenn Clientcode auf die Auflistung ändert. Darüber hinaus `List<T>` verfügbar macht viele Member, z. B. <xref:System.Collections.Generic.List%601.BinarySearch%2A>, nicht hilfreich oder in vielen Szenarien anwendbar sind. Die folgenden beiden Abschnitte beschreiben die Typen (Abstraktionen), die speziell für die Verwendung von öffentlichen APIs konzipiert.  
  
 **X DO NOT** verwenden `Hashtable` oder `Dictionary<TKey,TValue>` in öffentlichen APIs.  
  
 Diese Typen sind Datenstrukturen, die in der internen Implementierung verwendet werden soll. Öffentliche APIs sollten verwenden <xref:System.Collections.IDictionary>, `IDictionary <TKey, TValue>`, oder einen benutzerdefinierten Typ, der Implementierung einer oder beiden Schnittstellen.  
  
 **X DO NOT** verwenden <xref:System.Collections.Generic.IEnumerator%601>, <xref:System.Collections.IEnumerator>, oder eines anderen Typs, die entweder dieser Schnittstellen außer, als den Rückgabetyp implementiert einer `GetEnumerator` Methode.  
  
 Typen, die Rückgabe Enumeratoren Methoden außer `GetEnumerator` kann nicht verwendet werden, mit der `foreach` Anweisung.  
  
 **X DO NOT** implementieren sowohl `IEnumerator<T>` und `IEnumerable<T>` für den gleichen Typ. Das gleiche gilt für den nicht generischen Schnittstellen `IEnumerator` und `IEnumerable`.  
  
## <a name="collection-parameters"></a>Parameter für die Datensammlung  
 **✓ DO** verwenden Sie die möglichen Least spezialisierten Typ als Parametertyp. Die meisten Member, die die Sammlungen aus, als Parameter verwenden, die `IEnumerable<T>` Schnittstelle.  
  
 **X AVOID** mit <xref:System.Collections.Generic.ICollection%601> oder <xref:System.Collections.ICollection> als Parameter nur für den Zugriff auf die `Count` Eigenschaft.  
  
 Verwenden Sie stattdessen `IEnumerable<T>` oder `IEnumerable` und dynamisch überprüfen, ob das Objekt implementiert `ICollection<T>` oder `ICollection`.  
  
## <a name="collection-properties-and-return-values"></a>Auflistung – Eigenschaften und Rückgabewerte  
 **X DO NOT** festlegbaren Auflistungseigenschaften bereitstellen.  
  
 Benutzer können den Inhalt der Auflistung ersetzen, Löschen zuerst die Auflistung und dann den neuen Inhalt hinzufügen. Wenn die gesamte Sammlung ersetzt ein häufiges Szenario ist, geben Sie ggf. die `AddRange` Methode in der Auflistung.  
  
 **✓ DO** verwenden `Collection<T>` oder eine Unterklasse von `Collection<T>` für Eigenschaften oder des Rückgabewerts darstellen Schreib-Lese-Sammlungen Werte.  
  
 Wenn `Collection<T>` einige Anforderungen nicht erfüllt (z. B. in der Sammlung muss nicht implementiert <xref:System.Collections.IList>), verwenden Sie eine benutzerdefinierte Auflistung durch die Implementierung `IEnumerable<T>`, `ICollection<T>`, oder <xref:System.Collections.Generic.IList%601>.  
  
 **✓ DO** verwenden <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>, eine Unterklasse von `ReadOnlyCollection<T>`, oder in seltenen Fällen `IEnumerable<T>` für Eigenschaften oder des Rückgabewerts darstellen schreibgeschützten Auflistungen Werte.  
  
 Im Allgemeinen bevorzugt `ReadOnlyCollection<T>`. Wenn sie einige Anforderungen nicht erfüllt (z. B. in der Sammlung muss nicht implementiert `IList`), verwenden Sie eine benutzerdefinierte Auflistung durch die Implementierung `IEnumerable<T>`, `ICollection<T>`, oder `IList<T>`. Wenn Sie eine benutzerdefinierte schreibgeschützte Sammlung implementieren, implementieren `ICollection<T>.IsReadOnly` zurückzugebenden `true`.  
  
 In Fällen, in dem sind Sie sicher, dass das einzige Szenario, die jemals unterstützen möchten vorwärts-Iteration ist, können Sie einfach `IEnumerable<T>`.  
  
 **✓ CONSIDER** Unterklassen des generischen Basisklasse Auflistungen anstatt Auflistungen direkt verwenden.  
  
 Dadurch wird ein besserer Name und zum Hinzufügen von Mitgliedern Helfer, die nicht auf die grundlegenden Typen vorhanden sind. Dies gilt insbesondere für APIs auf höherer Ebene.  
  
 **✓ CONSIDER** zurückgeben eine Unterklasse von `Collection<T>` oder `ReadOnlyCollection<T>` aus sehr häufig verwendeter Methoden und Eigenschaften.  
  
 Dadurch wird es, Sie fügen Hilfsmethoden hinzu, oder ändern Sie die Sammlung-Implementierung in der Zukunft.  
  
 **✓ CONSIDER** eine schlüsselgebundene Sammlung verwenden, wenn die in der Auflistung gespeicherten Elemente einen eindeutigen Schlüssel aufweisen (Namen, IDs usw..). Schlüsselgebundene Auflistungen sind Sammlungen, die sowohl eine ganze Zahl als auch einen Schlüssel indiziert werden können und werden in der Regel durch Erben von implementiert `KeyedCollection<TKey,TItem>`.  
  
 Schlüsselgebundene Auflistungen in der Regel größeren Arbeitsspeicher Speicherbedarf haben und sollte nicht verwendet werden, wenn der Speicher-Overhead die Vorteile der Nutzung der Schlüssel überwiegt.  
  
 **X DO NOT** null-Werte zurück, aus der Auflistungseigenschaften oder Methoden Auflistungen zurückgeben. Eine leere Auflistung oder ein leeres Array stattdessen zurück.  
  
 Als allgemeine Regel gilt, dass null und leere (0) elementauflistungen oder Arrays sein soll die gleiche Weise behandelt.  
  
### <a name="snapshots-versus-live-collections"></a>Momentaufnahmen im Vergleich zu Live-Sammlungen  
 Sammlungen, in einen Zustand zu einem bestimmten Zeitpunkt darstellt, werden als Auflistungen von bezeichnet. Beispielsweise wäre eine Auflistung von einer Datenbankabfrage zurückgegebenen Zeilen mit einer Momentaufnahme ab. Auflistungen, die immer den aktuellen Zustand darstellen, werden live Sammlungen bezeichnet. Z. B. eine Auflistung von `ComboBox` Elemente ist eine live-Auflistung.  
  
 **X DO NOT** Momentaufnahme Auflistungen aus Eigenschaften zurückgegeben. Eigenschaften sollten live Sammlungen zurückgeben.  
  
 Eigenschaftengetter sollten sehr einfache Vorgänge. Zurückgeben einer Momentaufnahme erfordert, erstellen eine Kopie einer internen Auflistung in eine o(n)-Operation.  
  
 **✓ DO** verwenden Sie eine Momentaufnahme-Auflistung oder ein live `IEnumerable<T>` (oder dessen Untertyp) zur Darstellung von Auflistungen, die flüchtig sind (d. h., die können ändern, ohne die Auflistung explizit ändern).  
  
 Im Allgemeinen sind alle Sammlungen, die eine freigegebene Ressource (z. B. Dateien in einem Verzeichnis) darstellt flüchtig. Solche Sammlungen sind sehr schwierig oder unmöglich ist, als live-Sammlungen zu implementieren, es sei denn, die Implementierung einfach eine Vorwärts-Enumerator ist.  
  
## <a name="choosing-between-arrays-and-collections"></a>Auswählen zwischen Arrays und Sammlungen  
 **✓ DO** Arrays vorziehen Sammlungen.  
  
 Sammlungen bieten mehr Kontrolle über den Inhalt, können im Laufe der Zeit weiterentwickeln und mehr verwendet werden können. Verwenden von Arrays für nur-Lese Szenarien wird darüber hinaus abgeraten, da die Kosten für das Klonen des Arrays zu hoch sind. Benutzerfreundlichkeit Studien belegen, dass einige Entwickler mehr mithilfe von Sammlungen basierende APIs vertraut.  
  
 Wenn Sie Low-Level-APIs entwickeln, es besser, Arrays für Lese-/ Schreib-Szenarien verwenden möglicherweise jedoch. Arrays haben weniger Speicherbedarf, wodurch das Workingset zu reduzieren, und den Zugriff auf Elemente in einem Array ist schneller, da sie von der Laufzeit optimiert ist.  
  
 **✓ CONSIDER** Verwenden von Arrays in Low-Level-APIs Speicherverbrauch minimieren und Maximieren der Leistung.  
  
 **✓ DO** Bytearrays anstelle von Sammlungen von Bytes verwenden.  
  
 **X DO NOT** Arrays für Eigenschaften verwenden, wenn die Eigenschaft müsste ein neues Array (z. B. eine Kopie eines internen Arrays) jedes Mal zurückgeben, das Eigenschaften-Getter aufgerufen wird.  
  
## <a name="implementing-custom-collections"></a>Implementieren benutzerdefinierte Sammlungen  
 **✓ CONSIDER** erben von `Collection<T>`, `ReadOnlyCollection<T>`, oder `KeyedCollection<TKey,TItem>` beim Entwerfen der neuer Sammlungen.  
  
 **✓ DO** implementieren `IEnumerable<T>` beim Entwerfen der neuer Sammlungen. Erwägen Sie die Implementierung `ICollection<T>` oder sogar `IList<T>` , wo es sinnvoll ist.  
  
 Wenn Sie solche benutzerdefinierten Sammlung implementieren, das folgende Namensgebungsmuster API hergestellt, indem `Collection<T>` und `ReadOnlyCollection<T>` so weit wie möglich. Das heißt, implementieren Sie dieselben Member explizit zu, benennen Sie die Parameter, wie diese usw. nennen Sie diese beiden Auflistungen.  
  
 **✓ CONSIDER** Implementieren von Schnittstellen für nicht generische Auflistung (`IList` und `ICollection`), wenn die Auflistung häufig an APIs übergeben werden diese Schnittstellen als Eingabe annimmt.  
  
 **X AVOID** Collection-Schnittstellen auf Typen mit komplexen APIs, die unabhängig vom stagingstatus des Konzepts einer Auflistung implementieren.  
  
 **X DO NOT** erben von nicht generischen Basisklasse Auflistungen wie z. B. `CollectionBase`. Verwendung `Collection<T>`, `ReadOnlyCollection<T>`, und `KeyedCollection<TKey,TItem>` stattdessen.  
  
### <a name="naming-custom-collections"></a>Benennen benutzerdefinierte Sammlungen  
 Auflistungen (Typen implementiert `IEnumerable`) werden hauptsächlich aus zwei Gründen erstellt: (1), um eine neue Datenstruktur mit Vorgängen Struktur und oft unterschiedliche Leistungsmerkmale als vorhandenen Datenstrukturen zu erstellen (z. B. <xref:System.Collections.Generic.List%601>, <xref:System.Collections.Generic.LinkedList%601>, <xref:System.Collections.Generic.Stack%601>), und (2) erstellen Sie eine spezielle Auflistung für einen bestimmten Satz von Elementen enthält (z. B. <xref:System.Collections.Specialized.StringCollection>). Datenstrukturen werden am häufigsten in der internen Implementierung von Anwendungen und Bibliotheken verwendet. Spezialisierte Auflistungen sind in erster Linie zum in-APIs (als Eigenschaft und Parametertypen) verfügbar gemacht werden.  
  
 **✓ DO** verwenden Sie das Suffix "Wörterbuch" in Namen von Abstraktionen implementieren `IDictionary` oder `IDictionary<TKey,TValue>`.  
  
 **✓ DO** verwenden Sie das Suffix "Collection" im Namen von Typen implementieren `IEnumerable` (oder eines seiner Nachfolger) und eine Liste von Elementen darstellt.  
  
 **✓ DO** verwenden Sie den Namen der entsprechenden Struktur für benutzerdefinierte Datenstrukturen.  
  
 **X AVOID** Suffixe Gleichzeichen bestimmte Implementierung, z. B. "LinkedList" oder "Hashtable", im Namen der Auflistung Abstraktionen verwenden.  
  
 **✓ CONSIDER** Sammlungsnamen mit dem Namen des Elementtyps voranstellen. Z. B. eine Auflistung, die Speichern von Elementen des Typs `Address` (Implementieren von `IEnumerable<Address>`) heißen `AddressCollection`. Wenn der Typ eine Schnittstelle ist, das "I" Präfix des Elements kann Typ ausgelassen werden. Daher eine Sammlung von <xref:System.IDisposable> Elemente können aufgerufen werden, `DisposableCollection`.  
  
 **✓ CONSIDER** das Präfix "ReadOnly" in Namen von schreibgeschützten Auflistungen verwenden, wenn eine entsprechende beschreibbare Auflistung hinzugefügt werden kann oder bereits im Framework vorhanden ist.  
  
 Z. B. eine schreibgeschützte Auflistung von Zeichenfolgen aufgerufen werden soll. `ReadOnlyStringCollection`.  
  
 *Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Siehe auch

- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)  
- [Verwendungsrichtlinien](../../../docs/standard/design-guidelines/usage-guidelines.md)
