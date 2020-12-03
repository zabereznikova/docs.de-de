---
title: 'Breaking Change: Veraltete Eigenschaften in ConsoleLoggerOptions'
description: Hier erfahren Sie mehr über den Breaking Change an den .NET-Kernbibliotheken in .NET 5.0, durch den der Typ „ConsoleLoggerFormat“ und einige Eigenschaften von „ConsoleLoggerOptions“ nun als veraltet gelten.
ms.date: 11/01/2020
ms.openlocfilehash: e38ba3bda371c713a8b2cb4cda8b4c585dac29f5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759516"
---
# <a name="obsolete-properties-on-consoleloggeroptions"></a>Veraltete Eigenschaften in ConsoleLoggerOptions

Der Typ <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerFormat?displayProperty=nameWithType> und einige Eigenschaften in <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions> sind nun veraltet.

## <a name="change-description"></a>Änderungsbeschreibung

Ab .NET 5.0 sind der Typ <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerFormat?displayProperty=nameWithType> und mehrere Eigenschaften in <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions> veraltet. Die veraltete Eigenschaften sind:

- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.DisableColors?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.IncludeScopes?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.TimestampFormat?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.UseUtcTimestamp?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format?displayProperty=nameWithType>

Infolge der Einführung von neuen Formatierern sind diese Eigenschaften jetzt in den einzelnen Formatierern verfügbar.

## <a name="reason-for-change"></a>Grund für die Änderung

Die Eigenschaft <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format> ist ein Enumerationstyp, der keinen benutzerdefinierten Formatierer darstellen kann.

Die übrigen Eigenschaften wurden in <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions> festgelegt und auf beide integrierten Formate für Konsolenprotokolle angewendet. Mit der Einführung einer neuen Formatierungs-API ist es jedoch sinnvoller, die Formatierung in den für sie spezifischen Optionen darzustellen. Diese Änderung verbessert die Trennung zwischen der Protokollierung und den Protokollformatierern.

## <a name="version-introduced"></a>Eingeführt in Version

5.0

## <a name="recommended-action"></a>Empfohlene Maßnahme

- Verwenden Sie die neue Eigenschaft <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.FormatterName?displayProperty=nameWithType> anstelle der Eingenschaft <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format?displayProperty=nameWithType>. Beispiel:

  ```csharp
  loggingBuilder.AddConsole(options =>
  {
    options.FormatterName = ConsoleFormatterNames.Systemd;
  });
  ```

  Es gibt mehrere Unterschiede zwischen <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.FormatterName> und <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format>:

  - <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format> verfügt nur über zwei Optionen: `Default` und `Systemd`.
  - Bei <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.FormatterName> wird die Groß-/Kleinschreibung nicht beachtet. Außerdem kann die Eigenschaft eine beliebige Zeichenfolge darstellen. Die reservierten, integrierten Namen lauten `Simple`, `Systemd` und `Json` (.NET 5.0 und höher).
  - `"Format": "Systemd"` wird `"FormatterName": "Systemd"` zugeordnet.
  - `"Format": "Default"` wird `"FormatterName": "Simple"` zugeordnet.

- Verwenden Sie für die Eigenschaften <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.DisableColors>, <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.IncludeScopes>, <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.TimestampFormat> und <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.UseUtcTimestamp> stattdessen die entsprechende Eigenschaft in den neuen Typen <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterOptions>, <xref:Microsoft.Extensions.Logging.Console.JsonConsoleFormatterOptions> oder <xref:Microsoft.Extensions.Logging.Console.SimpleConsoleFormatterOptions>. Beispiel:

  ```csharp
  loggingBuilder.AddSimpleConsole(options =>
  {
      options.DisableColors = true;
  });
  ```

In den beiden folgenden JSON-Codeausschnitten wird gezeigt, wie sich die Konfigurationsdatei ändert. Alte Konfigurationsdatei:

```json
{
  "Logging": {
    "LogLevel": {
      "Default": "None",
      "Microsoft": "Warning",
      "Microsoft.Hosting.Lifetime": "Information"
    },

    "Console": {
      "LogLevel": {
        "Default": "Information"
      },
      "Format": "Systemd",
      "IncludeScopes": true,
      "TimestampFormat": "HH:mm:ss",
      "UseUtcTimestamp": true
    }
  },
  "AllowedHosts": "*"
}
```

Neue Konfigurationsdatei:

```json
{
  "Logging": {
    "LogLevel": {
      "Default": "None",
      "Microsoft": "Warning",
      "Microsoft.Hosting.Lifetime": "Information"
    },

    "Console": {
      "LogLevel": {
        "Default": "Information"
      },
      "FormatterName": "Systemd",
      "FormatterOptions": {
        "IncludeScopes": true,
        "TimestampFormat": "HH:mm:ss",
        "UseUtcTimestamp": true
      }
    }
  },
  "AllowedHosts": "*"
}
```

## <a name="affected-apis"></a>Betroffene APIs

- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.DisableColors?displayProperty=fullName>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.IncludeScopes?displayProperty=fullName>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.TimestampFormat?displayProperty=fullName>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.UseUtcTimestamp?displayProperty=fullName>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format?displayProperty=fullName>

<!--

#### Category

- Core .NET libraries
- ASP.NET

### Affected APIs

- `P:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.DisableColors`
- `P:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.IncludeScopes`
- `P:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.TimestampFormat`
- `P:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.UseUtcTimestamp`
- `P:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format`

-->
