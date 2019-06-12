---
title: 'Entschärfung: Überprüfen von Pfaden auf Doppelpunkte'
ms.date: 03/30/2017
ms.assetid: a0bb52de-d279-419d-8f23-4b12d1a3f36e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e41a51dcdf243091d3962278f1a59a85a2722894
ms.sourcegitcommit: 26f4a7697c32978f6a328c89dc4ea87034065989
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/28/2019
ms.locfileid: "66251134"
---
# <a name="mitigation-path-colon-checks"></a><span data-ttu-id="01b07-102">Entschärfung: Überprüfen von Pfaden auf Doppelpunkte</span><span class="sxs-lookup"><span data-stu-id="01b07-102">Mitigation: Path Colon Checks</span></span>
<span data-ttu-id="01b07-103">Für Apps, die gezielt .NET Framework 4.6.2 und höhere Versionen verwenden, wurde eine Reihe von Änderungen vorgenommen, um zuvor nicht unterstützte Pfade zu unterstützen (im Hinblick auf Länge und Format).</span><span class="sxs-lookup"><span data-stu-id="01b07-103">Starting with apps that target the .NET Framework 4.6.2, a number of changes were made to support previously unsupported paths (both in terms of length and format).</span></span> <span data-ttu-id="01b07-104">Insbesondere wurden Prüfungen auf ordnungsgemäße Syntax von Laufwerkstrennzeichen (den Doppelpunkt) strenger definiert.</span><span class="sxs-lookup"><span data-stu-id="01b07-104">In particular, checks for the proper drive separator syntax (the colon) were made more correct.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="01b07-105">Auswirkungen</span><span class="sxs-lookup"><span data-stu-id="01b07-105">Impact</span></span>  
 <span data-ttu-id="01b07-106">Durch diese Änderungen werden einige URI-Pfade blockiert, die von den Methoden <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> und <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> zuvor unterstützt wurden.</span><span class="sxs-lookup"><span data-stu-id="01b07-106">These changes block some URI paths the <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> and <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> methods previously supported.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="01b07-107">Minderung</span><span class="sxs-lookup"><span data-stu-id="01b07-107">Mitigation</span></span>  
 <span data-ttu-id="01b07-108">Sie können folgendermaßen vorgehen, um das Problem von bisher gültigen Pfaden zu umgehen, die von den Methoden <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> und <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> nicht mehr unterstützt werden:</span><span class="sxs-lookup"><span data-stu-id="01b07-108">To work around the problem of a previously acceptable path that is no longer supported by the <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=nameWithType> and <xref:System.IO.Path.GetPathRoot%2A?displayProperty=nameWithType> methods, you can do the following:</span></span>  
  
- <span data-ttu-id="01b07-109">Entfernen Sie manuell das Schema aus einer URL.</span><span class="sxs-lookup"><span data-stu-id="01b07-109">Manually remove the scheme from a URL.</span></span> <span data-ttu-id="01b07-110">Entfernen Sie beispielsweise `file://` aus einer URL.</span><span class="sxs-lookup"><span data-stu-id="01b07-110">For example, remove `file://` from a URL.</span></span>  
  
- <span data-ttu-id="01b07-111">Übergeben Sie den URI an einen <xref:System.Uri>-Konstruktor, und rufen Sie den Wert der <xref:System.Uri.LocalPath%2A?displayProperty=nameWithType>-Eigenschaft ab.</span><span class="sxs-lookup"><span data-stu-id="01b07-111">Pass the URI to a <xref:System.Uri> constructor,  and retrieve the value of the <xref:System.Uri.LocalPath%2A?displayProperty=nameWithType> property.</span></span>  
  
- <span data-ttu-id="01b07-112">Entscheiden Sie sich gegen die Normalisierung des neuen Pfades, indem Sie den Schalter `Switch.System.IO.UseLegacyPathHandling`<xref:System.AppContext>auf `true` festlegen.</span><span class="sxs-lookup"><span data-stu-id="01b07-112">Opt out of the new path normalization by setting the `Switch.System.IO.UseLegacyPathHandling`<xref:System.AppContext> switch to `true`.</span></span>  
  
    ```xml  
    <runtime>  
        <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />    
    </runtime>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="01b07-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="01b07-113">See also</span></span>

- [<span data-ttu-id="01b07-114">Neuausrichtungsänderungen</span><span class="sxs-lookup"><span data-stu-id="01b07-114">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-2.md)
