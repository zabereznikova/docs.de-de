---
ms.openlocfilehash: 946e71f2f466664c8f9fcf4811288ce693a872eb
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616254"
---
### <a name="workflow-xaml-checksums-for-symbols-changed-from-sha1-to-sha256"></a><span data-ttu-id="b394e-101">Änderung der Workflow-XAML-Prüfsummen für Symbole von SHA1 in SHA256</span><span class="sxs-lookup"><span data-stu-id="b394e-101">Workflow XAML checksums for symbols changed from SHA1 to SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="b394e-102">Details</span><span class="sxs-lookup"><span data-stu-id="b394e-102">Details</span></span>

<span data-ttu-id="b394e-103">Die Workflowlaufzeit generiert unter Verwendung eines Hashalgorithmus zur Unterstützung des Debuggens mit Visual Studio eine Prüfsumme für eine Workflow-XAML-Datei.</span><span class="sxs-lookup"><span data-stu-id="b394e-103">To support debugging with Visual Studio, the Workflow runtime generates a checksum for a workflow XAML file using a hashing algorithm.</span></span> <span data-ttu-id="b394e-104">In .NET Framework 4.6.2 und früheren Versionen wird beim Hashing der Workflowprüfsumme der MD5-Algorithmus verwendet, der auf Systemen, auf den FIPS aktiviert ist, Probleme verursacht hat.</span><span class="sxs-lookup"><span data-stu-id="b394e-104">In the .NET Framework 4.6.2 and earlier versions, workflow checksum hashing used the MD5 algorithm, which caused issues on FIPS-enabled systems.</span></span> <span data-ttu-id="b394e-105">Ab .NET Framework 4.7 wurde der Standardalgorithmus in SHA1 geändert.</span><span class="sxs-lookup"><span data-stu-id="b394e-105">Starting with the .NET Framework 4.7, the default algorithm was changed to SHA1.</span></span> <span data-ttu-id="b394e-106">Ab .NET Framework 4.8 wurde der Standardalgorithmus in SHA256 geändert.</span><span class="sxs-lookup"><span data-stu-id="b394e-106">Starting with the .NET Framework 4.8, the default algorithm was changed to SHA256.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="b394e-107">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="b394e-107">Suggestion</span></span>

<span data-ttu-id="b394e-108">Wenn Ihr Code aufgrund eines Prüfsummenfehlers keine Workflowinstanzen laden oder keine entsprechende Symbole finden kann, sollten Sie versuchen, die `AppContext`-Option „Switch.System.Activities.UseSHA1HashForDebuggerSymbols“ auf `true` festzulegen.</span><span class="sxs-lookup"><span data-stu-id="b394e-108">If your code is unable to load workflow instances or to find appropriate symbols due to a checksum failure, try setting the `AppContext` switch "Switch.System.Activities.UseSHA1HashForDebuggerSymbols" to `true`.</span></span> <span data-ttu-id="b394e-109">In Code:</span><span class="sxs-lookup"><span data-stu-id="b394e-109">In code:</span></span>

```csharp
System.AppContext.SetSwitch("Switch.System.Activities.UseSHA1HashForDebuggerSymbols", true);
```

<span data-ttu-id="b394e-110">Stattdessen können Sie dies auch im Rahmen der Konfiguration vornehmen:</span><span class="sxs-lookup"><span data-stu-id="b394e-110">Or in configuration:</span></span>

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.Activities.UseSHA1HashForDebuggerSymbols=true" />
  </runtime>
</configuration>
```

| <span data-ttu-id="b394e-111">name</span><span class="sxs-lookup"><span data-stu-id="b394e-111">Name</span></span>    | <span data-ttu-id="b394e-112">Wert</span><span class="sxs-lookup"><span data-stu-id="b394e-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="b394e-113">Bereich</span><span class="sxs-lookup"><span data-stu-id="b394e-113">Scope</span></span>   | <span data-ttu-id="b394e-114">Gering</span><span class="sxs-lookup"><span data-stu-id="b394e-114">Minor</span></span>       |
| <span data-ttu-id="b394e-115">Version</span><span class="sxs-lookup"><span data-stu-id="b394e-115">Version</span></span> | <span data-ttu-id="b394e-116">4.8</span><span class="sxs-lookup"><span data-stu-id="b394e-116">4.8</span></span>         |
| <span data-ttu-id="b394e-117">Typ</span><span class="sxs-lookup"><span data-stu-id="b394e-117">Type</span></span>    | <span data-ttu-id="b394e-118">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="b394e-118">Retargeting</span></span> |
