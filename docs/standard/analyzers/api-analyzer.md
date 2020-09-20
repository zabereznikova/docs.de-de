---
title: .NET API-Analysetool
description: Erfahren Sie, wie Sie mit dem .NET API-Analysetool veraltete APIs und Kompatibilitätsprobleme bei Plattformen erkennen können.
author: oliag
ms.date: 02/20/2020
ms.technology: dotnet-standard
ms.openlocfilehash: 8da4b2add206daa431124a7d24efc2676cbcaa69
ms.sourcegitcommit: 43d5aca3fda42bad8843f6c4e72f6bd52daa55f1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2020
ms.locfileid: "89598094"
---
# <a name="net-api-analyzer"></a>.NET API-Analysetool

Das .NET API-Analysetool ist ein Roslyn-Analysetool, das potenzielle Kompatibilitätsrisiken für C#-APIs auf verschiedenen Plattformen erkennt und Aufrufe zu veralteten APIs ermittelt. Für alle C#-Entwickler kann dieses Tool in jeder Entwicklungsphase nützlich sein.

Das API-Analysetool ist als NuGet-Paket [Microsoft.DotNet.Analyzers.Compatibility](https://www.nuget.org/packages/Microsoft.DotNet.Analyzers.Compatibility/) verfügbar. Nachdem Sie es in einem Projekt referenziert haben, überwacht es automatisch den Code und zeigt Probleme bei der API-Nutzung auf. Zudem erhalten Sie Vorschläge zu möglichen Fehlerbehebungen, wenn Sie auf die Glühbirne klicken. Die Warnungen lassen sich jedoch auch über eine Option im Dropdownmenü deaktivieren.

> [!NOTE]
> Beim .NET API-Analysetool handelt es sich um eine Vorabversion.

## <a name="prerequisites"></a>Voraussetzungen

- Visual Studio 2017 und höhere Versionen oder Visual Studio für Mac (alle Versionen).

## <a name="discover-deprecated-apis"></a>Ermitteln veralteter APIs

### <a name="what-are-deprecated-apis"></a>Was sind veraltete APIs?

Die .NET-Familie besteht aus einer Reihe großer Produkte, die ständig aktualisiert werden, um den Kundenbedürfnissen besser gerecht zu werden. Es ist dabei üblich, einige APIs als veraltet zu kennzeichnen und durch neue zu ersetzen. Eine API gilt als veraltet, sobald es eine bessere Alternative gibt. Eine Möglichkeit, darüber zu informieren, dass eine API veraltet ist und nicht mehr verwendet werden sollte, ist die Kennzeichnung der API mit dem Attribut <xref:System.ObsoleteAttribute>. Der Nachteil dieses Ansatzes ist, dass es nur eine Diagnose-ID für alle veralteten APIs gibt (für C#, [CS0612](../../csharp/misc/cs0612.md)). Dies bedeutet Folgendes:

- Es ist unmöglich, über dedizierte Dokumente für jeden Fall zu verfügen.
- Eine bestimmte Kategorie von Warnungen kann nicht unterdrückt werden. Sie können entweder alle oder keine unterdrücken.
- Damit Benutzer darüber informiert werden, dass eine API veraltet ist, muss eine referenzierte Assembly oder ein Zielpaket aktualisiert werden.

Das API-Analysetool verwendet API-spezifische Fehlercodes, die mit DE beginnen (welches für „Deprecation Error“ steht), über die die Anzeige einzelner Warnungen gesteuert werden können. Die veralteten APIs, die vom Analysetool identifiziert werden, sind im Repository [Dotnet/Platform-Compat](https://github.com/dotnet/platform-compat) definiert.

### <a name="add-the-api-analyzer-to-your-project"></a>Hinzufügen des API-Analysetools zu Ihrem Projekt

1. Öffnen Sie Visual Studio.
2. Öffnen Sie das Projekt, für das Sie das Analysetool ausführen möchten.
3. Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf Ihr Projekt, und wählen Sie **NuGet-Pakete verwalten** aus. (Diese Option ist auch im Menü **Projekt** verfügbar.)
4. Auf der Registerkarte NuGet-Paket-Manager:
   1. Wählen Sie als Paketquelle „nuget.org“ aus.
   2. Wechseln Sie zur Registerkarte **Durchsuchen**.
   3. Wählen Sie **Vorabversion einbeziehen** aus.
   4. Suchen Sie nach **Microsoft.DotNet.Analyzers.Compatibility**.
   5. Wählen Sie das Paket in der Liste aus.
   6. Wählen Sie die Schaltfläche **Installieren** aus.
   7. Wählen Sie die Schaltfläche **OK** im Dialogfeld **Vorschau der Änderungen** und dann die Schaltfläche **Ich stimme zu** im Dialogfeld **Zustimmung zur Lizenz** aus, wenn Sie den Lizenzbedingungen für die aufgelisteten Pakete zustimmen.

### <a name="use-the-api-analyzer"></a>Verwenden des API-Analysetools

Wenn eine veraltete API, z.B. <xref:System.Net.WebClient>, in einem Code verwendet wird, hebt das API-Analysetool diese durch eine grüne Wellenlinie hervor. Wenn Sie mit der Maus auf den API-Aufruf zeigen, wird eine Glühbirne mit Informationen über die veraltete API angezeigt, wie in folgendem Beispiel zu sehen:

![Screenshot der WebClient-API mit grüner Wellenlinie und Glühbirne auf der linken Seite](media/api-analyzer/green-squiggle.jpg)

Das Fenster **Fehlerliste** enthält Warnungen mit einer eindeutigen ID pro veralteter API, wie in folgendem Beispiel (`DE004`) gezeigt:

![Screenshot des Fensters mit der Fehlerliste, die die ID und Beschreibung von Warnungen zeigt](media/api-analyzer/warnings-id-and-descriptions.jpg "Fenster mit Fehlerliste, die Warnungen enthält")

Wenn Sie auf die ID klicken, gelangen Sie auf eine Webseite mit detaillierten Informationen darüber, warum die API veraltet ist, und mit Vorschlägen zu alternativen APIs, die verwendet werden können.

Sie können Warnungen unterdrücken, indem Sie mit der rechten Maustaste auf das markierte Element und dann mit der linken Maustaste auf **\<diagnostic ID> unterdrücken** klicken. Es gibt zwei Möglichkeiten, Warnungen zu unterdrücken:

- [lokal (in der Quelle)](#suppress-warnings-locally)
- [global (in einer Unterdrückungsdatei)](#suppress-warnings-globally) – empfohlen

### <a name="suppress-warnings-locally"></a>Lokales Unterdrücken von Warnungen

Wenn Sie Warnungen lokal unterdrücken möchten, klicken Sie mit der rechten Maustaste auf das Element, für das Sie Warnungen unterdrücken möchten, und klicken Sie dann auf **Schnellaktionen und Refactorings** > ***Diagnose-ID*\<diagnostic ID> unterdrücken** > **In Quelle**. Die Warnungspräprozessoranweisung [#pragma](../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md) wird Ihrem Quellcode im definierten Bereich hinzugefügt: ![Screenshot von Code, eingeschlossen in #pragma warning disable](media/api-analyzer/suppress-in-source.jpg)

### <a name="suppress-warnings-globally"></a>Globales Unterdrücken von Warnungen

Wenn Sie Warnungen global unterdrücken möchten, klicken Sie mit der rechten Maustaste auf das Element, für das Sie Warnungen unterdrücken möchten, und klicken Sie dann auf **Schnellaktionen und Refactorings** > ***Diagnose-ID*\<diagnostic ID> unterdrücken** > **In Unterdrückungsdatei**.

![Screenshot des Kontextmenüs mit Optionen zum Unterdrücken einer Warnung in Visual Studio](media/api-analyzer/suppress-in-sup-file.jpg)

Die Datei *GlobalSuppressions.cs* wird nach der ersten Unterdrückung zu Ihrem Projekt hinzugefügt. Neue globale Unterdrückungen werden an diese Datei angefügt.

![Screenshot der Datei GlobalSuppressions.cs im Projektmappen-Explorer](media/api-analyzer/suppression-file.jpg)

Eine globale Unterdrückung ist die empfohlene Methode, um projektübergreifende Konsistenz bei der Verwendung von APIs sicherzustellen.

## <a name="discover-cross-platform-issues"></a>Ermitteln plattformübergeifender Probleme

Ähnlich wie bei den veralteten APIs identifiziert das Analysetool alle APIs, die nicht plattformübergeifend sind. Beispielsweise funktioniert <xref:System.Console.WindowWidth?displayProperty=nameWithType> unter Windows, jedoch nicht unter Linux oder macOS. Die Diagnose-ID wird im Fenster **Fehlerliste** angezeigt. Sie können die Warnung unterdrücken, indem Sie mit der rechten Maustaste darauf klicken und **Schnellaktionen und Refactorings** wählen. Dabei verhält es sich anders als in Fällen veralteter APIs, bei denen Sie zwei Möglichkeiten haben (entweder das veraltete Element weiterhin zu verwenden und Warnungen zu unterdrücken oder es gar nicht zu verwenden). Hier können Sie, wenn Sie Ihren Code nur für bestimmte Plattformen entwickeln, alle Warnungen für alle anderen Plattformen unterdrücken, auf denen Ihr Code später nicht ausgeführt werden soll. Dazu müssen Sie nur Ihre Projektdatei bearbeiten und die Eigenschaft `PlatformCompatIgnore` hinzufügen, die alle zu ignorierenden Plattformen auflistet. Folgende Werte werden akzeptiert: `Linux`, `macOS` und `Windows`.

```xml
<PropertyGroup>
    <PlatformCompatIgnore>Linux;macOS</PlatformCompatIgnore>
</PropertyGroup>
```

Wenn Ihr Code auf mehrere Plattformen abzielt und Sie die Vorteile einer API nutzen möchten, die auf einigen Plattformen nicht unterstützt wird, können Sie diesen Teil des Codes mit einer `if`-Anweisung schützen:

```csharp
if (RuntimeInformation.IsOSPlatform(OSPlatform.Windows))
{
     var w = Console.WindowWidth;
     // More code
}
```

Sie können auch bedingt pro Zielframework/-betriebssystem kompilieren, dies ist jedoch derzeit nur [manuell](../frameworks.md#how-to-specify-a-target-framework) möglich.

## <a name="supported-diagnostics"></a>Unterstützte Diagnosen

Zurzeit verarbeitet das Analysetool die folgenden Fälle:

- Nutzung einer .NET Standard-API, die die Ausnahme <xref:System.PlatformNotSupportedException> (PC001) auslöst.
- Nutzung einer .NET Standard-API, die im .NET Framework 4.6.1 (PC002) nicht verfügbar ist.
- Nutzung einer in der UWP nicht vorhandenen nativen API (PC003)
- Die Verwendung von Delegate.BeginInvoke und EndInvoke-APIs (PC004).
- Nutzung einer API, die als veraltet (DEXXXX) gekennzeichnet ist.

## <a name="ci-machine"></a>CI-Computer

All diese Diagnosen stehen nicht nur in der IDE zur Verfügung, sondern auch über die Befehlszeile beim Erstellen Ihres Projekts, das den CI-Server umfasst.

## <a name="configuration"></a>Konfiguration

Der Benutzer entscheidet, wie die Diagnose behandelt werden soll: als Warnungen, Fehler oder Vorschläge. Alternativ kann er sie auch deaktivieren. Beispielsweise können Sie als Architekt entscheiden, dass Kompatibilitätsprobleme als Fehler behandelt werden sollen, während Aufrufe einiger veralteter APIs Warnungen und andere Probleme nur Vorschläge generieren. Diese Einstellungen können Sie getrennt nach Diagnose-ID und Projekt konfigurieren. Navigieren Sie hierzu im **Projektmappen-Explorer** unter Ihrem Projekt zum Knoten **Abhängigkeiten**. Erweitern Sie die Knoten **Abhängigkeiten** > **Analysetools** > **Microsoft.DotNet.Analyzers.Compatibility**. Klicken Sie mit der rechten Maustaste auf die Diagnose-ID, wählen Sie **Schweregrad für Regelsatz festlegen**, und wählen Sie die gewünschte Option aus.

![Screenshot Projektmappen-Explorer mit Diagnosen und Popupdialogfeld mit Regelsatz-Schweregrad](media/api-analyzer/disable-notifications.jpg)

## <a name="see-also"></a>Weitere Informationen

- Blogbeitrag [Introducing API Analyzer](https://devblogs.microsoft.com/dotnet/introducing-api-analyzer/) (Einführung in das API-Analysetool).
- Demovideo [API Analyzer](https://youtu.be/eeBEahYXGd0) (API-Analysetool) auf YouTube
