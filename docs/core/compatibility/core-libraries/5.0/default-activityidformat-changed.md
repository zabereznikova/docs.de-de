---
title: 'Breaking Change: Das ActivityIdFormat-Standardformat ist W3C'
description: Hier erfahren Sie mehr über den Breaking Change an den .NET-Kernbibliotheken in .NET 5.0, durch den ActivityIdFormat nun standardmäßig W3C lautet.
ms.date: 11/01/2020
ms.openlocfilehash: 77ee705ac18065c84ddeab3127e01b6a40c3b84d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759486"
---
# <a name="default-activityidformat-is-w3c"></a>Das ActivityIdFormat-Standardformat ist W3C

Das Standardformat für Activity-IDs (<xref:System.Diagnostics.Activity.DefaultIdFormat?displayProperty=nameWithType>) ist ab sofort <xref:System.Diagnostics.ActivityIdFormat.W3C?displayProperty=nameWithType>.

## <a name="change-description"></a>Änderungsbeschreibung

Das W3C-Activity-ID-Format wurde in .NET Core 3.0 als Alternative zum hierarchischen ID-Format eingeführt. Aus Kompatibilitätsgründen wurde das W3C-Format jedoch erst in .NET 5.0 zum Standardformat gemacht. Das Standardformat wurde in .NET 5.0 geändert, da das [W3C-Format ratifiziert](https://www.w3.org/TR/trace-context/) und in immer mehr Sprachimplementierungen verwendet wurde.

Wenn Ihre App als Ziel eine andere Plattform als .NET 5.0 oder höhere Versionen verwendet, gilt das alte Verhalten. Das Standardformat wäre dann also <xref:System.Diagnostics.ActivityIdFormat.Hierarchical>. Dieser Standard gilt für die Plattformen net45 und höher, netstandard1.1 und höher und netcoreapp (1.x, 2.x und 3.x). Ab .NET 5.0 wird <xref:System.Diagnostics.Activity.DefaultIdFormat?displayProperty=nameWithType> auf <xref:System.Diagnostics.ActivityIdFormat.W3C?displayProperty=nameWithType> festgelegt.

## <a name="version-introduced"></a>Eingeführt in Version

5.0

## <a name="recommended-action"></a>Empfohlene Maßnahme

Wenn die Anwendung nicht vom Bezeichner abhängig ist, der für die verteilte Ablaufverfolgung verwendet wird, ist keine Aktion erforderlich. Bibliotheken wie ASP.NET Core und <xref:System.Net.Http.HttpClient> können beide Versionen von <xref:System.Diagnostics.ActivityIdFormat> verwenden oder verteilen.

Wenn eine Interoperabilität mit vorhandenen Systemen erforderlich ist oder aktuelle Systeme auf dem Format des Bezeichners basieren, können Sie das alte Verhalten beibehalten, indem Sie <xref:System.Diagnostics.Activity.DefaultIdFormat> auf <xref:System.Diagnostics.ActivityIdFormat.Hierarchical?displayProperty=nameWithType> festlegen. Alternativ können Sie einen Wechsel von AppContext auf drei Weisen umsetzen:

- In der Projektdatei.

  ```xml
  <ItemGroup>
    <RuntimeHostConfigurationOption Include="System.Diagnostics.DefaultActivityIdFormatIsHierarchial" Value="true" />
  </ItemGroup>
  ```

- In der *runtimeconfig.json*-Datei.

  ```json
  {
      "runtimeOptions": {
          "configProperties": {
              "System.Diagnostics.DefaultActivityIdFormatIsHierarchial": true
          }
      }
  }
  ```

- Über eine Umgebungsvariable.

  `DOTNET_SYSTEM_DIAGNOSTICS_DEFAULTACTIVITYIDFORMATISHIERARCHIAL` wird auf `true` oder 1 festgelegt.

## <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Diagnostics.Activity.DefaultIdFormat?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `P:System.Diagnostics.Activity.DefaultIdFormat`

-->
