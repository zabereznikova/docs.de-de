---
ms.openlocfilehash: fa472b3a142f55f0cbdd83eabbbb00bddd9786d8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235639"
---
### <a name="minfreememorypercentagetoactiveservice-is-now-respected"></a><span data-ttu-id="1f16e-101">MinFreeMemoryPercentageToActiveService wird jetzt eingehalten</span><span class="sxs-lookup"><span data-stu-id="1f16e-101">MinFreeMemoryPercentageToActiveService is now respected</span></span>

|   |   |
|---|---|
|<span data-ttu-id="1f16e-102">Details</span><span class="sxs-lookup"><span data-stu-id="1f16e-102">Details</span></span>|<span data-ttu-id="1f16e-103">Diese Einstellung gibt den minimalen Arbeitsspeicher an, der auf dem Server verfügbar sein muss, bevor ein WCF-Dienst aktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="1f16e-103">This setting establishes the minimum memory that must be available on the server before a WCF service can be activated.</span></span> <span data-ttu-id="1f16e-104">Sie dient dazu, <xref:System.OutOfMemoryException?displayProperty=name>-Ausnahmen zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="1f16e-104">It is designed to prevent <xref:System.OutOfMemoryException?displayProperty=name> exceptions.</span></span> <span data-ttu-id="1f16e-105">In .NET Framework 4.5 hatte diese Einstellung keine Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="1f16e-105">In the .NET Framework 4.5, this setting had no effect.</span></span> <span data-ttu-id="1f16e-106">In .NET Framework 4.5.1 wird die Einstellung beobachtet.</span><span class="sxs-lookup"><span data-stu-id="1f16e-106">In the .NET Framework 4.5.1, the setting is observed.</span></span>|
|<span data-ttu-id="1f16e-107">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="1f16e-107">Suggestion</span></span>|<span data-ttu-id="1f16e-108">Eine Ausnahme tritt auf, wenn der auf dem Webserver verfügbare freie Arbeitsspeicher kleiner ist als der Prozentsatz, der in der Konfigurationseinstellung definiert ist.</span><span class="sxs-lookup"><span data-stu-id="1f16e-108">An exception occurs if the free memory available on the web server is less than the percentage defined by the configuration setting.</span></span> <span data-ttu-id="1f16e-109">Einige WCF-Dienste, die zuvor erfolgreich in Umgebungen mit eingeschränktem Arbeitsspeicher gestartet und ausgeführt wurden, schlagen jetzt möglicherweise fehl.</span><span class="sxs-lookup"><span data-stu-id="1f16e-109">Some WCF services that successfully started and ran in a constrained memory environment may now fail.</span></span>|
|<span data-ttu-id="1f16e-110">Bereich</span><span class="sxs-lookup"><span data-stu-id="1f16e-110">Scope</span></span>|<span data-ttu-id="1f16e-111">Gering</span><span class="sxs-lookup"><span data-stu-id="1f16e-111">Minor</span></span>|
|<span data-ttu-id="1f16e-112">Version</span><span class="sxs-lookup"><span data-stu-id="1f16e-112">Version</span></span>|<span data-ttu-id="1f16e-113">4.5.1</span><span class="sxs-lookup"><span data-stu-id="1f16e-113">4.5.1</span></span>|
|<span data-ttu-id="1f16e-114">Typ</span><span class="sxs-lookup"><span data-stu-id="1f16e-114">Type</span></span>|<span data-ttu-id="1f16e-115">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="1f16e-115">Runtime</span></span>|
