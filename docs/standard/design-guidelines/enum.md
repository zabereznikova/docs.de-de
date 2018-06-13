---
title: Enum-Entwurf
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, enumerations
- simple enumerations
- enumerations [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], enumerations
- flags enumerations
ms.assetid: dd53c952-9d9a-4736-86ff-9540e815d545
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 544f617ca3a352814504125d7a61d70db5a81566
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33579248"
---
# <a name="enum-design"></a>Enum-Entwurf
Enumerationen sind eine besondere Art von Werttyp. Es gibt zwei Arten von Enumerationen: Einfache Enumerationen und Flags-Enumerationen.  
  
 Einfache Enumerationen stellen kleine geschlossene Sätze von Optionen dar. Ein gängiges Beispiel der einfachen Enumeration ist ein Satz von Farben.  
  
 Flags-Enumerationen dienen zur Unterstützung von bitweiser Operations für den Enum-Werte. Ein gängiges Beispiel Flags-Enumeration wird eine Liste der Optionen an.  
  
 **Führen Sie ✓** mit, dass eine Enumeration typisieren Parameter, Eigenschaften und Rückgabewerte, die Sätze von Werten darstellen.  
  
 **Führen Sie ✓** statische Konstanten anstelle einer Enumeration begünstigen.  
  
 **X nicht** Enum für offene Gruppen (z. B. die Version des Betriebssystems, Namen von Ihrer Freunde usw.) verwenden.  
  
 **X nicht** Geben Sie für die zukünftige Verwendung reservierte Enumerationswerte, die vorgesehen sind.  
  
 Sie können Werte immer einfach der vorhandenen Enumeration zu einem späteren Zeitpunkt hinzufügen. Finden Sie unter [Hinzufügen von Werten für Enumerationen](#add_value) detaillierte Informationen zum Hinzufügen von Werten für Enumerationen. Reservierten Werte einfach dadurch die echte Wertemenge und tendenziell zu Benutzerfehler führen.  
  
 **X vermeiden** öffentlich verfügbar machen Enumerationen mit nur einem Wert.  
  
 Üblicherweise für zukünftige Erweiterungen der C-APIs sichergestellt wird Methodensignaturen reservierte Parameter hinzu. Solche reservierte Parameter können als Enumerationen mit einem einzelnen Wert ausgedrückt werden. Dies sollte nicht in der verwalteten APIs erfolgen. Überladen von Methoden ermöglicht das Hinzufügen von Parametern in zukünftigen Versionen.  
  
 **X nicht** Sentinel Werte in Enumerationen enthalten.  
  
 Obwohl sie manchmal hilfreich, Frameworkentwickler sind, sind Sentinel Werte für Benutzer von Framework verwirrend. Sie werden verwendet, den Status der Enumeration, statt wird einer der Werte aus der Gruppe, dargestellt durch die Enumeration zu verfolgen.  
  
 **Führen Sie ✓** Geben Sie einen Wert von 0 zu einfachen Enumerationen.  
  
 Rufen Sie den Wert etwa "None". Wenn ein solcher Wert nicht für diese bestimmte Enumeration geeignet ist, sollte der am häufigsten verwendete Standardwert für die Enumeration den zugrunde liegenden Wert von 0 (null) zugewiesen werden.  
  
 **✓ GGF.** mit <xref:System.Int32> (die Standardeinstellung in den meisten Programmiersprachen) als zugrunde liegende Typ einer Enumeration, wenn eine der folgenden Aussagen zutrifft:  
  
-   Die Enumeration ist eine Flags-Enumeration, und Sie haben mehr als 32 Flags, oder voraussichtlich mehr in der Zukunft verbunden.  
  
-   Der zugrunde liegende Typ benötigt werden, anders als <xref:System.Int32> für Interoperabilität mit nicht verwaltetem Code erwartet andere Größe Enumerationen erleichtern.  
  
-   Eine kleinere zugrunde liegenden Typs führt zu erheblichen einsparungen im Raum. Wenn Sie erwarten, dass ein Enum hauptsächlich als ein Argument für den steuerungsverlauf verwendet werden soll, wird die Größe nur ein geringer Unterschied. Die Größe einsparungen können erheblich sein wenn:  
  
    -   Sie erwarten, dass die Enumeration als Feld in einer sehr häufig instanziierten Struktur oder Klasse verwendet werden.  
  
    -   Sie erwarten, dass Benutzer große Arrays oder Auflistungen von Enum-Instanzen erstellen.  
  
    -   Sie erwarten, dass eine große Anzahl von Instanzen der Enumeration serialisiert werden soll.  
  
 Für die Verwendung im Arbeitsspeicher, Bedenken Sie, dass verwaltete Objekte immer sind `DWORD`-ausgerichtet, sodass effektiv mehrere Enumerationen oder andere kleineren Strukturen in einer Instanz auf eine kleinere Aufzählung mit pack um einen Unterschied machen, da immer die gesamte Instanzgröße ist erforderlich zu rundende bis zu einem `DWORD`.  
  
 **Führen Sie ✓** benennen Flags-Enumerationen mit Nomen im plural oder Substantivausdrücke und einfache Enumerationen mit Nomen im singular oder nominale Ausdrücke.  
  
 **X nicht** erweitern <xref:System.Enum?displayProperty=nameWithType> direkt.  
  
 <xref:System.Enum?displayProperty=nameWithType> eine besondere Art ist von der CLR zum Erstellen von benutzerdefinierten Enumerationen verwendet werden. Die meisten Programmiersprachen bieten ein Programmierelement, das Ihnen den Zugriff auf diese Funktionalität bietet. Beispielsweise ist in c# die `enum` Schlüsselwort wird verwendet, um eine Enumeration zu definieren.  
  
<a name="design"></a>   
### <a name="designing-flag-enums"></a>Entwerfen von Flags-Enumerationen  
 **Führen Sie ✓** gelten die <xref:System.FlagsAttribute?displayProperty=nameWithType> Flags-Enumerationen. Dieses Attribut nicht auf einfache Enumerationen anwenden.  
  
 **Führen Sie ✓** Potenzen von 2 für die Kennzeichnung Enum-Werte verwenden, damit diese problemlos kombiniert werden, können mit dem bitweisen OR-Operation.  
  
 **✓ GGF.** Kombinationen der Flags verwendet spezielle Enumerationswerte für häufig bereitstellen.  
  
 Bitweise Operationen sollte sind ein Konzept, das erweitert und nicht für einfache Aufgaben erforderlich. <xref:System.IO.FileAccess.ReadWrite> ist ein Beispiel eines speziellen Werts.  
  
 **X vermeiden** Erstellen von Flags-Enumerationen, in denen bestimmte Kombinationen von Werten ungültig sind.  
  
 **X vermeiden** mit Flagwerten Enum 0 (null), wenn der Wert "deaktiviert sind alle Flags" darstellt und Sie heißt entsprechend, wie der nächsten Richtlinie vorgesehen.  
  
 **Führen Sie ✓** benennen Sie den Wert 0 (null) von Flags-Enumerationen `None`. Für eine Flags-Enumeration muss der Wert immer bedeuten, dass "alle Flags gelöscht werden."  
  
<a name="add_value"></a>   
### <a name="adding-value-to-enums"></a>Enumerationen Wert hinzugefügt  
 Es ist üblich, um zu ermitteln, müssen Sie Werte einer Enumeration hinzufügen, nachdem Sie bereits versendet habe. Ein potenzieller Anwendung Kompatibilitätsproblem vorliegt, wenn der neu hinzugefügte Wert aus einer vorhandenen API zurückgegeben wird da schlecht geschriebene Anwendungen den neuen Wert nicht ordnungsgemäß verarbeiten können.  
  
 **✓ GGF.** Enumerationen, die trotz eines geringen Kompatibilitätsproblems Werte hinzugefügt.  
  
 Wenn Sie sich um echte Daten zur Anwendungsinkompatibilitäten durch Hinzufügen einer Enumeration verursacht haben, erwägen Sie eine neue API, die den alten und neuen Werte zurückgibt, und als veraltet markiert die alten API, die fortgesetzt werden nur die alten Werte zurückgeben soll. Dadurch wird sichergestellt, dass Ihre vorhandenen Anwendungen kompatibel bleiben.  
  
 *Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*  
  
## <a name="see-also"></a>Siehe auch  
 [Richtlinien für den Entwurf von Typen](../../../docs/standard/design-guidelines/type.md)  
 [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
