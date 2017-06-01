---
title: "Richtlinien f&#252;r Auflistungen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: 297b8f1d-b11f-4dc6-960a-8e990817304e
caps.latest.revision: 4
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 4
---
# Richtlinien f&#252;r Auflistungen
Vor allem zum Bearbeiten einer Gruppenstatus von Objekten müssen einige gemeinsame Eigenschaften haben keinerlei kann eine Auflistung betrachtet werden. Es ist fast immer für solche Typen implementieren <xref:System.Collections.IEnumerable> oder <xref:System.Collections.Generic.IEnumerable%601>, sodass in diesem Abschnitt wird nur eine oder beide dieser Schnittstellen implementieren Sammlungen zu berücksichtigen.  
  
 **X nicht** mithilfe von schwach typisierten Sammlungen von öffentlichen APIs.  
  
 Der Typ aller Rückgabewerte und Parameter, die Auflistungselemente darstellen sollte der genaue Typ, keine seine Basistypen \(Dies gilt nur für öffentliche Member der Auflistung\).  
  
 **X nicht** verwenden <xref:System.Collections.ArrayList> oder <xref:System.Collections.Generic.List%601> in öffentlichen APIs.  
  
 Diese Typen sind Datenstrukturen, die in der internen Implementierung von öffentlichen APIs nicht verwendet werden soll.`List<T>` ist für Leistung und Energieverbrauch auf Kosten der APIs und Flexibilität Voraussichten optimiert. Wenn Sie zurückgeben, z. B. `List<T>`, nicht einmal werden benachrichtigt, wenn der Clientcode die Auflistung geändert werden können. Darüber hinaus `List<T>` verfügbar macht viele Member, wie z. B. <xref:System.Collections.Generic.List%601.BinarySearch%2A>, nicht hilfreich oder in vielen Szenarien anwendbar sind. Die folgenden zwei Abschnitte beschreiben die Typen \(Abstraktionen\), die speziell für die Verwendung in öffentlichen APIs vorgesehen.  
  
 **X nicht** verwenden `Hashtable` oder `Dictionary<TKey,TValue>` in öffentlichen APIs.  
  
 Diese Typen sind Datenstrukturen, die in der internen Implementierung verwendet werden soll. Öffentliche APIs sollten verwenden <xref:System.Collections.IDictionary>, `IDictionary <TKey, TValue>`, oder ein benutzerdefinierter Typ, der eine oder beide der Schnittstellen implementieren.  
  
 **X nicht** verwenden <xref:System.Collections.Generic.IEnumerator%601>, <xref:System.Collections.IEnumerator>, oder einen anderen Typ, die eine dieser Schnittstellen außer, als den Rückgabetyp implementiert einer `GetEnumerator` Methode.  
  
 Typen, die Methoden als Enumeratoren Remoteanmeldeversuch `GetEnumerator` kann nicht verwendet werden, mit der `foreach` Anweisung.  
  
 **X nicht** implementieren beide `IEnumerator<T>` und `IEnumerable<T>` auf dem gleichen Typ. Das gleiche gilt für den nicht generischen Schnittstellen `IEnumerator` und `IEnumerable`.  
  
## Auflistung von Parametern  
 **✓ führen** verwenden Sie als Parametertyp die wenigsten spezialisierte Typ möglich. Die meisten Member Sammlungen benötigt, als Parameter verwendet die `IEnumerable<T>` Schnittstelle.  
  
 **X vermeiden** mit <xref:System.Collections.Generic.ICollection%601> oder <xref:System.Collections.ICollection> als Parameter nur für den Zugriff auf die `Count` Eigenschaft.  
  
 Verwenden Sie stattdessen `IEnumerable<T>` oder `IEnumerable` und dynamisch überprüfen, ob das Objekt implementiert `ICollection<T>` oder `ICollection`.  
  
## Von Auflistungseigenschaften und Rückgabewerte  
 **X nicht** festlegbare Auflistungseigenschaften bereitstellen.  
  
 Benutzer können den Inhalt der Auflistung ersetzen, indem die Auflistung zuerst löschen und dann den neuen Inhalt hinzufügen. Falls die ganze Auflistung ersetzen ein häufiges Szenario ist, sollten Sie die `AddRange` \-Methode für die Auflistung.  
  
 **✓ führen** verwenden `Collection<T>` oder eine Unterklasse von `Collection<T>` Eigenschaften oder des Rückgabewerts für Lese\-\/Schreibzugriff Sammlungen Werte.  
  
 Wenn `Collection<T>` einige Voraussetzung nicht erfüllt \(z. B. die Auflistung muss nicht implementieren <xref:System.Collections.IList>\), verwenden Sie eine benutzerdefinierte Auflistung durch die Implementierung `IEnumerable<T>`, `ICollection<T>`, oder <xref:System.Collections.Generic.IList%601>.  
  
 **✓ führen** verwenden <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>, eine Unterklasse von `ReadOnlyCollection<T>`, oder in seltenen Fällen `IEnumerable<T>` Eigenschaften oder des Rückgabewerts Werte darstellen schreibgeschützten Auflistungen.  
  
 Im Allgemeinen verwenden `ReadOnlyCollection<T>`. Wenn sie eine Anforderung nicht erfüllt \(z. B. die Auflistung muss nicht implementieren `IList`\), verwenden Sie eine benutzerdefinierte Auflistung durch die Implementierung `IEnumerable<T>`, `ICollection<T>`, oder `IList<T>`. Wenn Sie eine benutzerdefinierte Auflistung schreibgeschützt implementieren, implementieren `ICollection<T>.ReadOnly` "false" zurückgibt.  
  
 In Fällen, in denen Sie sicher, dass das einzige Szenario Sie jemals unterstützen möchten Vorwärtscursor Iteration ist, können Sie einfach `IEnumerable<T>`.  
  
 **✓ ggf.** mit Unterklassen von generischen Basisklasse Auflistungen statt direkt unter Verwendung der Auflistung.  
  
 Dadurch können für einen besseren und zum Hinzufügen von Mitgliedern Helfer, die nicht auf die grundlegenden Typen vorhanden sind. Dies gilt insbesondere für allgemeine APIs.  
  
 **✓ ggf.** zurückgeben eine Unterklasse von `Collection<T>` oder `ReadOnlyCollection<T>` von häufig verwendeten Methoden und Eigenschaften.  
  
 Dadurch wird es, Sie Hilfsmethoden hinzufügen oder ändern Sie die Sammlung\-Implementierung in der Zukunft.  
  
 **✓ ggf.** eine schlüsselgebundene Sammlung verwenden, wenn in der Auflistung gespeicherten Elemente einen eindeutigen Schlüssel aufweisen \(Namen, IDs usw..\). Schlüsselgebundene Auflistungen sind Sammlungen, die indiziert werden können, indem Sie eine ganze Zahl und einen Schlüssel und werden normalerweise durch Erben von implementiert `KeyedCollection<TKey,TItem>`.  
  
 Schlüsselgebundene Auflistungen in der Regel größeren Arbeitsspeicher Speicherbedarf haben und sollte nicht verwendet werden, wenn der Speicher\-Overhead die Vorteile der Schlüssel überwiegt.  
  
 **X nicht** null\-Werte zurück, aus der Auflistungseigenschaften oder aus Methoden Auflistungen zurückgeben. Eine leere Auflistung oder ein leeres Array stattdessen zurück.  
  
 Als allgemeine Regel gilt, dass null und leere \(Element 0\)\-Sammlungen und Arrays ist die gleiche Weise behandelt.  
  
### Momentaufnahmen im Vergleich zu Live\-Sammlungen  
 Sammlungen, Zeitpunkt von einem Zustand zu einem bestimmten Zeitpunkt darstellt, werden Snapshot Sammlungen bezeichnet. Zum Beispiel wäre eine Auflistung von einer Datenbankabfrage zurückgegebenen Zeilen mit einer Momentaufnahme. Sammlungen, die immer den aktuellen Zustand darstellen, werden live Sammlungen bezeichnet. Zum Beispiel eine Auflistung von `ComboBox` Elemente ist eine live\-Auflistung.  
  
 **X nicht** Snapshot Auflistungen von Eigenschaften zurückgeben. Eigenschaften sollten live Auflistungen zurückgeben.  
  
 Eigenschaftengetter sollten sehr einfache Operationen ausgeführt werden. Zurückgeben einer momentaufnahmes erfordert, erstellen eine Kopie einer internen Auflistung in einem Vorgang O\(n\).  
  
 **✓ führen** verwenden eine Snapshot\-Auflistung oder ein `IEnumerable<T>` \(oder den Untertyp\) Sammlungen dar, die flüchtig sind \(d. h., die können ändern, ohne explizit ändern der Auflistung\).  
  
 Im Allgemeinen sind alle Sammlungen, die eine freigegebene Ressource \(z. B. Dateien in einem Verzeichnis\) darstellt flüchtig. Diese Sammlungen sind sehr schwierig oder unmöglich ist, als live Sammlungen zu implementieren, es sei denn, die Implementierung einfach einen vorwärtsgerichteten\-Enumerator ist.  
  
## Auswählen zwischen Arrays und Sammlungen  
 **✓ führen** Arrays vorziehen Sammlungen.  
  
 Sammlungen bieten mehr Kontrolle über den Inhalt, können mit der Zeit weiterentwickelt und mehr verwendet werden können. Verwenden von Arrays für nur\-Lese Szenarien ist darüber hinaus abzuraten, da die Kosten für das Klonen des Arrays zu hoch sind. Nutzbarkeit Studien, dass manche Entwickler mehr mithilfe von Sammlungen basierende APIs vertraut.  
  
 Wenn Sie Low\-Level\-APIs entwickeln, es besser, Arrays für Lese\-\/ Schreib\-Szenarien verwenden möglicherweise jedoch. Arrays haben einen geringeren Speicherbedarf, wodurch das Workingset zu reduzieren, und den Zugriff auf Elemente in einem Array ist schneller, da er von der Laufzeit optimiert ist.  
  
 **✓ ggf.** mithilfe von Arrays in Low\-Level\-APIs zur Minimierung der Speicherbedarf und die Leistung optimieren.  
  
 **✓ führen** Bytearrays anstelle von Sammlungen von Bytes verwenden.  
  
 **X nicht** Arrays für Eigenschaften verwenden, wenn die Eigenschaft müsste ein neues Array \(z. B. eine Kopie eines internen Arrays\) jedes Mal zurück, der Eigenschaften\-Getter aufgerufen wird.  
  
## Implementieren von benutzerdefinierten Sammlungen  
 **✓ ggf.** erben von `Collection<T>`, `ReadOnlyCollection<T>`, oder `KeyedCollection<TKey,TItem>` beim Entwerfen von neuer Sammlungen.  
  
 **✓ führen** implementieren `IEnumerable<T>` beim Entwerfen von neuer Sammlungen. Implementieren Sie `ICollection<T>` oder sogar `IList<T>` in denen es sinnvoll.  
  
 Wenn Sie eine solche benutzerdefinierte Auflistung implementieren, führen Sie das API\-Muster wird hergestellt `Collection<T>` und `ReadOnlyCollection<T>` so weit wie möglich. Das heißt, implementieren Sie dieselben Member explizit zu, benennen Sie die Parameter zu, wie diese beiden Sammlungen diese usw. nennen.  
  
 **✓ ggf.** generischen Schnittstellen implementieren \(`IList` und `ICollection`\), wenn die Auflistung häufig an APIs übergeben werden diese Schnittstellen als Eingabe annimmt.  
  
 **X vermeiden** Implementieren von Auflistungsschnittstellen für Typen mit komplexen APIs, die nicht mit dem Konzept einer Auflistung.  
  
 **X nicht** erben von nicht generischen Basisklasse Auflistungen, wie z. B. `CollectionBase`. Mit `Collection<T>`, `ReadOnlyCollection<T>`, und `KeyedCollection<TKey,TItem>` stattdessen.  
  
### Benennen benutzerdefinierte Sammlungen  
 Sammlungen \(Typen implementiert `IEnumerable`\) werden in erster Linie aus zwei Gründen erstellt: \(1\), erstellen Sie eine neue Datenstruktur mit Struktur\-spezifische Vorgänge und oft unterschiedliche Leistungsmerkmale als vorhandene Datenstrukturen \(z. B.  <xref:System.Collections.Generic.List%601>, <xref:System.Collections.Generic.LinkedList%601>, <xref:System.Collections.Generic.Stack%601>\), und \(2\) eine spezielle Auflistung enthält einen bestimmten Satz von Elementen zu erstellen \(z. B.  <xref:System.Collections.Specialized.StringCollection>\). Datenstrukturen werden meist in der internen Implementierung von Anwendungen und Bibliotheken verwendet. Spezialisierte Auflistungen sind in erster Linie zum in\-APIs \(als Eigenschaft und Parametertypen\) verfügbar gemacht werden.  
  
 **✓ führen** verwenden Sie das Suffix "Wörterbuch" im Namen von Abstraktionen implementieren `IDictionary` oder `IDictionary<TKey,TValue>`.  
  
 **✓ führen** verwenden Sie das Suffix "Collection" im Namen von Typen implementieren `IEnumerable` \(oder eines seiner untergeordneten Elemente\) und eine Liste von Elementen darstellt.  
  
 **✓ führen** verwenden Sie den Namen der entsprechenden Struktur für benutzerdefinierte Datenstrukturen.  
  
 **X vermeiden** alle Suffixe, dass bestimmte Implementierung, z. B. "LinkedList" oder "Hashtable" im Namen der Auflistung Abstraktionen verwenden.  
  
 **✓ ggf.** Sammlungsnamen mit dem Namen des Elementtyps voranstellen. Z. B. eine Auflistung, die Speichern von Elementen des Typs `Address` \(implementieren `IEnumerable<Address>`\) sollte mit dem Namen `AddressCollection`. Wenn der Typ eine Schnittstelle ist, das "I"\-Präfix des Artikels Typ ausgelassen werden. Folglich eine Auflistung von <xref:System.IDisposable> Elemente können aufgerufen werden, `DisposableCollection`.  
  
 **✓ ggf.** das Präfix "ReadOnly" in Namen von schreibgeschützten Auflistungen verwenden, wenn eine entsprechende beschreibbare Auflistung hinzugefügt oder bereits im Framework vorhanden ist.  
  
 Angenommen, eine schreibgeschützte Auflistung von Zeichenfolgen aufgerufen werden `ReadOnlyStringCollection`.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc. aus [Framework\-Entwurfsrichtlinien: Konventionen, Ausdrücke und Muster für wieder verwendbare .NET\-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) vom 22. Oktober 2008 von Addison\-Wesley Professional als Teil der Microsoft Windows Development\-Reihe von Krzysztof Cwalina und Brad Abrams, veröffentlicht.*  
  
## Siehe auch  
 [Framework\-Entwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)   
 [Verwendungsrichtlinien](../../../docs/standard/design-guidelines/usage-guidelines.md)