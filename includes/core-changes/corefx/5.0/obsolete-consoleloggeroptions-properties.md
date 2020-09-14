---
ms.openlocfilehash: e92fe8364800b1775f0acc31d67aef66a42d0b95
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2020
ms.locfileid: "89465884"
---
### <a name="obsolete-properties-on-consoleloggeroptions"></a><span data-ttu-id="0fbd2-101">Veraltete Eigenschaften in ConsoleLoggerOptions</span><span class="sxs-lookup"><span data-stu-id="0fbd2-101">Obsolete properties on ConsoleLoggerOptions</span></span>

<span data-ttu-id="0fbd2-102">Der Typ <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerFormat?displayProperty=nameWithType> und einige Eigenschaften in <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions> sind nun veraltet.</span><span class="sxs-lookup"><span data-stu-id="0fbd2-102">The <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerFormat?displayProperty=nameWithType> type and some properties on <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions> are now obsolete.</span></span>

#### <a name="change-description"></a><span data-ttu-id="0fbd2-103">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="0fbd2-103">Change description</span></span>

<span data-ttu-id="0fbd2-104">Ab .NET 5.0 sind der Typ <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerFormat?displayProperty=nameWithType> und mehrere Eigenschaften in <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions> veraltet.</span><span class="sxs-lookup"><span data-stu-id="0fbd2-104">Starting in .NET 5.0, the <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerFormat?displayProperty=nameWithType> type and several properties on <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions> are obsolete.</span></span> <span data-ttu-id="0fbd2-105">Die veraltete Eigenschaften sind:</span><span class="sxs-lookup"><span data-stu-id="0fbd2-105">The obsolete properties are:</span></span>

- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.DisableColors?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.IncludeScopes?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.TimestampFormat?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.UseUtcTimestamp?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format?displayProperty=nameWithType>

<span data-ttu-id="0fbd2-106">Infolge der Einführung von neuen Formatierern sind diese Eigenschaften jetzt in den einzelnen Formatierern verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0fbd2-106">With the introduction of new formatters, these properties are now available on the individual formatters.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="0fbd2-107">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="0fbd2-107">Reason for change</span></span>

<span data-ttu-id="0fbd2-108">Die Eigenschaft <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format> ist ein Enumerationstyp, der keinen benutzerdefinierten Formatierer darstellen kann.</span><span class="sxs-lookup"><span data-stu-id="0fbd2-108">The <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format> property is an enumeration type, which cannot represent a custom formatter.</span></span>

<span data-ttu-id="0fbd2-109">Die übrigen Eigenschaften wurden in <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions> festgelegt und auf beide integrierten Formate für Konsolenprotokolle angewendet.</span><span class="sxs-lookup"><span data-stu-id="0fbd2-109">The remaining properties were set on <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions> and applied to both of the built-in formats for console logs.</span></span> <span data-ttu-id="0fbd2-110">Mit der Einführung einer neuen Formatierungs-API ist es jedoch sinnvoller, die Formatierung in den für sie spezifischen Optionen darzustellen.</span><span class="sxs-lookup"><span data-stu-id="0fbd2-110">However, with the introduction of a new formatter API, it makes more sense for formatting to be represented on the formatter-specific options.</span></span> <span data-ttu-id="0fbd2-111">Diese Änderung verbessert die Trennung zwischen der Protokollierung und den Protokollformatierern.</span><span class="sxs-lookup"><span data-stu-id="0fbd2-111">This change provides better separation between the logger and logger formatters.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="0fbd2-112">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="0fbd2-112">Version introduced</span></span>

<span data-ttu-id="0fbd2-113">5.0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="0fbd2-113">5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="0fbd2-114">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="0fbd2-114">Recommended action</span></span>

- <span data-ttu-id="0fbd2-115">Verwenden Sie die neue Eigenschaft <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.FormatterName?displayProperty=nameWithType> anstelle der Eingenschaft <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0fbd2-115">Use the new <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.FormatterName?displayProperty=nameWithType> property in place of the <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="0fbd2-116">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0fbd2-116">For example:</span></span>

  ```csharp
  loggingBuilder.AddConsole(options =>
  {
    options.FormatterName = ConsoleFormatterNames.Systemd;
  });
  ```

  <span data-ttu-id="0fbd2-117">Es gibt mehrere Unterschiede zwischen <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.FormatterName> und <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format>:</span><span class="sxs-lookup"><span data-stu-id="0fbd2-117">There are several differences between <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.FormatterName> and <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format>:</span></span>

  - <span data-ttu-id="0fbd2-118"><xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format> verfügt nur über zwei Optionen: `Default` und `Systemd`.</span><span class="sxs-lookup"><span data-stu-id="0fbd2-118"><xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format> has only two possible options: `Default` and `Systemd`.</span></span>
  - <span data-ttu-id="0fbd2-119">Bei <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.FormatterName> wird die Groß-/Kleinschreibung nicht beachtet. Außerdem kann die Eigenschaft eine beliebige Zeichenfolge darstellen.</span><span class="sxs-lookup"><span data-stu-id="0fbd2-119"><xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.FormatterName> is case insensitive and can be any string.</span></span> <span data-ttu-id="0fbd2-120">Die reservierten, integrierten Namen lauten `Simple`, `Systemd` und `Json` (.NET 5.0 und höher).</span><span class="sxs-lookup"><span data-stu-id="0fbd2-120">The reserved, built-in names are `Simple`, `Systemd`, and `Json` (.NET 5.0 and later).</span></span>
  - <span data-ttu-id="0fbd2-121">`"Format": "Systemd"` wird `"FormatterName": "Systemd"` zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="0fbd2-121">`"Format": "Systemd"` maps to `"FormatterName": "Systemd"`.</span></span>
  - <span data-ttu-id="0fbd2-122">`"Format": "Default"` wird `"FormatterName": "Simple"` zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="0fbd2-122">`"Format": "Default"` maps to `"FormatterName": "Simple"`.</span></span>

- <span data-ttu-id="0fbd2-123">Verwenden Sie für die Eigenschaften <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.DisableColors>, <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.IncludeScopes>, <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.TimestampFormat> und <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.UseUtcTimestamp> stattdessen die entsprechende Eigenschaft in den neuen Typen <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterOptions>, <xref:Microsoft.Extensions.Logging.Console.JsonConsoleFormatterOptions> oder <xref:Microsoft.Extensions.Logging.Console.SimpleConsoleFormatterOptions>.</span><span class="sxs-lookup"><span data-stu-id="0fbd2-123">For the <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.DisableColors>, <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.IncludeScopes>, <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.TimestampFormat>, and <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.UseUtcTimestamp> properties, use the corresponding property on the new <xref:Microsoft.Extensions.Logging.Console.ConsoleFormatterOptions>, <xref:Microsoft.Extensions.Logging.Console.JsonConsoleFormatterOptions>, or <xref:Microsoft.Extensions.Logging.Console.SimpleConsoleFormatterOptions> types instead.</span></span> <span data-ttu-id="0fbd2-124">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0fbd2-124">For example:</span></span>

  ```csharp
  loggingBuilder.AddSimpleConsole(options =>
  {
      options.DisableColors = true;
  });
  ```

<span data-ttu-id="0fbd2-125">In den beiden folgenden JSON-Codeausschnitten wird gezeigt, wie sich die Konfigurationsdatei ändert.</span><span class="sxs-lookup"><span data-stu-id="0fbd2-125">The following two JSON snippets show how the configuration file changes.</span></span> <span data-ttu-id="0fbd2-126">Alte Konfigurationsdatei:</span><span class="sxs-lookup"><span data-stu-id="0fbd2-126">Old configuration file:</span></span>

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

<span data-ttu-id="0fbd2-127">Neue Konfigurationsdatei:</span><span class="sxs-lookup"><span data-stu-id="0fbd2-127">New configuration file:</span></span>

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

#### <a name="category"></a><span data-ttu-id="0fbd2-128">Kategorie</span><span class="sxs-lookup"><span data-stu-id="0fbd2-128">Category</span></span>

- <span data-ttu-id="0fbd2-129">Core .NET-Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="0fbd2-129">Core .NET libraries</span></span>
- <span data-ttu-id="0fbd2-130">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="0fbd2-130">ASP.NET</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="0fbd2-131">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="0fbd2-131">Affected APIs</span></span>

- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.DisableColors?displayProperty=fullName>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.IncludeScopes?displayProperty=fullName>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.TimestampFormat?displayProperty=fullName>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.UseUtcTimestamp?displayProperty=fullName>
- <xref:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format?displayProperty=fullName>

<!--

#### Affected APIs

- `P:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.DisableColors`
- `P:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.IncludeScopes`
- `P:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.TimestampFormat`
- `P:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.UseUtcTimestamp`
- `P:Microsoft.Extensions.Logging.Console.ConsoleLoggerOptions.Format`

-->
