---
ms.openlocfilehash: 2aa424ff5e3308b730c22cb865993d4100f193cc
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616256"
---
### <a name="workflow-xoml-file-checksums-changed-from-md5-to-sha256"></a><span data-ttu-id="284ac-101">Änderung der Workflowprüfsummen der XOML-Datei von MD5 in SHA256</span><span class="sxs-lookup"><span data-stu-id="284ac-101">Workflow XOML file checksums changed from MD5 to SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="284ac-102">Details</span><span class="sxs-lookup"><span data-stu-id="284ac-102">Details</span></span>

<span data-ttu-id="284ac-103">Um das Debuggen von XOML-basierten Workflows mit Visual Studio zu unterstützen, wird beim Erstellen von Workflowprojekten, die XOML-Dateien enthalten, eine Prüfsumme des Inhalts der XOML-Datei in den als <xref:System.Workflow.ComponentModel.Compiler.WorkflowMarkupSourceAttribute.MD5Digest?displayProperty=nameWithType>-Wert erzeugten Code aufgenommen.</span><span class="sxs-lookup"><span data-stu-id="284ac-103">To support debugging XOML-based workflows with Visual Studio, when workflow projects containing XOML files build, a checksum of the contents of the XOML file is included in the code generated as a <xref:System.Workflow.ComponentModel.Compiler.WorkflowMarkupSourceAttribute.MD5Digest?displayProperty=nameWithType> value.</span></span> <span data-ttu-id="284ac-104">In .NET Framework 4.7.2 und früheren Versionen wird beim Hashing der Prüfsumme der MD5-Algorithmus verwendet, der auf Systemen, auf den FIPS aktiviert ist, Probleme verursacht hat.</span><span class="sxs-lookup"><span data-stu-id="284ac-104">In the .NET Framework 4.7.2 and earlier versions, this checksum hashing used the MD5 algorithm, which caused issues on FIPS-enabled systems.</span></span> <span data-ttu-id="284ac-105">Ab .NET Framework 4.8 wird der SHA256-Algorithmus verwendet.</span><span class="sxs-lookup"><span data-stu-id="284ac-105">Starting with the .NET Framework 4.8, the algorithm used is SHA256.</span></span> <span data-ttu-id="284ac-106">Um mit dem WorkflowMarkupSourceAttribute.MD5Digest kompatibel zu sein, werden nur die ersten 16 Bytes der erzeugten Prüfsumme verwendet. Dies kann zu Problemen beim Debuggen führen.</span><span class="sxs-lookup"><span data-stu-id="284ac-106">To be compatibile with the WorkflowMarkupSourceAttribute.MD5Digest, only the first 16 bytes of the generated checksum are used.This may cause problems during debugging.</span></span> <span data-ttu-id="284ac-107">Sie müssen das Projekt ggf. neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="284ac-107">You may need to re-build your project.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="284ac-108">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="284ac-108">Suggestion</span></span>

<span data-ttu-id="284ac-109">Wenn die Neuerstellung Ihres Projekts das Problem nicht löst, versuchen Sie, den `AppContext`-Schalter &quot;Switch.System.Workflow.ComponentModel.UseLegacyHashForXomlFileChecksum&quot; auf TRUE zu setzen. In Code:</span><span class="sxs-lookup"><span data-stu-id="284ac-109">If re-building your project does not solve the problem, try setting the `AppContext` switch &quot;Switch.System.Workflow.ComponentModel.UseLegacyHashForXomlFileChecksum&quot; to true.In code:</span></span>

<pre><code class="lang-csharp">System.AppContext.SetSwitch(&quot;Switch.System.Workflow.ComponentModel.UseLegacyHashForXomlFileChecksum&quot;, true);&#13;&#10;</code></pre>

<span data-ttu-id="284ac-110">Oder in einer Konfigurationsdatei (diese muss sich in MSBuild.exe.config für die von Ihnen verwendete MSBuild.exe befinden):</span><span class="sxs-lookup"><span data-stu-id="284ac-110">Or in a configuration file (this needs to be in MSBuild.exe.config for the MSBuild.exe that you are using):</span></span>

<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Workflow.ComponentModel.UseLegacyHashForXomlFileChecksum=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="284ac-111">Name</span><span class="sxs-lookup"><span data-stu-id="284ac-111">Name</span></span>    | <span data-ttu-id="284ac-112">Wert</span><span class="sxs-lookup"><span data-stu-id="284ac-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="284ac-113">Bereich</span><span class="sxs-lookup"><span data-stu-id="284ac-113">Scope</span></span>   | <span data-ttu-id="284ac-114">Gering</span><span class="sxs-lookup"><span data-stu-id="284ac-114">Minor</span></span>       |
| <span data-ttu-id="284ac-115">Version</span><span class="sxs-lookup"><span data-stu-id="284ac-115">Version</span></span> | <span data-ttu-id="284ac-116">4.8</span><span class="sxs-lookup"><span data-stu-id="284ac-116">4.8</span></span>         |
| <span data-ttu-id="284ac-117">Typ</span><span class="sxs-lookup"><span data-stu-id="284ac-117">Type</span></span>    | <span data-ttu-id="284ac-118">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="284ac-118">Retargeting</span></span> |
