---
title: "Enum-Entwurf | Microsoft Docs"
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
helpviewer_keywords: 
  - "Typentwurfsrichtlinien Enumerationen"
  - "Einfache Enumerationen"
  - "[Enumerationen [.NET Framework], Entwurfsrichtlinien"
  - "Klassenbibliotheken – Entwurfsrichtlinien [.NET Framework], Enumerationen"
  - "Flags-Enumerationen"
ms.assetid: dd53c952-9d9a-4736-86ff-9540e815d545
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Enum-Entwurf
Enumerationen sind eine besondere Art von Typ. Es gibt zwei Arten von Enumerationen: Einfache Enumerationen und Flags\-Enumerationen.  
  
 Einfache Enumerationen stellen kleine geschlossene Sätze von Optionen dar. Ein allgemeines Beispiel für die einfache Enumeration ist ein Satz von Farben.  
  
 Flags\-Enumerationen dienen zur Unterstützung der bitweiser Operations für die Enum\-Werte. Ein allgemeines Beispiel für die Flags\-Enumeration ist eine Liste der Optionen.  
  
 **✓ führen** mit, dass eine Enumeration typisieren Parameter, Eigenschaften und Rückgabewerte, die Sätze von Werten darstellen.  
  
 **✓ führen** bevorzugen die Verwendung einer Enumeration anstelle von statischen Konstanten.  
  
 **X nicht** Enum für offene Gruppen \(z. B. die Betriebssystemversion, die Namen Ihrer Freunde usw.\) verwenden.  
  
 **X nicht** Geben Sie für die zukünftige Verwendung reservierten Enumerationswerte, die vorgesehen sind.  
  
 Sie können Werte immer einfach in die vorhandene Enumeration zu einem späteren Zeitpunkt hinzufügen. Finden Sie unter [Hinzufügen von Werten für Enumerationen](#add_value) ausführliche Informationen zum Hinzufügen von Werten zu Enumerationen. Reservierte Werte einfach verunreinigen den Satz von realen Werten und tendenziell zu Benutzerfehlern führen.  
  
 **X vermeiden** öffentlich verfügbar machen Enumerationen mit nur einem Wert.  
  
 Eine gängige Praxis für die zukünftige Erweiterbarkeit von C\-APIs ist Methodensignaturen reservierte Parameter hinzu. Dieser reservierte Parameter können als Enumerationen mit einem einzelnen Standardwert ausgedrückt werden. Dies sollte nicht verwalteter APIs erfolgen. Überladen von Methoden ermöglicht das Hinzufügen von Parametern in zukünftigen Versionen.  
  
 **X nicht** Sentinel Werte in Enumerationen.  
  
 Obwohl sie manchmal hilfreich, Framework\-Entwickler sind, sind Sentinel Werte für Benutzer von Framework verwirrend. Sie werden zum Nachverfolgen des Zustands statt wird einer der Werte der Enumeration aus der Gruppe, die durch die Enumeration dargestellt.  
  
 **✓ führen** Geben Sie einen Wert von 0 \(null\) auf einfache Enumerationen.  
  
 Rufen Sie den Wert wie "None". Wenn dieser Wert nicht für diese bestimmte Enumeration geeignet ist, sollte der am häufigsten verwendete Standardwert für die Enumeration den zugrunde liegenden Wert 0 \(null\) zugewiesen werden.  
  
 **✓ ggf.** mit <xref:System.Int32> \(die Standardeinstellung in den meisten Programmiersprachen\) der zugrunde liegende Typ einer Enumeration, wenn eine der folgenden Aussagen zutrifft:  
  
-   Die Enumeration ist eine Flags\-Enumeration, und Sie haben mehr als 32 Flags oder mehr in der Zukunft haben.  
  
-   Der zugrunde liegende Typ muss anders als <xref:System.Int32> für die Interoperabilität mit nicht verwaltetem Code erwartet andere Größe Enumerationen erleichtern.  
  
-   Ein kleinerer zugrunde liegender Typ führt zu wesentlicher Einsparung an Speicherplatz. Wenn Sie erwarten, dass ein Enum hauptsächlich als ein Argument für den Verlauf des Steuerelements verwendet werden soll, wird die Größe kaum einen Unterschied. Die Größe entlastet möglicherweise werden wenn:  
  
    -   Sie erwarten, dass die Enumeration als Feld in einer sehr häufig instanziierten Struktur oder Klasse verwendet werden.  
  
    -   Sie erwarten, dass Benutzer große Arrays oder Auflistungen der Enum\-Instanzen erstellen.  
  
    -   Sie erwarten, dass eine große Anzahl von Instanzen der Enumeration serialisiert werden soll.  
  
 Für die Verwendung im Arbeitsspeicher, Bedenken Sie, dass verwaltete Objekte immer sind `DWORD`\-ausgerichtet, so dass Sie tatsächlich mehrere Enumerationen oder andere kleineren Strukturen in einer Instanz in eine kleinere Enumeration mit pack um einen Unterschied machen, da die Größe der gesamten Instanz immer gerundet werden soll eine `DWORD`.  
  
 **✓ führen** Namen Flags\-Enumerationen mit Nomen im plural oder Substantivausdrücke und einfache Enumerationen im singular Nomen und nominale Ausdrücke.  
  
 **X nicht** erweitern <xref:System.Enum?displayProperty=fullName> direkt.  
  
 <xref:System.Enum?displayProperty=fullName> eine besondere Art ist von der CLR zum Erstellen von benutzerdefinierten Enumerationen verwendet werden. Die meisten Programmiersprachen bieten ein Programmierelement, die Sie Zugriff auf diese Funktionalität zu erhalten. Zum Beispiel in c\# die `enum` \-Schlüsselwort verwendet, um eine Enumeration zu definieren.  
  
<a name="design"></a>   
### Entwerfen von Flags\-Enumerationen  
 **✓ führen** gelten die <xref:System.FlagsAttribute?displayProperty=fullName> Flags\-Enumerationen. Dieses Attribut nicht auf einfache Enumerationen anwenden.  
  
 **✓ führen** Potenzen von 2 für die Kennzeichnung Enum\-Werte verwenden, damit sie frei kombiniert werden können mithilfe des bitweise OR\-Operation.  
  
 **✓ ggf.** Kombinationen von Flags besondere Enumerationswerte für häufig Bereitstellung verwendet.  
  
 Bitweise Operationen sollte sind ein erweitertes Konzept und nicht für einfache Aufgaben erforderlich.<xref:System.IO.FileAccess> ist ein Beispiel eines speziellen Werts.  
  
 **X vermeiden** Erstellen von Flags\-Enumerationen, in denen bestimmte Kombinationen von Werten ungültig sind.  
  
 **X vermeiden** mit Enum\-Werte von 0 \(null\) kennzeichnen, es sei denn, der Wert für "alle Flags deaktiviert sind" und gemäß der nächsten Richtlinie entsprechend benannt ist.  
  
 **✓ führen** nennen Sie den Wert 0 \(null\) von Flags\-Enumerationen `None`. Für eine Flags\-Enumeration muss der Wert bedeuten immer "alle Flags deaktiviert sind."  
  
<a name="add_value"></a>   
### Mehrwert für Enumerationen  
 Es ist üblich, um zu ermitteln, müssen Sie die Werte einer Enumeration hinzufügen, nachdem Sie bereits geliefert haben. Besteht eine potenziellen Problems "Anwendungskompatibilität" Wenn der neu hinzugefügten Wert aus einer vorhandenen API, zurückgegeben wird da schlecht geschriebenen Anwendung den neuen Wert nicht ordnungsgemäß verarbeiten können.  
  
 **✓ ggf.** trotz eines geringen Kompatibilitätsproblems Enumerationen Werte hinzufügen.  
  
 Bei echte Daten zu Anwendungsinkompatibilitäten durch Hinzufügen einer Enumeration ist sinnvoll, eine neue API, die die alten und neuen Werte zurückgibt, und setzt die alte API, die fortgesetzt werden soll, nur die alten Werte zurückgeben. Dadurch wird sichergestellt, dass Ihre vorhandenen Anwendungen kompatibel bleiben.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc. aus [Framework\-Entwurfsrichtlinien: Konventionen, Ausdrücke und Muster für wieder verwendbare .NET\-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) vom 22. Oktober 2008 von Addison\-Wesley Professional als Teil der Microsoft Windows Development\-Reihe von Krzysztof Cwalina und Brad Abrams, veröffentlicht.*  
  
## Siehe auch  
 [Typentwurfsrichtlinien](../../../docs/standard/design-guidelines/type.md)   
 [Framework\-Entwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)