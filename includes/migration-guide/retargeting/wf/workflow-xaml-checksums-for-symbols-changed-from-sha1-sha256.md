---
ms.openlocfilehash: 946e71f2f466664c8f9fcf4811288ce693a872eb
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616254"
---
### <a name="workflow-xaml-checksums-for-symbols-changed-from-sha1-to-sha256"></a>Änderung der Workflow-XAML-Prüfsummen für Symbole von SHA1 in SHA256

#### <a name="details"></a>Details

Die Workflowlaufzeit generiert unter Verwendung eines Hashalgorithmus zur Unterstützung des Debuggens mit Visual Studio eine Prüfsumme für eine Workflow-XAML-Datei. In .NET Framework 4.6.2 und früheren Versionen wird beim Hashing der Workflowprüfsumme der MD5-Algorithmus verwendet, der auf Systemen, auf den FIPS aktiviert ist, Probleme verursacht hat. Ab .NET Framework 4.7 wurde der Standardalgorithmus in SHA1 geändert. Ab .NET Framework 4.8 wurde der Standardalgorithmus in SHA256 geändert.

#### <a name="suggestion"></a>Vorschlag

Wenn Ihr Code aufgrund eines Prüfsummenfehlers keine Workflowinstanzen laden oder keine entsprechende Symbole finden kann, sollten Sie versuchen, die `AppContext`-Option „Switch.System.Activities.UseSHA1HashForDebuggerSymbols“ auf `true` festzulegen. In Code:

```csharp
System.AppContext.SetSwitch("Switch.System.Activities.UseSHA1HashForDebuggerSymbols", true);
```

Stattdessen können Sie dies auch im Rahmen der Konfiguration vornehmen:

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.Activities.UseSHA1HashForDebuggerSymbols=true" />
  </runtime>
</configuration>
```

| name    | Wert       |
|:--------|:------------|
| Bereich   | Gering       |
| Version | 4.8         |
| Typ    | Neuzuweisung |
