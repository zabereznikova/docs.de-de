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
ms.openlocfilehash: 130e9b4e7f8d7076d1dc3f21f51dc07a68799bbe
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709451"
---
# <a name="enum-design"></a>Enum-Entwurf

Enumerationswerte sind eine besondere Art von Werttyp. Es gibt zwei Arten von Aufständen: einfache Aufteilungs-und flagumerationszeichen.

Einfache Aufstellungen stellen kleine geschlossene Sätze von Auswahlmöglichkeiten dar. Ein gängiges Beispiel für die einfache-Enumeration ist ein Satz von Farben.

Flag-Enumerationen sind so konzipiert, dass bitweise Vorgänge für die Enumerationswerte unterstützt werden. Ein gängiges Beispiel für die Flags-Enumeration ist eine Liste von Optionen.

**✓ DO** mit, dass eine Enumeration typisieren Parameter, Eigenschaften und Rückgabewerte, die Sätze von Werten darstellen.

**✓ DO** statische Konstanten anstelle einer Enumeration begünstigen.

**X DO NOT** Enum für offene Gruppen (z. B. die Version des Betriebssystems, Namen von Ihrer Freunde usw.) verwenden.

**X DO NOT** Geben Sie für die zukünftige Verwendung reservierte Enumerationswerte, die vorgesehen sind.

Sie können der vorhandenen Enumeration jederzeit einfach Werte hinzufügen. Weitere Informationen zum Hinzufügen von Werten zu enumeraten finden [Sie unter Hinzufügen von Werten zu](#add_value) Enumerationswerten Reservierte Werte verschmutzen lediglich den Satz realer Werte und führen tendenziell zu Benutzerfehlern.

**X AVOID** öffentlich verfügbar machen Enumerationen mit nur einem Wert.

Eine gängige Vorgehensweise, um die zukünftige Erweiterbarkeit von C-APIs sicherzustellen, besteht darin, den Methoden Signaturen reservierte Parameter hinzuzufügen. Solche reservierten Parameter können als Enumerationswerte mit einem einzelnen Standardwert ausgedrückt werden. Dies sollte nicht in verwalteten APIs erfolgen. Die Methoden Überladung ermöglicht das Hinzufügen von Parametern in zukünftigen Versionen.

**X DO NOT** Sentinel Werte in Enumerationen enthalten.

Obwohl Sie für Frameworkentwickler manchmal hilfreich sind, sind Sentinel-Werte für Benutzer des Frameworks verwirrend. Sie werden verwendet, um den Zustand der Enumeration zu verfolgen, anstatt einen der Werte aus dem Satz zu verwenden, der durch die Enumeration repräsentiert wird.

**✓ DO** Geben Sie einen Wert von 0 zu einfachen Enumerationen.

Es empfiehlt sich, den Wert in etwa "None" zu aufrufen. Wenn ein solcher Wert für diese bestimmte Enumeration nicht geeignet ist, sollte dem am häufigsten voreingestellten Standardwert für die Enumeration der zugrunde liegende Wert 0 (null) zugewiesen werden.

**✓ CONSIDER** mit <xref:System.Int32> (die Standardeinstellung in den meisten Programmiersprachen) als zugrunde liegende Typ einer Enumeration, wenn eine der folgenden Aussagen zutrifft:

- Die Enumeration ist eine Flags-Enumeration, und Sie verfügen über mehr als 32 Flags oder erwarten, dass in der Zukunft mehr vorhanden sind.

- Der zugrunde liegende Typ muss sich von der <xref:System.Int32> unterscheiden, um die Interoperabilität mit nicht verwaltetem Code zu verbessern, der unterschiedliche enums erwartet.

- Ein kleinerer zugrunde liegender Typ führt zu erheblichen Einsparungen im Bereich. Wenn Sie davon ausgehen, dass die Aufzählung hauptsächlich als Argument für die Ablauf Steuerung verwendet werden soll, hat die Größe kaum einen Unterschied. Die Größen Einsparungen können in folgenden Größen erheblich sein:

  - Sie erwarten, dass die Enumeration als Feld in einer sehr häufig instanziierten Struktur oder Klasse verwendet wird.

  - Sie erwarten, dass Benutzer große Arrays oder Auflistungen der Enumeration-Instanzen erstellen.

  - Sie erwarten, dass eine große Anzahl von Instanzen der Enumeration serialisiert wird.

Beachten Sie bei der in-Memory-Verwendung, dass verwaltete Objekte stets `DWORD`ausgerichtet sind, sodass Sie tatsächlich mehrere Enumerationen oder andere kleine Strukturen in einer Instanz benötigen, um eine kleinere Aufzählung mit zu erstellen, um einen Unterschied zu schaffen, da die gesamte instanzgröße immer auf einen `DWORD`aufgerundet wird.

**✓ DO** benennen Flags-Enumerationen mit Nomen im plural oder Substantivausdrücke und einfache Enumerationen mit Nomen im singular oder nominale Ausdrücke.

**X DO NOT** erweitern <xref:System.Enum?displayProperty=nameWithType> direkt.

<xref:System.Enum?displayProperty=nameWithType> ist ein spezieller Typ, der von der CLR verwendet wird, um benutzerdefinierte Enumerationen zu erstellen. Die meisten Programmiersprachen bieten ein Programmier Element, das Ihnen den Zugriff auf diese Funktionalität ermöglicht. Beispielsweise wird im C# `enum`-Schlüsselwort verwendet, um eine Enumeration zu definieren.

<a name="design"></a>

### <a name="designing-flag-enums"></a>Entwerfen von Flag-Aufständen

**✓ DO** gelten die <xref:System.FlagsAttribute?displayProperty=nameWithType> Flags-Enumerationen. Wenden Sie dieses Attribut nicht auf einfache auffüge Aufgaben an.

**✓ DO** Potenzen von 2 für die Kennzeichnung Enum-Werte verwenden, damit diese problemlos kombiniert werden, können mit dem bitweisen OR-Operation.

**✓ CONSIDER** Kombinationen der Flags verwendet spezielle Enumerationswerte für häufig bereitstellen.

Bitweise Vorgänge sind ein erweitertes Konzept, das für einfache Aufgaben nicht erforderlich ist. <xref:System.IO.FileAccess.ReadWrite> ist ein Beispiel für einen solchen besonderen Wert.

**X AVOID** Erstellen von Flags-Enumerationen, in denen bestimmte Kombinationen von Werten ungültig sind.

**X AVOID** mit Flagwerten Enum 0 (null), wenn der Wert "deaktiviert sind alle Flags" darstellt und Sie heißt entsprechend, wie der nächsten Richtlinie vorgesehen.

**✓ DO** benennen Sie den Wert 0 (null) von Flags-Enumerationen `None`. Bei einer Flag-Enumeration muss der Wert immer lauten, dass alle Flags gelöscht werden.

<a name="add_value"></a>

### <a name="adding-value-to-enums"></a>Hinzufügen von Wert zu enumeraten

Es kommt häufig vor, dass Sie einer Enumeration Werte hinzufügen müssen, nachdem Sie Sie bereits geliefert haben. Es gibt ein potenzielles Problem mit der Anwendungs Kompatibilität, wenn der neu hinzugefügte Wert von einer vorhandenen API zurückgegeben wird, da schlecht geschriebene Anwendungen den neuen Wert möglicherweise nicht ordnungsgemäß verarbeiten.

**✓ CONSIDER** Enumerationen, die trotz eines geringen Kompatibilitätsproblems Werte hinzugefügt.

Wenn Sie über echte Daten über Anwendungs Inkompatibilitäten verfügen, die durch Ergänzungen zu einer Enumeration verursacht werden, sollten Sie eine neue API hinzufügen, die die neuen und alten Werte zurückgibt, und die alte API als veraltet kennzeichnen, sodass nur die alten Werte zurückgegeben werden sollten. Dadurch wird sichergestellt, dass Ihre vorhandenen Anwendungen kompatibel bleiben.

*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*

## <a name="see-also"></a>Siehe auch

- [Richtlinien für den Entwurf von Typen](../../../docs/standard/design-guidelines/type.md)
- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
