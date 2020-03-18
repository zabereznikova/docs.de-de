---
ms.openlocfilehash: f59c9f048bb3cd3f425e36b931302258fcf693f5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67803498"
---
### <a name="workflow-xoml-file-checksums-changed-from-md5-to-sha256"></a>Änderung der Workflowprüfsummen der XOML-Datei von MD5 in SHA256

|   |   |
|---|---|
|Details|Um das Debuggen von XOML-basierten Workflows mit Visual Studio zu unterstützen, wird beim Erstellen von Workflowprojekten, die XOML-Dateien enthalten, eine Prüfsumme des Inhalts der XOML-Datei in den als <xref:System.Workflow.ComponentModel.Compiler.WorkflowMarkupSourceAttribute.MD5Digest?displayProperty=nameWithType>-Wert erzeugten Code aufgenommen. In .NET Framework 4.7.2 und früheren Versionen wird beim Hashing der Prüfsumme der MD5-Algorithmus verwendet, der auf Systemen, auf den FIPS aktiviert ist, Probleme verursacht hat. Ab .NET Framework 4.8 wird der SHA256-Algorithmus verwendet. Um mit dem WorkflowMarkupSourceAttribute.MD5Digest kompatibel zu sein, werden nur die ersten 16 Bytes der erzeugten Prüfsumme verwendet. Dies kann zu Problemen beim Debuggen führen. Sie müssen das Projekt ggf. neu erstellen.|
|Vorschlag|Wenn die Neuerstellung Ihres Projekts das Problem nicht löst, versuchen Sie, den <code>AppContext</code>-Schalter &quot;Switch.System.Workflow.ComponentModel.UseLegacyHashForXomlFileChecksum&quot; auf TRUE zu setzen. In Code:<pre><code class="lang-csharp">System.AppContext.SetSwitch(&quot;Switch.System.Workflow.ComponentModel.UseLegacyHashForXomlFileChecksum&quot;, true);&#13;&#10;</code></pre>Oder in einer Konfigurationsdatei (diese muss sich in MSBuild.exe.config für die von Ihnen verwendete MSBuild.exe befinden):<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Workflow.ComponentModel.UseLegacyHashForXomlFileChecksum=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|`Scope`|Nebenversion|
|Version|4.8|
|Geben Sie Folgendes ein:|Neuzuweisung|
