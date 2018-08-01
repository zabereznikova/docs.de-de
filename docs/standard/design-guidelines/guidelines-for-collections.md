---
title: Richtlinien für Auflistungen
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 297b8f1d-b11f-4dc6-960a-8e990817304e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3d73ff726e9ddfe1ec1d16dd020f53445f984fb9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33578858"
---
# <a name="guidelines-for-collections"></a>Richtlinien für Auflistungen
Jeder Typ speziell dazu entwickelt, bearbeiten eine Gruppe von Objekten müssen einige gemeinsame Eigenschaften haben, kann eine Auflistung betrachtet werden. Es ist fast immer für solche Typen implementieren <xref:System.Collections.IEnumerable> oder <xref:System.Collections.Generic.IEnumerable%601>, sodass in diesem Abschnitt wird nur Typen, die eine oder beide dieser Schnittstellen implementieren, die Auflistungen werden berücksichtigt.  
  
 **X DO NOT** schwach typisierte Auflistungen in öffentlichen APIs verwenden.  
  
 Der Typ aller Rückgabewerte und Parameter, die Sammelelemente darstellen sollte der genaue Elementtyp, der keine seine Basistypen (Dies gilt nur für öffentliche Member der Auflistung).  
  
 **X DO NOT** verwenden <xref:System.Collections.ArrayList> oder <xref:System.Collections.Generic.List%601> in öffentlichen APIs.  
  
 Diese Typen sind Datenstrukturen, die in der internen Implementierung, die in öffentlichen APIs nicht verwendet werden soll. `List<T>` ist optimiert für Leistung und Energieverbrauch auf Kosten eines erhöhten Voraussichten-APIs und Flexibilität. Wenn Sie zurückkehren, z. B. `List<T>`, nicht jemals werden können, um Benachrichtigungen zu empfangen, wenn Clientcode auf die Auflistung ändert. Darüber hinaus `List<T>` viele Elemente wie z. B. macht <xref:System.Collections.Generic.List%601.BinarySearch%2A>, nicht nützlich oder in vielen Szenarien anwendbar sind. In den folgenden beiden Abschnitten werden die Typen (Abstraktionen) entwickelt, die speziell zur Verwendung in öffentlichen APIs beschrieben.  
  
 **X DO NOT** verwenden `Hashtable` oder `Dictionary<TKey,TValue>` in öffentlichen APIs.  
  
 Diese Typen sind Datenstrukturen, die in der internen Implementierung verwendet werden soll. Öffentliche API zu verwendende <xref:System.Collections.IDictionary>, `IDictionary <TKey, TValue>`, oder ein benutzerdefinierter Typ, der eine oder beide der Schnittstellen implementieren.  
  
 **X DO NOT** verwenden <xref:System.Collections.Generic.IEnumerator%601>, <xref:System.Collections.IEnumerator>, oder eines anderen Typs, die entweder dieser Schnittstellen außer, als den Rückgabetyp implementiert einer `GetEnumerator` Methode.  
  
 Zurückgeben von Enumeratoren aus Methoden außer Typen `GetEnumerator` kann nicht verwendet werden, mit der `foreach` Anweisung.  
  
 **X DO NOT** implementieren sowohl `IEnumerator<T>` und `IEnumerable<T>` für den gleichen Typ. Das gleiche gilt für die nicht generischen Schnittstellen `IEnumerator` und `IEnumerable`.  
  
## <a name="collection-parameters"></a>Parameter für die Datensammlung  
 **✓ DO** verwenden Sie die möglichen Least spezialisierten Typ als Parametertyp. Die meisten Member, die Auflistungen, der als Parameter verwenden, die `IEnumerable<T>` Schnittstelle.  
  
 **X AVOID** mit <xref:System.Collections.Generic.ICollection%601> oder <xref:System.Collections.ICollection> als Parameter nur für den Zugriff auf die `Count` Eigenschaft.  
  
 Verwenden Sie stattdessen `IEnumerable<T>` oder `IEnumerable` und dynamisch wird überprüft, ob das Objekt implementiert `ICollection<T>` oder `ICollection`.  
  
## <a name="collection-properties-and-return-values"></a>Sammlungseigenschaften und Rückgabewerte  
 **X DO NOT** festlegbaren Auflistungseigenschaften bereitstellen.  
  
 Benutzer können den Inhalt der Auflistung ersetzen, indem zuerst das Löschen der Sammlung, und fügen den neuen Inhalt. Ist das Ersetzen der gesamten Sammlung ein häufiges Szenario, in Erwägung ziehen die `AddRange` Methode für die Auflistung.  
  
 **✓ DO** verwenden `Collection<T>` oder eine Unterklasse von `Collection<T>` für Eigenschaften oder des Rückgabewerts darstellen Schreib-Lese-Sammlungen Werte.  
  
 Wenn `Collection<T>` wird eine Anforderung nicht erfüllt (z. B. der Sammlung muss nicht implementiert <xref:System.Collections.IList>), verwenden Sie durch die Implementierung eine benutzerdefinierte Sammlung `IEnumerable<T>`, `ICollection<T>`, oder <xref:System.Collections.Generic.IList%601>.  
  
 **✓ DO** verwenden <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>, eine Unterklasse von `ReadOnlyCollection<T>`, oder in seltenen Fällen `IEnumerable<T>` für Eigenschaften oder des Rückgabewerts darstellen schreibgeschützten Auflistungen Werte.  
  
 Im Allgemeinen verwenden `ReadOnlyCollection<T>`. Wenn sie einige Anforderungen nicht erfüllt (z. B. der Sammlung muss nicht implementiert `IList`), verwenden Sie durch die Implementierung eine benutzerdefinierte Sammlung `IEnumerable<T>`, `ICollection<T>`, oder `IList<T>`. Wenn Sie eine benutzerdefinierte schreibgeschützte Auflistung implementieren, implementieren `ICollection<T>.IsReadOnly` zurückzugebenden `true`.  
  
 In Fällen, in denen sind Sie sicher, dass das einzige Szenario, die jemals unterstützen möchten Vorwärtscursor Iteration ist, können Sie einfach `IEnumerable<T>`.  
  
 **✓ CONSIDER** Unterklassen des generischen Basisklasse Auflistungen anstatt Auflistungen direkt verwenden.  
  
 Dadurch kann für ein besserer Name und zum Hinzufügen von Mitgliedern Hilfsfunktion, die nicht auf die grundlegenden Typen vorhanden sind. Dies gilt insbesondere für allgemeine APIs.  
  
 **✓ CONSIDER** zurückgeben eine Unterklasse von `Collection<T>` oder `ReadOnlyCollection<T>` aus sehr häufig verwendeter Methoden und Eigenschaften.  
  
 Dies wird erleichtern Sie fügen Hilfsmethoden hinzu, oder ändern Sie die Sammlung-Implementierung in der Zukunft.  
  
 **✓ CONSIDER** eine schlüsselgebundene Sammlung verwenden, wenn die in der Auflistung gespeicherten Elemente einen eindeutigen Schlüssel aufweisen (Namen, IDs usw..). Schlüsselgebundene Auflistungen sind Sammlungen, die indiziert werden können, indem Sie eine ganze Zahl und einen Schlüssel und sind in der Regel durch Vererben von implementiert `KeyedCollection<TKey,TItem>`.  
  
 Schlüsselgebundene Auflistungen in der Regel größeren Arbeitsspeicher belegen nur wenig Arbeitsspeicher haben und sollte nicht verwendet werden, wenn der Speicher-Overhead ergeben sich folgende Vorteile die Schlüssel überwiegt.  
  
 **X DO NOT** null-Werte zurück, aus der Auflistungseigenschaften oder Methoden Auflistungen zurückgeben. Eine leere Auflistung oder ein leeres Array stattdessen zurückgeben.  
  
 Als allgemeine Regel gilt, dass null und leere (0) elementauflistungen oder Arrays sein soll, die gleiche Weise behandelt.  
  
### <a name="snapshots-versus-live-collections"></a>Momentaufnahmen im Vergleich zu Live Sammlungen  
 Sammlungen, die einen Status zu einem Zeitpunkt darstellt, werden als Momentaufnahme Sammlungen bezeichnet. Beispielsweise wäre eine Auflistung von einer Datenbankabfrage zurückgegebenen Zeilen mit einer Momentaufnahme ab. Sammlungen, die immer den aktuellen Status darstellen sind live Sammlungen aufgerufen. Angenommen, eine Auflistung von `ComboBox` Elemente wird eine live-Auflistung.  
  
 **X DO NOT** Momentaufnahme Auflistungen aus Eigenschaften zurückgegeben. Eigenschaften sollten live Auflistungen zurückgeben.  
  
 Eigenschaftengetter sollte sehr einfache Vorgänge. Zurückgeben einer Momentaufnahme erfordert, erstellen eine Kopie einer internen Auflistung in einem Vorgang O(n).  
  
 **✓ DO** verwenden Sie eine Momentaufnahme-Auflistung oder ein live `IEnumerable<T>` (oder dessen Untertyp) zur Darstellung von Auflistungen, die flüchtig sind (d. h., die können ändern, ohne die Auflistung explizit ändern).  
  
 Im Allgemeinen sind alle Sammlungen, die eine freigegebene Ressource (z. B. Dateien in einem Verzeichnis) darstellt flüchtig. Solche Sammlungen sind sehr schwer oder gar nicht als live-Auflistungen implementieren, es sei denn, die Implementierung einfach einen Vorwärtscursor Enumerator ist.  
  
## <a name="choosing-between-arrays-and-collections"></a>Auswählen zwischen Arrays und Sammlungen  
 **✓ DO** Arrays vorziehen Sammlungen.  
  
 Sammlungen bieten mehr Kontrolle über den Inhalt, können mit der Zeit weiterentwickelt und mehr verwendet werden können. Verwenden von Arrays für nur-Lese Szenarien wird darüber hinaus abgeraten, da die Kosten für das Array zu klonen hoch ist. Nutzbarkeit Studien haben gezeigt, dass einige Entwickler nachrichtenorientierten Auflistung basierende APIs verwenden können.  
  
 Jedoch wenn Sie Low-Level-APIs entwickeln, kann es besser für Szenarien mit Lese-/ Schreibzugriff Arrays zu verwenden sein. Arrays haben einen weniger Speicher beansprucht, was hilft, das Workingset zu reduzieren, und den Zugriff auf Elemente in einem Array ist schneller, da er von der Laufzeit optimiert ist.  
  
 **✓ CONSIDER** Verwenden von Arrays in Low-Level-APIs Speicherverbrauch minimieren und Maximieren der Leistung.  
  
 **✓ DO** Bytearrays anstelle von Sammlungen von Bytes verwenden.  
  
 **X DO NOT** Arrays für Eigenschaften verwenden, wenn die Eigenschaft müsste ein neues Array (z. B. eine Kopie eines internen Arrays) jedes Mal zurückgeben, das Eigenschaften-Getter aufgerufen wird.  
  
## <a name="implementing-custom-collections"></a>Implementieren benutzerdefinierte Sammlungen  
 **✓ CONSIDER** erben von `Collection<T>`, `ReadOnlyCollection<T>`, oder `KeyedCollection<TKey,TItem>` beim Entwerfen der neuer Sammlungen.  
  
 **✓ DO** implementieren `IEnumerable<T>` beim Entwerfen der neuer Sammlungen. Implementieren Sie `ICollection<T>` oder sogar `IList<T>` , in denen es sinnvoll.  
  
 Wenn Sie solche benutzerdefinierten Auflistung implementieren zu können, führen Sie das API-Muster, die durch die `Collection<T>` und `ReadOnlyCollection<T>` so getreu wie möglich. Das heißt, implementieren Sie das dieselben Member explizit zu, benennen Sie die Parameter aus, wie diese beiden Auflistungen werden usw. benennen.  
  
 **✓ CONSIDER** Implementieren von Schnittstellen für nicht generische Auflistung (`IList` und `ICollection`), wenn die Auflistung häufig an APIs übergeben werden diese Schnittstellen als Eingabe annimmt.  
  
 **X AVOID** Collection-Schnittstellen auf Typen mit komplexen APIs, die unabhängig vom stagingstatus des Konzepts einer Auflistung implementieren.  
  
 **X DO NOT** erben von nicht generischen Basisklasse Auflistungen wie z. B. `CollectionBase`. Verwendung `Collection<T>`, `ReadOnlyCollection<T>`, und `KeyedCollection<TKey,TItem>` stattdessen.  
  
### <a name="naming-custom-collections"></a>Benennen benutzerdefinierte Sammlungen  
 Auflistungen (Typen implementiert, `IEnumerable`), die hauptsächlich aus zwei Gründen erstellt werden: (1), um eine neue Datenstruktur mit Vorgängen Struktur und häufig unterschiedlichen Leistungsmerkmalen als vorhandenen Datenstrukturen erstellen (z. B. <xref:System.Collections.Generic.List%601>, <xref:System.Collections.Generic.LinkedList%601>, <xref:System.Collections.Generic.Stack%601>), und (2), um eine spezielle Auflistung für die Aufnahme von einer bestimmten Gruppe von Elementen zu erstellen (z. B. <xref:System.Collections.Specialized.StringCollection>). Datenstrukturen werden am häufigsten in die interne Implementierung der Anwendungen und Bibliotheken verwendet. Spezialisierte Auflistungen werden hauptsächlich in APIs (als Eigenschaft und Parametertypen) verfügbar gemacht werden.  
  
 **✓ DO** verwenden Sie das Suffix "Wörterbuch" in Namen von Abstraktionen implementieren `IDictionary` oder `IDictionary<TKey,TValue>`.  
  
 **✓ DO** verwenden Sie das Suffix "Collection" im Namen von Typen implementieren `IEnumerable` (oder eines seiner Nachfolger) und eine Liste von Elementen darstellt.  
  
 **✓ DO** verwenden Sie den Namen der entsprechenden Struktur für benutzerdefinierte Datenstrukturen.  
  
 **X AVOID** Suffixe Gleichzeichen bestimmte Implementierung, z. B. "LinkedList" oder "Hashtable", im Namen der Auflistung Abstraktionen verwenden.  
  
 **✓ CONSIDER** Sammlungsnamen mit dem Namen des Elementtyps voranstellen. Angenommen, eine Auflistung, die Speichern von Elementen des Typs `Address` (implementieren `IEnumerable<Address>`) heißen `AddressCollection`. Wenn der Typ eine Schnittstelle ist, das "I" als Präfix des Elements Art ausgelassen werden kann. Daher wird eine Auflistung von <xref:System.IDisposable> Elemente können aufgerufen werden, `DisposableCollection`.  
  
 **✓ CONSIDER** das Präfix "ReadOnly" in Namen von schreibgeschützten Auflistungen verwenden, wenn eine entsprechende beschreibbare Auflistung hinzugefügt werden kann oder bereits im Framework vorhanden ist.  
  
 Angenommen, eine schreibgeschützte Auflistung von Zeichenfolgen aufgerufen werden `ReadOnlyStringCollection`.  
  
 *Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*  
  
## <a name="see-also"></a>Siehe auch  
 [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)  
 [Verwendungsrichtlinien](../../../docs/standard/design-guidelines/usage-guidelines.md)
