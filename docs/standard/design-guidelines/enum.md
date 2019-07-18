---
title: Enum-Entwurf
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, enumerations
- simple enumerations
- enumerations [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], enumerations
- flags enumerations
ms.assetid: dd53c952-9d9a-4736-86ff-9540e815d545
author: KrzysztofCwalina
ms.openlocfilehash: e890ebbbeb04ca424b84c11791e5ce7fa55db72e
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2019
ms.locfileid: "67663477"
---
# <a name="enum-design"></a>Enum-Entwurf

Enumerationen sind eine besondere Art von Werttyp. Es gibt zwei Arten von Enumerationen: Einfache Enumerationen und Flags-Enumerationen.

Einfache Enumerationen stellen kleine geschlossene Sätze von Optionen dar. Ein allgemeines Beispiel für die einfache Enumeration ist ein Satz von Farben.

Flags-Enumerationen dienen zur Unterstützung von bitweiser Operations für Enum-Werte. Ein allgemeines Beispiel für die Bitflags-Enum ist eine Liste von Optionen an.

**✓ DO** mit, dass eine Enumeration typisieren Parameter, Eigenschaften und Rückgabewerte, die Sätze von Werten darstellen.

**✓ DO** statische Konstanten anstelle einer Enumeration begünstigen.

**X DO NOT** Enum für offene Gruppen (z. B. die Version des Betriebssystems, Namen von Ihrer Freunde usw.) verwenden.

**X DO NOT** Geben Sie für die zukünftige Verwendung reservierte Enumerationswerte, die vorgesehen sind.

Sie können Werte immer der vorhandenen-Enumeration zu einem späteren Zeitpunkt hinzufügen. Finden Sie unter [hinzufügen Werte zu Enumerationen](#add_value) ausführliche Informationen zum Hinzufügen von Werten für Enumerationen. Reservierten Werte einfach, verunreinigen den Satz von tatsächlichen Werten und tendenziell zu Benutzerfehlern führen.

**X AVOID** öffentlich verfügbar machen Enumerationen mit nur einem Wert.

Üblicherweise zum Sicherstellen der zukünftige Erweiterbarkeit von C-APIs wird, um Methodensignaturen reservierte Parameter hinzuzufügen. Diese reservierte Parameter können als Enumerationen mit einem einzigen Standardwert ausgedrückt werden. Dies sollte nicht in der verwalteten APIs ausgeführt werden. Überladen von Methoden ermöglicht das Hinzufügen von Parametern in zukünftigen Versionen.

**X DO NOT** Sentinel Werte in Enumerationen enthalten.

Obwohl sie manchmal hilfreich, Framework-Entwickler sind, sind die Werte der Sentinel für Benutzer von Framework verwirrend. Sie werden zum Nachverfolgen des Zustands anstelle von wird einer der Werte der Enumeration aus der Gruppe, die durch die Enumeration dargestellt wird.

**✓ DO** Geben Sie einen Wert von 0 zu einfachen Enumerationen.

Rufen Sie den Wert beispielsweise "None". Wenn solche Werte nicht für diese bestimmte Enumeration geeignet ist, sollte der am häufigsten verwendete Standardwert für die Enumeration den zugrunde liegenden Wert von 0 (null) zugewiesen werden.

**✓ CONSIDER** mit <xref:System.Int32> (die Standardeinstellung in den meisten Programmiersprachen) als zugrunde liegende Typ einer Enumeration, wenn eine der folgenden Aussagen zutrifft:

- Die Enumeration ist eine Flags-Enumeration, und Sie haben mehr als 32-Flags oder erwarten, dass zukünftig mehr.

- Der zugrunde liegende Typ muss anders als <xref:System.Int32> für Interoperabilität mit nicht verwaltetem Code erwartet andere Größe Enumerationen erleichtern.

- Ein kleinerer zugrunde liegender Typ führt zu beträchtlichen einsparungen beim Speicherplatz. Wenn Sie erwarten, die Enumeration dass, die hauptsächlich als Argument für die ablaufsteuerung verwendet werden, ist die Größe kaum einen Unterschied. Die einsparungen können erheblich sein wenn:

  - Sie erwarten, dass die Enumeration als ein Feld in einer sehr häufig instanziierten Struktur oder Klasse verwendet werden soll.

  - Sie erwarten, dass Benutzer große Arrays oder Auflistungen der Enum-Instanzen erstellen.

  - Sie erwarten, dass eine große Anzahl von Instanzen der Enumeration serialisiert werden soll.

Für die speicherauslastung, denken Sie daran, dass verwaltete Objekte immer `DWORD`-ausgerichtet, weshalb Sie effektiv mehrere Enumerationen oder andere kleineren Strukturen in einer Instanz mit eine kleineren Enumeration zu platzieren, um einen Unterschied machen, da die Größe der gesamten Instanz immer jetzt bis zu rundende eine `DWORD`.

**✓ DO** benennen Flags-Enumerationen mit Nomen im plural oder Substantivausdrücke und einfache Enumerationen mit Nomen im singular oder nominale Ausdrücke.

**X DO NOT** erweitern <xref:System.Enum?displayProperty=nameWithType> direkt.

<xref:System.Enum?displayProperty=nameWithType> ein spezieller Typ wird von der CLR zum Erstellen von benutzerdefinierten Enumerationen verwendet werden. Die meisten Programmiersprachen bieten ein Programmierelement, das Zugriff auf diese Funktionalität bietet. Z. B. in c# die `enum` Schlüsselwort wird verwendet, um eine Enumeration zu definieren.

<a name="design"></a>

### <a name="designing-flag-enums"></a>Entwerfen von Flags-Enumerationen

**✓ DO** gelten die <xref:System.FlagsAttribute?displayProperty=nameWithType> Flags-Enumerationen. Dieses Attribut nicht auf einfache Enumerationen anwenden.

**✓ DO** Potenzen von 2 für die Kennzeichnung Enum-Werte verwenden, damit diese problemlos kombiniert werden, können mit dem bitweisen OR-Operation.

**✓ CONSIDER** Kombinationen der Flags verwendet spezielle Enumerationswerte für häufig bereitstellen.

Bitweise Operationen sind ein Konzept, das erweiterte und sollte nicht für einfache Aufgaben erforderlich sein. <xref:System.IO.FileAccess.ReadWrite> ist ein Beispiel für solche ein spezieller Wert.

**X AVOID** Erstellen von Flags-Enumerationen, in denen bestimmte Kombinationen von Werten ungültig sind.

**X AVOID** mit Flagwerten Enum 0 (null), wenn der Wert "deaktiviert sind alle Flags" darstellt und Sie heißt entsprechend, wie der nächsten Richtlinie vorgesehen.

**✓ DO** benennen Sie den Wert 0 (null) von Flags-Enumerationen `None`. Für eine Flags-Enumeration muss der Wert immer bedeutet, dass "alle Flags deaktiviert werden."

<a name="add_value"></a>

### <a name="adding-value-to-enums"></a>Enumerationen Wert hinzufügen

Es ist üblich, feststellen, dass Sie eine Enumeration Werte hinzufügen, nachdem Sie bereits geliefert haben möchten. Es liegt einer potenziellen Problems "Anwendungskompatibilität" bei der neu hinzugefügte Wert, über eine vorhandene API zurückgegeben wird, schlecht geschriebene Anwendungen den neuen Wert nicht ordnungsgemäß verarbeiten können.

**✓ CONSIDER** Enumerationen, die trotz eines geringen Kompatibilitätsproblems Werte hinzugefügt.

Wenn Sie echte Daten über Anwendungsinkompatibilitäten durch Hinzufügungen zu einer Enumeration verursacht haben, erwägen Sie eine neue API, die die alten und neuen Werte zurückgibt, und Beenden der alten API, die fortgesetzt werden nur die alten Werte zurückgeben soll. Dadurch wird sichergestellt, dass Ihre vorhandenen Anwendungen kompatibel bleiben.

*Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

*Pearson Education, Inc. über Rechte vorbehalten [Framework-Entwurfsrichtlinien vorgestellt: Aufrufkonventionen, Ausdrücke und Muster für die Wiederverwendbare Bibliotheken für .NET, 2. Auflage](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams, 22. Oktober 2008 von Addison-Wesley Professional als Teil der Microsoft Windows Development-Reihe veröffentlicht.*

## <a name="see-also"></a>Siehe auch

- [Richtlinien für den Entwurf von Typen](../../../docs/standard/design-guidelines/type.md)
- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
