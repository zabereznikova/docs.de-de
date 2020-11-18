---
title: Enum-Entwurf
description: Entwurf für Enumerationswerte, die eine besondere Art von Werttyp sind. Einfache Enumerationen enthalten kleine, geschlossene Sätze von Optionen. Flag-Enumerationen unterstützen bitweise Vorgänge für Enumerationswerte.
ms.date: 10/22/2008
helpviewer_keywords:
- type design guidelines, enumerations
- simple enumerations
- enumerations [.NET Framework], design guidelines
- class library design guidelines [.NET Framework], enumerations
- flags enumerations
ms.assetid: dd53c952-9d9a-4736-86ff-9540e815d545
ms.openlocfilehash: a2e19197b114daa2a0956a6fc87231a6a81de916
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94821358"
---
# <a name="enum-design"></a>Enum-Entwurf

Enumerationswerte sind eine besondere Art von Werttyp. Es gibt zwei Arten von Aufständen: einfache Aufteilungs-und flagumerationszeichen.

Einfache Aufstellungen stellen kleine geschlossene Sätze von Auswahlmöglichkeiten dar. Ein gängiges Beispiel für die einfache-Enumeration ist ein Satz von Farben.

Flag-Enumerationen sind so konzipiert, dass bitweise Vorgänge für die Enumerationswerte unterstützt werden. Ein gängiges Beispiel für die Flags-Enumeration ist eine Liste von Optionen.

✔️ eine Enumeration verwenden, um Parameter, Eigenschaften und Rückgabewerte, die Sätze von Werten darstellen, stark einzugeben.

✔️ bevorzugen die Verwendung einer Enumeration anstelle von statischen Konstanten.

❌ Verwenden Sie keine Enumeration für geöffnete Sätze (z. b. die Betriebssystemversion, die Namen der Freunde usw.).

❌ Geben Sie keine reservierten Enumerationswerte an, die für die zukünftige Verwendung vorgesehen sind.

Sie können der vorhandenen Enumeration jederzeit einfach Werte hinzufügen. Weitere Informationen zum Hinzufügen von Werten zu enumeraten finden [Sie unter Hinzufügen von Werten zu](#add_value) Enumerationswerten Reservierte Werte verschmutzen lediglich den Satz realer Werte und führen tendenziell zu Benutzerfehlern.

❌ Vermeiden Sie die öffentliche Offenlegung von Enumerationswerten mit nur einem Wert

Eine gängige Vorgehensweise, um die zukünftige Erweiterbarkeit von C-APIs sicherzustellen, besteht darin, den Methoden Signaturen reservierte Parameter hinzuzufügen. Solche reservierten Parameter können als Enumerationswerte mit einem einzelnen Standardwert ausgedrückt werden. Dies sollte nicht in verwalteten APIs erfolgen. Die Methoden Überladung ermöglicht das Hinzufügen von Parametern in zukünftigen Versionen.

❌ Fügen Sie keine Sentinel-Werte in Enumerationswerte ein.

Obwohl Sie für Frameworkentwickler manchmal hilfreich sind, sind Sentinel-Werte für Benutzer des Frameworks verwirrend. Sie werden verwendet, um den Zustand der Enumeration zu verfolgen, anstatt einen der Werte aus dem Satz zu verwenden, der durch die Enumeration repräsentiert wird.

✔️ für einfache Enumerationswerte den Wert 0 (null) bereitstellen.

Es empfiehlt sich, den Wert in etwa "None" zu aufrufen. Wenn ein solcher Wert für diese bestimmte Enumeration nicht geeignet ist, sollte dem am häufigsten voreingestellten Standardwert für die Enumeration der zugrunde liegende Wert 0 (null) zugewiesen werden.

✔️ sollten Sie die Verwendung von <xref:System.Int32> (standardmäßig in den meisten Programmiersprachen) als zugrunde liegenden Typ einer-Aufzählung in Erwägung gezogen, es sei denn, eine der folgenden ist true

- Die Enumeration ist eine Flags-Enumeration, und Sie verfügen über mehr als 32 Flags oder erwarten, dass in der Zukunft mehr vorhanden sind.

- Der zugrunde liegende Typ muss sich von der <xref:System.Int32> einfacheren Interoperabilität mit nicht verwaltetem Code unterscheiden, der andere enums erwartet.

- Ein kleinerer zugrunde liegender Typ führt zu erheblichen Einsparungen im Bereich. Wenn Sie davon ausgehen, dass die Aufzählung hauptsächlich als Argument für die Ablauf Steuerung verwendet werden soll, hat die Größe kaum einen Unterschied. Die Größen Einsparungen können in folgenden Größen erheblich sein:

  - Sie erwarten, dass die Enumeration als Feld in einer sehr häufig instanziierten Struktur oder Klasse verwendet wird.

  - Sie erwarten, dass Benutzer große Arrays oder Auflistungen der Enumeration-Instanzen erstellen.

  - Sie erwarten, dass eine große Anzahl von Instanzen der Enumeration serialisiert wird.

Beachten Sie bei der in-Memory-Verwendung, dass verwaltete Objekte immer `DWORD` ausgerichtet sind, sodass Sie in einer Instanz tatsächlich mehrere Enumerationen oder andere kleine Strukturen benötigen, um einen Unterschied zu erstellen, da die gesamte instanzgröße immer auf einen aufgerundet wird `DWORD` .

✔️ durch eine namensflag-Enumerationen mit Plural-Nomen oder nominalen Ausdrücken und einfachen Enumerationen mit Singular-Nomen oder Substantiv Ausdrücken.

❌ Nicht direkt erweitern <xref:System.Enum?displayProperty=nameWithType> .

<xref:System.Enum?displayProperty=nameWithType> ist ein spezieller Typ, der von der CLR verwendet wird, um benutzerdefinierte Enumerationen zu erstellen. Die meisten Programmiersprachen bieten ein Programmier Element, das Ihnen den Zugriff auf diese Funktionalität ermöglicht. Beispielsweise wird in c# das- `enum` Schlüsselwort verwendet, um eine Enumeration zu definieren.

<a name="design"></a>

### <a name="designing-flag-enums"></a>Entwerfen von Flag-Aufständen

✔️ anwenden, um auf-auf-auf-auf-auf- <xref:System.FlagsAttribute?displayProperty=nameWithType> Wenden Sie dieses Attribut nicht auf einfache auffüge Aufgaben an.

✔️ für die Flag-Enumerationswerte zwei Möglichkeiten verwenden, damit Sie mit der bitweisen OR-Operation frei kombiniert werden können.

✔️ sollten besondere Enumerationswerte für häufig verwendete Kombinationen von Flags bereitgestellt werden.

Bitweise Vorgänge sind ein erweitertes Konzept, das für einfache Aufgaben nicht erforderlich ist. <xref:System.IO.FileAccess.ReadWrite> ein Beispiel für einen solchen besonderen Wert.

❌ Vermeiden Sie das Erstellen von Flag-enumeraten, wenn bestimmte Kombinationen von Werten ungültig sind

❌ Vermeiden Sie die Verwendung von Flag-Enumerationswerten von 0 (null), es sei denn, der Wert steht für "alle Flags sind gelöscht" und entsprechend der Bezeichnung durch die nächste Richtlinie

✔️ den Wert 0 (null) der Flag-Enumerationsnamen `None` . Bei einer Flag-Enumeration muss der Wert immer lauten, dass alle Flags gelöscht werden.

<a name="add_value"></a>

### <a name="adding-value-to-enums"></a>Hinzufügen von Wert zu enumeraten

Es kommt häufig vor, dass Sie einer Enumeration Werte hinzufügen müssen, nachdem Sie Sie bereits geliefert haben. Es gibt ein potenzielles Problem mit der Anwendungs Kompatibilität, wenn der neu hinzugefügte Wert von einer vorhandenen API zurückgegeben wird, da schlecht geschriebene Anwendungen den neuen Wert möglicherweise nicht ordnungsgemäß verarbeiten.

✔️ ggf. Werte zu Enumerationswerten hinzufügen, trotz eines geringen Kompatibilitäts Risikos.

Wenn Sie über echte Daten über Anwendungs Inkompatibilitäten verfügen, die durch Ergänzungen zu einer Enumeration verursacht werden, sollten Sie eine neue API hinzufügen, die die neuen und alten Werte zurückgibt, und die alte API als veraltet kennzeichnen, sodass nur die alten Werte zurückgegeben werden sollten. Dadurch wird sichergestellt, dass Ihre vorhandenen Anwendungen kompatibel bleiben.

*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*

## <a name="see-also"></a>Siehe auch

- [Typentwurfs Richtlinien](type.md)
- [Framework-Entwurfs Richtlinien](index.md)
