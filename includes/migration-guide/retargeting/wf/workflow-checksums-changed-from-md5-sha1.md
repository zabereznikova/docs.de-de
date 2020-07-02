---
ms.openlocfilehash: 72d48d1daa85b6891c122f2fcc5279642253b926
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614552"
---
### <a name="workflow-checksums-changed-from-md5-to-sha1"></a><span data-ttu-id="a4faa-101">Änderung der Workflowprüfsummen von MD5 in SHA1</span><span class="sxs-lookup"><span data-stu-id="a4faa-101">Workflow checksums changed from MD5 to SHA1</span></span>

#### <a name="details"></a><span data-ttu-id="a4faa-102">Details</span><span class="sxs-lookup"><span data-stu-id="a4faa-102">Details</span></span>

<span data-ttu-id="a4faa-103">Die Workflowlaufzeit generiert unter Verwendung eines Hashalgorithmus zur Unterstützung des Debuggens mit Visual Studio eine Prüfsumme für eine Workflowinstanz.</span><span class="sxs-lookup"><span data-stu-id="a4faa-103">To support debugging with Visual Studio, the Workflow runtime generates a checksum for a workflow instance using a hashing algorithm.</span></span> <span data-ttu-id="a4faa-104">In .NET Framework 4.6.2 und früheren Versionen wird beim Hashing der Workflowprüfsumme der MD5-Algorithmus verwendet, der auf Systemen, auf den FIPS aktiviert ist, Probleme verursacht hat.</span><span class="sxs-lookup"><span data-stu-id="a4faa-104">In the .NET Framework 4.6.2 and earlier versions, workflow checksum hashing used the MD5 algorithm, which caused issues on FIPS-enabled systems.</span></span> <span data-ttu-id="a4faa-105">Ab .NET Framework 4.7 wird der SHA1-Algorithmus verwendet.</span><span class="sxs-lookup"><span data-stu-id="a4faa-105">Starting with the .NET Framework 4.7, the algorithm is SHA1.</span></span> <span data-ttu-id="a4faa-106">Wenn Ihr Code diese Prüfsummen dauerhaft gespeichert hat, sind diese nicht kompatibel.</span><span class="sxs-lookup"><span data-stu-id="a4faa-106">If your code has persisted these checksums, they will be incompatible.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="a4faa-107">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="a4faa-107">Suggestion</span></span>

<span data-ttu-id="a4faa-108">Wenn Ihr Code aufgrund eines Prüfsummenfehlers keine Workflowinstanzen laden kann, sollten Sie versuchen, den `AppContext`-Schalter &quot;Switch.System.Activities.UseMD5ForWFDebugger&quot; auf TRUE festzulegen. Dies können Sie in Form von Code tun:</span><span class="sxs-lookup"><span data-stu-id="a4faa-108">If your code is unable to load workflow instances due to a checksum failure, try setting the `AppContext` switch &quot;Switch.System.Activities.UseMD5ForWFDebugger&quot; to true.In code:</span></span>

```csharp
System.AppContext.SetSwitch("Switch.System.Activities.UseMD5ForWFDebugger", true);
```

<span data-ttu-id="a4faa-109">Stattdessen können Sie dies auch im Rahmen der Konfiguration vornehmen:</span><span class="sxs-lookup"><span data-stu-id="a4faa-109">Or in configuration:</span></span>

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.Activities.UseMD5ForWFDebugger=true" />
  </runtime>
</configuration>
```

| <span data-ttu-id="a4faa-110">Name</span><span class="sxs-lookup"><span data-stu-id="a4faa-110">Name</span></span>    | <span data-ttu-id="a4faa-111">Wert</span><span class="sxs-lookup"><span data-stu-id="a4faa-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="a4faa-112">Bereich</span><span class="sxs-lookup"><span data-stu-id="a4faa-112">Scope</span></span>   | <span data-ttu-id="a4faa-113">Gering</span><span class="sxs-lookup"><span data-stu-id="a4faa-113">Minor</span></span>       |
| <span data-ttu-id="a4faa-114">Version</span><span class="sxs-lookup"><span data-stu-id="a4faa-114">Version</span></span> | <span data-ttu-id="a4faa-115">4.7</span><span class="sxs-lookup"><span data-stu-id="a4faa-115">4.7</span></span>         |
| <span data-ttu-id="a4faa-116">Typ</span><span class="sxs-lookup"><span data-stu-id="a4faa-116">Type</span></span>    | <span data-ttu-id="a4faa-117">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="a4faa-117">Retargeting</span></span> |
