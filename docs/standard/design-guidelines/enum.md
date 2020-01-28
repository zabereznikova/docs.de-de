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
ms.openlocfilehash: 3b24bfefd3edb0585e9c6369e9b8151b17151661
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741715"
---
# <a name="enum-design"></a>Enum-Entwurf

Enumerationswerte sind eine besondere Art von Werttyp. Es gibt zwei Arten von Aufständen: einfache Aufteilungs-und flagumerationszeichen.

Einfache Aufstellungen stellen kleine geschlossene Sätze von Auswahlmöglichkeiten dar. Ein gängiges Beispiel für die einfache-Enumeration ist ein Satz von Farben.

Flag-Enumerationen sind so konzipiert, dass bitweise Vorgänge für die Enumerationswerte unterstützt werden. Ein gängiges Beispiel für die Flags-Enumeration ist eine Liste von Optionen.

✔️ eine Enumeration verwenden, um Parameter, Eigenschaften und Rückgabewerte, die Sätze von Werten darstellen, stark einzugeben.

✔️ bevorzugen die Verwendung einer Enumeration anstelle von statischen Konstanten.

❌ keine Enumeration für geöffnete Sätze verwenden (z. b. die Betriebssystemversion, die Namen Ihrer Freunde usw.).

❌ keine reservierten Enumerationswerte bereit, die für die zukünftige Verwendung vorgesehen sind.

Sie können der vorhandenen Enumeration jederzeit einfach Werte hinzufügen. Weitere Informationen zum Hinzufügen von Werten zu enumeraten finden [Sie unter Hinzufügen von Werten zu](#add_value) Enumerationswerten Reservierte Werte verschmutzen lediglich den Satz realer Werte und führen tendenziell zu Benutzerfehlern.

❌ vermeiden, dass Enumerationswerte nur mit einem Wert öffentlich verfügbar gemacht werden

Eine gängige Vorgehensweise, um die zukünftige Erweiterbarkeit von C-APIs sicherzustellen, besteht darin, den Methoden Signaturen reservierte Parameter hinzuzufügen. Solche reservierten Parameter können als Enumerationswerte mit einem einzelnen Standardwert ausgedrückt werden. Dies sollte nicht in verwalteten APIs erfolgen. Die Methoden Überladung ermöglicht das Hinzufügen von Parametern in zukünftigen Versionen.

❌ keine Sentinel-Werte in Enumerationswerte einschließen.

Obwohl Sie für Frameworkentwickler manchmal hilfreich sind, sind Sentinel-Werte für Benutzer des Frameworks verwirrend. Sie werden verwendet, um den Zustand der Enumeration zu verfolgen, anstatt einen der Werte aus dem Satz zu verwenden, der durch die Enumeration repräsentiert wird.

✔️ für einfache Enumerationswerte den Wert 0 (null) bereitstellen.

Es empfiehlt sich, den Wert in etwa "None" zu aufrufen. Wenn ein solcher Wert für diese bestimmte Enumeration nicht geeignet ist, sollte dem am häufigsten voreingestellten Standardwert für die Enumeration der zugrunde liegende Wert 0 (null) zugewiesen werden.

✔️ sollten Sie in Erwägung gezogen werden, in den meisten Programmiersprachen <xref:System.Int32> als zugrunde liegenden Typ einer-Aufzählung zu verwenden, es sei denn, eine der folgenden Werte ist true:

- Die Enumeration ist eine Flags-Enumeration, und Sie verfügen über mehr als 32 Flags oder erwarten, dass in der Zukunft mehr vorhanden sind.

- Der zugrunde liegende Typ muss sich von der <xref:System.Int32> unterscheiden, um die Interoperabilität mit nicht verwaltetem Code zu verbessern, der unterschiedliche enums erwartet.

- Ein kleinerer zugrunde liegender Typ führt zu erheblichen Einsparungen im Bereich. Wenn Sie davon ausgehen, dass die Aufzählung hauptsächlich als Argument für die Ablauf Steuerung verwendet werden soll, hat die Größe kaum einen Unterschied. Die Größen Einsparungen können in folgenden Größen erheblich sein:

  - Sie erwarten, dass die Enumeration als Feld in einer sehr häufig instanziierten Struktur oder Klasse verwendet wird.

  - Sie erwarten, dass Benutzer große Arrays oder Auflistungen der Enumeration-Instanzen erstellen.

  - Sie erwarten, dass eine große Anzahl von Instanzen der Enumeration serialisiert wird.

Beachten Sie bei der in-Memory-Verwendung, dass verwaltete Objekte stets `DWORD`ausgerichtet sind, sodass Sie tatsächlich mehrere Enumerationen oder andere kleine Strukturen in einer Instanz benötigen, um eine kleinere Aufzählung mit zu erstellen, um einen Unterschied zu schaffen, da die gesamte instanzgröße immer auf einen `DWORD`aufgerundet wird.

✔️ durch eine namensflag-Enumerationen mit Plural-Nomen oder nominalen Ausdrücken und einfachen Enumerationen mit Singular-Nomen oder Substantiv Ausdrücken.

❌ <xref:System.Enum?displayProperty=nameWithType> nicht direkt erweitern.

<xref:System.Enum?displayProperty=nameWithType> ist ein spezieller Typ, der von der CLR verwendet wird, um benutzerdefinierte Enumerationen zu erstellen. Die meisten Programmiersprachen bieten ein Programmier Element, das Ihnen den Zugriff auf diese Funktionalität ermöglicht. Beispielsweise wird im C# `enum`-Schlüsselwort verwendet, um eine Enumeration zu definieren.

<a name="design"></a>

### <a name="designing-flag-enums"></a>Entwerfen von Flag-Aufständen

✔️ die <xref:System.FlagsAttribute?displayProperty=nameWithType> zum Markieren von Aufständen anwenden. Wenden Sie dieses Attribut nicht auf einfache auffüge Aufgaben an.

✔️ für die Flag-Enumerationswerte zwei Möglichkeiten verwenden, damit Sie mit der bitweisen OR-Operation frei kombiniert werden können.

✔️ sollten besondere Enumerationswerte für häufig verwendete Kombinationen von Flags bereitgestellt werden.

Bitweise Vorgänge sind ein erweitertes Konzept, das für einfache Aufgaben nicht erforderlich ist. <xref:System.IO.FileAccess.ReadWrite> ist ein Beispiel für einen solchen besonderen Wert.

❌ vermeiden Sie das Erstellen von Flag-enumeraten, wenn bestimmte Kombinationen von Werten ungültig sind

❌ vermeiden Sie die Verwendung von Flag-Enumerationswerten von 0 (null), es sei denn, der Wert steht für "alle Flags sind gelöscht" und entsprechend der Bezeichnung durch die nächste Richtlinie

✔️ den Wert 0 (null) der Flag-enumerationszeichen `None`. Bei einer Flag-Enumeration muss der Wert immer lauten, dass alle Flags gelöscht werden.

<a name="add_value"></a>

### <a name="adding-value-to-enums"></a>Hinzufügen von Wert zu enumeraten

Es kommt häufig vor, dass Sie einer Enumeration Werte hinzufügen müssen, nachdem Sie Sie bereits geliefert haben. Es gibt ein potenzielles Problem mit der Anwendungs Kompatibilität, wenn der neu hinzugefügte Wert von einer vorhandenen API zurückgegeben wird, da schlecht geschriebene Anwendungen den neuen Wert möglicherweise nicht ordnungsgemäß verarbeiten.

✔️ ggf. Werte zu Enumerationswerten hinzufügen, trotz eines geringen Kompatibilitäts Risikos.

Wenn Sie über echte Daten über Anwendungs Inkompatibilitäten verfügen, die durch Ergänzungen zu einer Enumeration verursacht werden, sollten Sie eine neue API hinzufügen, die die neuen und alten Werte zurückgibt, und die alte API als veraltet kennzeichnen, sodass nur die alten Werte zurückgegeben werden sollten. Dadurch wird sichergestellt, dass Ihre vorhandenen Anwendungen kompatibel bleiben.

*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*

## <a name="see-also"></a>Siehe auch

- [Richtlinien für den Entwurf von Typen](../../../docs/standard/design-guidelines/type.md)
- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
