---
title: 'Entschärfung: Überprüfen von Pfaden auf Doppelpunkte'
ms.date: 03/30/2017
ms.assetid: a0bb52de-d279-419d-8f23-4b12d1a3f36e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c6799e36ec312bf857a12293dc0be15e9cc21f55
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64648456"
---
# <a name="mitigation-path-colon-checks"></a><span data-ttu-id="b7b79-102">Entschärfung: Überprüfen von Pfaden auf Doppelpunkte</span><span class="sxs-lookup"><span data-stu-id="b7b79-102">Mitigation: Path Colon Checks</span></span>
<span data-ttu-id="b7b79-103">Von Apps für die Zielplattform [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] an wurde eine Reihe von Änderungen vorgenommen, um zuvor nicht unterstützte Pfade zu unterstützen (im Hinblick auf Länge und Format).</span><span class="sxs-lookup"><span data-stu-id="b7b79-103">Starting with apps that target the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], a number of changes were made to support previously unsupported paths (both in terms of length and format).</span></span> <span data-ttu-id="b7b79-104">Insbesondere wurden Prüfungen auf ordnungsgemäße Syntax von Laufwerkstrennzeichen (den Doppelpunkt) strenger definiert.</span><span class="sxs-lookup"><span data-stu-id="b7b79-104">In particular, checks for the proper drive separator syntax (the colon) were made more correct.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="b7b79-105">Auswirkungen</span><span class="sxs-lookup"><span data-stu-id="b7b79-105">Impact</span></span>  
 <span data-ttu-id="b7b79-106">Durch diese Änderungen werden einige URI-Pfade blockiert, die von den Methoden <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> und <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> zuvor unterstützt wurden.</span><span class="sxs-lookup"><span data-stu-id="b7b79-106">These changes block some URI paths the <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> and <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> methods previously supported.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="b7b79-107">Minderung</span><span class="sxs-lookup"><span data-stu-id="b7b79-107">Mitigation</span></span>  
 <span data-ttu-id="b7b79-108">Sie können folgendermaßen vorgehen, um das Problem von bisher gültigen Pfaden zu umgehen, die von den Methoden <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> und <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> nicht mehr unterstützt werden:</span><span class="sxs-lookup"><span data-stu-id="b7b79-108">To work around the problem of a previously acceptable path that is no longer supported by the <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> and <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> methods, you can do the following:</span></span>  
  
- <span data-ttu-id="b7b79-109">Entfernen Sie manuell das Schema aus einer URL.</span><span class="sxs-lookup"><span data-stu-id="b7b79-109">Manually remove the scheme from a URL.</span></span> <span data-ttu-id="b7b79-110">Entfernen Sie beispielsweise `file://` aus einer URL.</span><span class="sxs-lookup"><span data-stu-id="b7b79-110">For example, remove `file://` from a URL.</span></span>  
  
- <span data-ttu-id="b7b79-111">Übergeben Sie den URI an einen <xref:System.Uri>-Konstruktor, und rufen Sie den Wert der <xref:System.Uri.LocalPath%2A?displayProperty=nameWithType>-Eigenschaft ab.</span><span class="sxs-lookup"><span data-stu-id="b7b79-111">Pass the URI to a <xref:System.Uri> constructor,  and retrieve the value of the <xref:System.Uri.LocalPath%2A?displayProperty=nameWithType> property.</span></span>  
  
- <span data-ttu-id="b7b79-112">Entscheiden Sie sich gegen die Normalisierung des neuen Pfades, indem Sie den Schalter `Switch.System.IO.UseLegacyPathHandling`<xref:System.AppContext>auf `true` festlegen.</span><span class="sxs-lookup"><span data-stu-id="b7b79-112">Opt out of the new path normalization by setting the `Switch.System.IO.UseLegacyPathHandling`<xref:System.AppContext> switch to `true`.</span></span>  
  
    ```xml  
    <runtime>  
        <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />    
    </runtime>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="b7b79-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b7b79-113">See also</span></span>

- [<span data-ttu-id="b7b79-114">Neuausrichtungsänderungen</span><span class="sxs-lookup"><span data-stu-id="b7b79-114">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-2.md)
