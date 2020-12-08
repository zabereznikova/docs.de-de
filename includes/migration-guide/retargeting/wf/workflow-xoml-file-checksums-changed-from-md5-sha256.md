---
ms.openlocfilehash: b1910bf0338bccd77ad9e983990d4d193698ec1f
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/01/2020
ms.locfileid: "96477857"
---
### <a name="workflow-xoml-file-checksums-changed-from-md5-to-sha256"></a>Änderung der Workflowprüfsummen der XOML-Datei von MD5 in SHA256

#### <a name="details"></a>Details

Um das Debuggen von XOML-basierten Workflows mit Visual Studio zu unterstützen, wird beim Erstellen von Workflowprojekten, die XOML-Dateien enthalten, eine Prüfsumme des Inhalts der XOML-Datei in den als <xref:System.Workflow.ComponentModel.Compiler.WorkflowMarkupSourceAttribute.MD5Digest?displayProperty=nameWithType>-Wert erzeugten Code aufgenommen. In .NET Framework 4.7.2 und früheren Versionen wird beim Hashing der Prüfsumme der MD5-Algorithmus verwendet, der auf Systemen, auf den FIPS aktiviert ist, Probleme verursacht hat. Ab .NET Framework 4.8 wird der SHA256-Algorithmus verwendet. Um mit dem WorkflowMarkupSourceAttribute.MD5Digest kompatibel zu sein, werden nur die ersten 16 Bytes der erzeugten Prüfsumme verwendet. Dies kann zu Problemen beim Debuggen führen. Sie müssen das Projekt ggf. neu erstellen.

#### <a name="suggestion"></a>Vorschlag

Wenn die Neuerstellung Ihres Projekts das Problem nicht löst, versuchen Sie, den `AppContext`-Schalter &quot;Switch.System.Workflow.ComponentModel.UseLegacyHashForXomlFileChecksum&quot; auf TRUE zu setzen. In Code:

<pre><code class="lang-csharp">System.AppContext.SetSwitch(&quot;Switch.System.Workflow.ComponentModel.UseLegacyHashForXomlFileChecksum&quot;, true);&#13;&#10;</code></pre>

Oder in einer Konfigurationsdatei (diese muss sich in MSBuild.exe.config für die von Ihnen verwendete MSBuild.exe befinden):

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Workflow.ComponentModel.UseLegacyHashForXomlFileChecksum=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| name    | Wert       |
|:--------|:------------|
| Bereich   | Gering       |
| Version | 4.8         |
| Typ    | Neuzuweisung |
