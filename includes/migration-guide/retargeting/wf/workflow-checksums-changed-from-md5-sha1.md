---
ms.openlocfilehash: 72d48d1daa85b6891c122f2fcc5279642253b926
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614552"
---
### <a name="workflow-checksums-changed-from-md5-to-sha1"></a>Änderung der Workflowprüfsummen von MD5 in SHA1

#### <a name="details"></a>Details

Die Workflowlaufzeit generiert unter Verwendung eines Hashalgorithmus zur Unterstützung des Debuggens mit Visual Studio eine Prüfsumme für eine Workflowinstanz. In .NET Framework 4.6.2 und früheren Versionen wird beim Hashing der Workflowprüfsumme der MD5-Algorithmus verwendet, der auf Systemen, auf den FIPS aktiviert ist, Probleme verursacht hat. Ab .NET Framework 4.7 wird der SHA1-Algorithmus verwendet. Wenn Ihr Code diese Prüfsummen dauerhaft gespeichert hat, sind diese nicht kompatibel.

#### <a name="suggestion"></a>Vorschlag

Wenn Ihr Code aufgrund eines Prüfsummenfehlers keine Workflowinstanzen laden kann, sollten Sie versuchen, den `AppContext`-Schalter &quot;Switch.System.Activities.UseMD5ForWFDebugger&quot; auf TRUE festzulegen. Dies können Sie in Form von Code tun:

```csharp
System.AppContext.SetSwitch("Switch.System.Activities.UseMD5ForWFDebugger", true);
```

Stattdessen können Sie dies auch im Rahmen der Konfiguration vornehmen:

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.Activities.UseMD5ForWFDebugger=true" />
  </runtime>
</configuration>
```

| Name    | Wert       |
|:--------|:------------|
| Bereich   | Gering       |
| Version | 4.7         |
| Typ    | Neuzuweisung |
