---
title: 'Breaking Change: Das Paket Microsoft.DotNet.PlatformAbstractions wurde entfernt'
description: Hier erfahren Sie mehr über den Breaking Change an den .NET-Kernbibliotheken in .NET 5.0, bei dem das Paket „Microsoft.DotNet.PlatformAbstractions“ entfernt wurde.
ms.date: 11/01/2020
ms.openlocfilehash: 38ffe5e592d01c3bae14fc41becb594283b975a3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759468"
---
# <a name="microsoftdotnetplatformabstractions-package-removed"></a>Das Paket Microsoft.DotNet.PlatformAbstractions wurde entfernt

Es werden keine neuen Versionen des [Microsoft.DotNet.PlatformAbstractions-Pakets](https://www.nuget.org/packages/Microsoft.DotNet.PlatformAbstractions/) erzeugt.

## <a name="change-description"></a>Änderungsbeschreibung

Zuvor wurden neue Versionen der <xref:Microsoft.DotNet.PlatformAbstractions?displayProperty=fullName>-Bibliothek zusammen mit neuen Versionen von .NET Core erstellt. In Zukunft werden der Bibliothek keine neuen Funktionen hinzugefügt, und es werden keine neuen Hauptversionen mehr veröffentlicht. Vorhandene Versionen der Bibliothek funktionieren jedoch weiterhin und werden gewartet.

Die <xref:Microsoft.DotNet.PlatformAbstractions?displayProperty=fullName>-Bibliothek überschneidet sich mit APIs, die bereits in den System.\*-APIs eingerichtet sind. Außerdem werden einige <xref:Microsoft.DotNet.PlatformAbstractions>-APIs nicht mit dem gleichen Maß an Genauigkeit und langfristiger Unterstützbarkeit wie der Rest des Systems\* entworfen. APIs. <xref:Microsoft.DotNet.PlatformAbstractions> verwendet beispielsweise die `Platform`-Enumeration, um die aktuelle Betriebssystemplattform zu beschreiben. Dieser Enumerationsentwurf wurde explizit abgelehnt, als die <xref:System.Runtime.InteropServices.RuntimeInformation.IsOSPlatform(System.Runtime.InteropServices.OSPlatform)?displayProperty=nameWithType>-API entworfen wurde, um neue Plattformen und zukünftige Flexibilität zu ermöglichen.

Die von der <xref:Microsoft.DotNet.PlatformAbstractions?displayProperty=fullName>-Bibliothek aktivierten Szenarios sind jetzt ohne sie möglich. Vorhandene Versionen funktionieren weiterhin, auch in .NET 5.0 und später, und werden zusammen mit früheren Versionen von .NET Core gewartet. Der Bibliothek werden jedoch keine neuen Funktionen hinzugefügt. Stattdessen werden anderen Bibliotheken und APIs neue Funktionen hinzugefügt.

## <a name="version-introduced"></a>Eingeführt in Version

5.0

## <a name="recommended-action"></a>Empfohlene Maßnahme

- Sie können weiterhin ältere Versionen der Bibliothek verwenden, wenn diese Ihre Anforderungen erfüllen.

- Wenn die älteren Versionen Ihre Anforderungen nicht erfüllen, ersetzen Sie die Verwendung der `PlatformAbstractions`-APIs durch die empfohlenen Ersetzungen.

  | `PlatformAbstractions`-API | Empfohlener Ersatz |
  |-|-|
  | `ApplicationEnvironment.ApplicationBasePath` | <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType> |
  | <xref:Microsoft.DotNet.PlatformAbstractions.HashCodeCombiner> | <xref:System.HashCode?displayProperty=nameWithType> |
  | `RuntimeEnvironment.GetRuntimeIdentifier()` | <xref:System.Runtime.InteropServices.RuntimeInformation.RuntimeIdentifier?displayProperty=nameWithType> |
  | `RuntimeEnvironment.OperatingSystemPlatform` | <xref:System.Runtime.InteropServices.RuntimeInformation.IsOSPlatform(System.Runtime.InteropServices.OSPlatform)?displayProperty=nameWithType> |
  | `RuntimeEnvironment.RuntimeArchitecture` | <xref:System.Runtime.InteropServices.RuntimeInformation.ProcessArchitecture?displayProperty=nameWithType> |
  | `RuntimeEnvironment.OperatingSystem` | <xref:System.Runtime.InteropServices.RuntimeInformation.OSDescription?displayProperty=nameWithType> |
  | `RuntimeEnvironment.OperatingSystemVersion` | <xref:System.Runtime.InteropServices.RuntimeInformation.OSDescription?displayProperty=nameWithType> und <xref:System.Environment.OSVersion?displayProperty=nameWithType> |

  > [!NOTE]
  > Die meisten Anwendungsfälle für `RuntimeEnvironment.OperatingSystem` und `RuntimeEnvironment.OperatingSystemVersion` dienen zu Anzeigezwecken, zum Beispiel die Anzeige eines Benutzers, der Protokollierung und der Telemetrie. Es wird nicht empfohlen, Entscheidungen zur Runtime basierend auf der Betriebssystemversion zu treffen. <xref:System.Environment.OSVersion?displayProperty=nameWithType> gibt nun die [korrekte Version](environment-osversion-returns-correct-version.md) für die Betriebssysteme Windows und macOS zurück. Für die meisten Unix-Distributionen ist das, was man als „Betriebssystemversion“ bezeichnet, nicht ganz so einfach. Es kann beispielsweise hier die Linux-Kernelversion sein oder die Distributionsversion. Bei den meisten Unix-Plattformen geben <xref:System.Environment.OSVersion?displayProperty=nameWithType> und <xref:System.Runtime.InteropServices.RuntimeInformation.OSDescription?displayProperty=nameWithType> die Version zurück, die von `uname` zurückgegeben wird. Der empfohlene Ansatz zum Abrufen des Linux-Distributionsnamens und der Version ist es, die Datei */etc/os-release* zu lesen.

## <a name="affected-apis"></a>Betroffene APIs

- `Microsoft.DotNet.PlatformAbstractions.ApplicationEnvironment.ApplicationBasePath`
- <xref:Microsoft.DotNet.PlatformAbstractions.HashCodeCombiner?displayProperty=fullName>
- `Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.GetRuntimeIdentifier()`
- `Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystem`
- `Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystemPlatform`
- `Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystemVersion`
- `Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.RuntimeArchitecture`

<!--

### Category

Core .NET libraries

### Affected APIs

- `P:Microsoft.DotNet.PlatformAbstractions.ApplicationEnvironment.ApplicationBasePath`
- `T:Microsoft.DotNet.PlatformAbstractions.HashCodeCombiner`
- `M:Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.GetRuntimeIdentifier`
- `P:Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystem`
- `P:Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystemPlatform`
- `P:Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystemVersion`
- `P:Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.RuntimeArchitecture`

-->
