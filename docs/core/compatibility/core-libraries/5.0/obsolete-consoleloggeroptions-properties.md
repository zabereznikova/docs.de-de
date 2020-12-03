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
# <a name="obsolete-properties-on-consoleloggeroptions"></a><span data-ttu-id="66f37-103">Veraltete Eigenschaften in ConsoleLoggerOptions</span><span class="sxs-lookup"><span data-stu-id="66f37-103">Obsolete properties on ConsoleLoggerOptions</span></span>

<span data-ttu-id="66f37-104">Der Typ <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerFormat?displayProperty=nameWithType> und einige Eigenschaften in <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions> sind nun veraltet.</span><span class="sxs-lookup"><span data-stu-id="66f37-104">The <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerFormat?displayProperty=nameWithType> type and some properties on <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions> are now obsolete.</span></span>

## <a name="change-description"></a><span data-ttu-id="66f37-105">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="66f37-105">Change description</span></span>

<span data-ttu-id="66f37-106">Ab .NET 5.0 sind der Typ <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerFormat?displayProperty=nameWithType> und mehrere Eigenschaften in <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions> veraltet.</span><span class="sxs-lookup"><span data-stu-id="66f37-106">Starting in .NET 5.0, the <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerFormat?displayProperty=nameWithType> type and several properties on <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions> are obsolete.</span></span> <span data-ttu-id="66f37-107">Die veraltete Eigenschaften sind:</span><span class="sxs-lookup"><span data-stu-id="66f37-107">The obsolete properties are:</span></span>

- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.DisableColors?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.IncludeScopes?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.TimestampFormat?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.UseUtcTimestamp?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format?displayProperty=nameWithType>

<span data-ttu-id="66f37-108">Infolge der Einführung von neuen Formatierern sind diese Eigenschaften jetzt in den einzelnen Formatierern verfügbar.</span><span class="sxs-lookup"><span data-stu-id="66f37-108">With the introduction of new formatters, these properties are now available on the individual formatters.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="66f37-109">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="66f37-109">Reason for change</span></span>

<span data-ttu-id="66f37-110">Die Eigenschaft <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format> ist ein Enumerationstyp, der keinen benutzerdefinierten Formatierer darstellen kann.</span><span class="sxs-lookup"><span data-stu-id="66f37-110">The <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format> property is an enumeration type, which cannot represent a custom formatter.</span></span>

<span data-ttu-id="66f37-111">Die übrigen Eigenschaften wurden in <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions> festgelegt und auf beide integrierten Formate für Konsolenprotokolle angewendet.</span><span class="sxs-lookup"><span data-stu-id="66f37-111">The remaining properties were set on <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions> and applied to both of the built-in formats for console logs.</span></span> <span data-ttu-id="66f37-112">Mit der Einführung einer neuen Formatierungs-API ist es jedoch sinnvoller, die Formatierung in den für sie spezifischen Optionen darzustellen.</span><span class="sxs-lookup"><span data-stu-id="66f37-112">However, with the introduction of a new formatter API, it makes more sense for formatting to be represented on the formatter-specific options.</span></span> <span data-ttu-id="66f37-113">Diese Änderung verbessert die Trennung zwischen der Protokollierung und den Protokollformatierern.</span><span class="sxs-lookup"><span data-stu-id="66f37-113">This change provides better separation between the logger and logger formatters.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="66f37-114">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="66f37-114">Version introduced</span></span>

<span data-ttu-id="66f37-115">5.0</span><span class="sxs-lookup"><span data-stu-id="66f37-115">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="66f37-116">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="66f37-116">Recommended action</span></span>

- <span data-ttu-id="66f37-117">Verwenden Sie die neue Eigenschaft <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.FormatterName?displayProperty=nameWithType> anstelle der Eingenschaft <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="66f37-117">Use the new <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.FormatterName?displayProperty=nameWithType> property in place of the <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="66f37-118">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="66f37-118">For example:</span></span>

  ```csharp
  loggingBuilder.AddConsole(options =>
  {
    options.FormatterName = ConsoleFormatterNames.Systemd;
  });
  ```

  <span data-ttu-id="66f37-119">Es gibt mehrere Unterschiede zwischen <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.FormatterName> und <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format>:</span><span class="sxs-lookup"><span data-stu-id="66f37-119">There are several differences between <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.FormatterName> and <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format>:</span></span>

  - <span data-ttu-id="66f37-120"><xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format> verfügt nur über zwei Optionen: `Default` und `Systemd`.</span><span class="sxs-lookup"><span data-stu-id="66f37-120"><xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format> has only two possible options: `Default` and `Systemd`.</span></span>
  - <span data-ttu-id="66f37-121">Bei <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.FormatterName> wird die Groß-/Kleinschreibung nicht beachtet. Außerdem kann die Eigenschaft eine beliebige Zeichenfolge darstellen.</span><span class="sxs-lookup"><span data-stu-id="66f37-121"><xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.FormatterName> is case insensitive and can be any string.</span></span> <span data-ttu-id="66f37-122">Die reservierten, integrierten Namen lauten `Simple`, `Systemd` und `Json` (.NET 5.0 und höher).</span><span class="sxs-lookup"><span data-stu-id="66f37-122">The reserved, built-in names are `Simple`, `Systemd`, and `Json` (.NET 5.0 and later).</span></span>
  - <span data-ttu-id="66f37-123">`"Format": "Systemd"` wird `"FormatterName": "Systemd"` zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="66f37-123">`"Format": "Systemd"` maps to `"FormatterName": "Systemd"`.</span></span>
  - <span data-ttu-id="66f37-124">`"Format": "Default"` wird `"FormatterName": "Simple"` zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="66f37-124">`"Format": "Default"` maps to `"FormatterName": "Simple"`.</span></span>

- <span data-ttu-id="66f37-125">Verwenden Sie für die Eigenschaften <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.DisableColors>, <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.IncludeScopes>, <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.TimestampFormat> und <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.UseUtcTimestamp> stattdessen die entsprechende Eigenschaft in den neuen Typen <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterOptions>, <xref:Microsoft.Extensions.Logging.Console.JsonConsoleFormatterOptions> oder <xref:Microsoft.Extensions.Logging.Console.SimpleConsoleFormatterOptions>.</span><span class="sxs-lookup"><span data-stu-id="66f37-125">For the <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.DisableColors>, <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.IncludeScopes>, <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.TimestampFormat>, and <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.UseUtcTimestamp> properties, use the corresponding property on the new <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterOptions>, <xref:Microsoft.Extensions.Logging.Console.JsonConsoleFormatterOptions>, or <xref:Microsoft.Extensions.Logging.Console.SimpleConsoleFormatterOptions> types instead.</span></span> <span data-ttu-id="66f37-126">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="66f37-126">For example:</span></span>

  ```csharp
  loggingBuilder.AddSimpleConsole(options =>
  {
      options.DisableColors = true;
  });
  ```

<span data-ttu-id="66f37-127">In den beiden folgenden JSON-Codeausschnitten wird gezeigt, wie sich die Konfigurationsdatei ändert.</span><span class="sxs-lookup"><span data-stu-id="66f37-127">The following two JSON snippets show how the configuration file changes.</span></span> <span data-ttu-id="66f37-128">Alte Konfigurationsdatei:</span><span class="sxs-lookup"><span data-stu-id="66f37-128">Old configuration file:</span></span>

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

<span data-ttu-id="66f37-129">Neue Konfigurationsdatei:</span><span class="sxs-lookup"><span data-stu-id="66f37-129">New configuration file:</span></span>

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

## <a name="affected-apis"></a><span data-ttu-id="66f37-130">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="66f37-130">Affected APIs</span></span>

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
