---
ms.openlocfilehash: 416590c7bd959eea011b7e7c5db48f22d349d0f5
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615663"
---
### <a name="apps-published-with-clickonce-that-use-a-sha-256-code-signing-certificate-may-fail-on-windows-2003"></a><span data-ttu-id="ba4b9-101">Mit ClickOnce veröffentlichte Apps, die ein SHA-256-Codesignaturzertifikat verwenden, verursachen unter Windows 2003 möglicherweise einen Fehler</span><span class="sxs-lookup"><span data-stu-id="ba4b9-101">Apps published with ClickOnce that use a SHA-256 code-signing certificate may fail on Windows 2003</span></span>

#### <a name="details"></a><span data-ttu-id="ba4b9-102">Details</span><span class="sxs-lookup"><span data-stu-id="ba4b9-102">Details</span></span>

<span data-ttu-id="ba4b9-103">Die ausführbare Datei ist mit SHA256 signiert.</span><span class="sxs-lookup"><span data-stu-id="ba4b9-103">The executable is signed with SHA256.</span></span> <span data-ttu-id="ba4b9-104">Früher wurde sie mit SHA1 signiert, unabhängig davon, ob das Codesignaturzertifikat SHA-1 oder SHA-256 war.</span><span class="sxs-lookup"><span data-stu-id="ba4b9-104">Previously, it was signed with SHA1 regardless of whether the code-signing certificate was SHA-1 or SHA-256.</span></span> <span data-ttu-id="ba4b9-105">Dies gilt für:</span><span class="sxs-lookup"><span data-stu-id="ba4b9-105">This applies to:</span></span>

- <span data-ttu-id="ba4b9-106">Alle Anwendungen, die mit Visual Studio 2012 oder höher erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="ba4b9-106">All applications built with Visual Studio 2012 or later.</span></span>
- <span data-ttu-id="ba4b9-107">Anwendungen, die mit Visual Studio 2010 oder früher auf Systemen mit vorhandenem .NET Framework 4.5 erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="ba4b9-107">Applications built with Visual Studio 2010 or earlier on systems with the .NET Framework 4.5 present.</span></span>
<span data-ttu-id="ba4b9-108">Darüber hinaus wird das ClickOnce-Manifest, wenn .NET Framework 4.5 oder höher vorhanden ist, auch mit SHA-256 für SHA-256-Zertifikate signiert, unabhängig von der .NET Framework-Version, mit der es kompiliert wurde.</span><span class="sxs-lookup"><span data-stu-id="ba4b9-108">In addition, if the .NET Framework 4.5 or later is present, the ClickOnce manifest is also signed with SHA-256 for SHA-256 certificates regardless of the .NET Framework version against which it was compiled.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="ba4b9-109">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="ba4b9-109">Suggestion</span></span>

<span data-ttu-id="ba4b9-110">Die Änderung bei der Signierung der ausführbaren ClickOnce-Datei betrifft nur Windows Server 2003-Systeme. Für diese ist die Installation von KB 938397 erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ba4b9-110">The change in signing the ClickOnce executable affects only Windows Server 2003 systems; they require that KB 938397 be installed.</span></span> <span data-ttu-id="ba4b9-111">Die Änderung bei der Signierung des Manifests mit SHA-256, selbst wenn eine App auf .NET Framework 4.0 oder frühere Versionen abzielt, führt eine Laufzeitabhängigkeit von .NET Framework 4.5 oder einer höheren Version ein.</span><span class="sxs-lookup"><span data-stu-id="ba4b9-111">The change in signing the manifest with SHA-256 even when an app targets the .NET Framework 4.0 or earlier versions introduces a runtime dependency on the .NET Framework 4.5 or a later version.</span></span>

| <span data-ttu-id="ba4b9-112">name</span><span class="sxs-lookup"><span data-stu-id="ba4b9-112">Name</span></span>    | <span data-ttu-id="ba4b9-113">Wert</span><span class="sxs-lookup"><span data-stu-id="ba4b9-113">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="ba4b9-114">Bereich</span><span class="sxs-lookup"><span data-stu-id="ba4b9-114">Scope</span></span>   | <span data-ttu-id="ba4b9-115">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="ba4b9-115">Edge</span></span>        |
| <span data-ttu-id="ba4b9-116">Version</span><span class="sxs-lookup"><span data-stu-id="ba4b9-116">Version</span></span> | <span data-ttu-id="ba4b9-117">4.5</span><span class="sxs-lookup"><span data-stu-id="ba4b9-117">4.5</span></span>         |
| <span data-ttu-id="ba4b9-118">Typ</span><span class="sxs-lookup"><span data-stu-id="ba4b9-118">Type</span></span>    | <span data-ttu-id="ba4b9-119">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="ba4b9-119">Retargeting</span></span> |
