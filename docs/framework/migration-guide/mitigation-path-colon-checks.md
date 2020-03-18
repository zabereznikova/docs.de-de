---
title: 'Entschärfung: Überprüfung von Pfaden auf Doppelpunkte'
ms.date: 03/30/2017
ms.assetid: a0bb52de-d279-419d-8f23-4b12d1a3f36e
ms.openlocfilehash: c6e1106b6f5d8457417992941b9f28712d484442
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "79181246"
---
# <a name="mitigation-path-colon-checks"></a><span data-ttu-id="03562-102">Entschärfung: Überprüfung von Pfaden auf Doppelpunkte</span><span class="sxs-lookup"><span data-stu-id="03562-102">Mitigation: Path Colon Checks</span></span>
<span data-ttu-id="03562-103">Für Apps, die gezielt .NET Framework 4.6.2 und höhere Versionen verwenden, wurde eine Reihe von Änderungen vorgenommen, um zuvor nicht unterstützte Pfade zu unterstützen (im Hinblick auf Länge und Format).</span><span class="sxs-lookup"><span data-stu-id="03562-103">Starting with apps that target the .NET Framework 4.6.2, a number of changes were made to support previously unsupported paths (both in terms of length and format).</span></span> <span data-ttu-id="03562-104">Insbesondere wurden Prüfungen auf ordnungsgemäße Syntax von Laufwerkstrennzeichen (den Doppelpunkt) strenger definiert.</span><span class="sxs-lookup"><span data-stu-id="03562-104">In particular, checks for the proper drive separator syntax (the colon) were made more correct.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="03562-105">Auswirkungen</span><span class="sxs-lookup"><span data-stu-id="03562-105">Impact</span></span>  
 <span data-ttu-id="03562-106">Durch diese Änderungen werden einige URI-Pfade blockiert, die von den Methoden <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> und <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> zuvor unterstützt wurden.</span><span class="sxs-lookup"><span data-stu-id="03562-106">These changes block some URI paths the <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> and <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> methods previously supported.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="03562-107">Minderung</span><span class="sxs-lookup"><span data-stu-id="03562-107">Mitigation</span></span>  
 <span data-ttu-id="03562-108">Sie können folgendermaßen vorgehen, um das Problem von bisher gültigen Pfaden zu umgehen, die von den Methoden <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> und <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> nicht mehr unterstützt werden:</span><span class="sxs-lookup"><span data-stu-id="03562-108">To work around the problem of a previously acceptable path that is no longer supported by the <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> and <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> methods, you can do the following:</span></span>  
  
- <span data-ttu-id="03562-109">Entfernen Sie manuell das Schema aus einer URL.</span><span class="sxs-lookup"><span data-stu-id="03562-109">Manually remove the scheme from a URL.</span></span> <span data-ttu-id="03562-110">Entfernen Sie beispielsweise `file://` aus einer URL.</span><span class="sxs-lookup"><span data-stu-id="03562-110">For example, remove `file://` from a URL.</span></span>  
  
- <span data-ttu-id="03562-111">Übergeben Sie den URI an einen <xref:System.Uri>-Konstruktor, und rufen Sie den Wert der <xref:System.Uri.LocalPath%2A?displayProperty=nameWithType>-Eigenschaft ab.</span><span class="sxs-lookup"><span data-stu-id="03562-111">Pass the URI to a <xref:System.Uri> constructor,  and retrieve the value of the <xref:System.Uri.LocalPath%2A?displayProperty=nameWithType> property.</span></span>  
  
- <span data-ttu-id="03562-112">Entscheiden Sie sich gegen die Normalisierung des neuen Pfades, indem Sie den Schalter `Switch.System.IO.UseLegacyPathHandling`<xref:System.AppContext>auf `true` festlegen.</span><span class="sxs-lookup"><span data-stu-id="03562-112">Opt out of the new path normalization by setting the `Switch.System.IO.UseLegacyPathHandling`<xref:System.AppContext> switch to `true`.</span></span>  
  
    ```xml  
    <runtime>  
        <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />
    </runtime>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="03562-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="03562-113">See also</span></span>

- [<span data-ttu-id="03562-114">Anwendungskompatibilität</span><span class="sxs-lookup"><span data-stu-id="03562-114">Application compatibility</span></span>](application-compatibility.md)
