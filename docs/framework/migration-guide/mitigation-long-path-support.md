---
title: "Entschärfung: Unterstützung für lange Pfade"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3cbe2d77-6e2c-4665-a6c5-7000b9ad6890
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 138e96c3d45b79ccf30f6a3d39f0af26a48c0117
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-long-path-support"></a><span data-ttu-id="46da2-102">Entschärfung: Unterstützung für lange Pfade</span><span class="sxs-lookup"><span data-stu-id="46da2-102">Mitigation: Long Path Support</span></span>
<span data-ttu-id="46da2-103">Von Apps für die Zielplattform [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] an lösen E/A-Methoden des Dateisystems nicht mehr automatisch eine <xref:System.IO.PathTooLongException> aus, wenn ein Pfad oder ein vollqualifizierter Dateiname 260 (oder `MAX_PATH`) Zeichen überschreitet.</span><span class="sxs-lookup"><span data-stu-id="46da2-103">Starting with apps that target the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)],  file system I/O methods not longer automatically throw a <xref:System.IO.PathTooLongException> if a path or fully qualified file name exceeds 260 (or `MAX_PATH`) characters.</span></span> <span data-ttu-id="46da2-104">Stattdessen werden lange Pfade mit bis zu 32.000 Zeichen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="46da2-104">Instead, long paths of up to 32K characters are supported.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="46da2-105">Auswirkungen</span><span class="sxs-lookup"><span data-stu-id="46da2-105">Impact</span></span>  
 <span data-ttu-id="46da2-106">Für die Zielplattform [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] neu kompilierte Anwendungen, die zuvor automatisch eine <xref:System.IO.PathTooLongException>-Ausnahme auslösten, wenn ein Pfad die Länge von 260 Zeichen überschritt, lösen jetzt nur unter den folgenden Bedingungen eine <xref:System.IO.PathTooLongException> aus:</span><span class="sxs-lookup"><span data-stu-id="46da2-106">Apps recompiled to target the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] and that previously threw a <xref:System.IO.PathTooLongException> automatically because a path exceeded 260 characters will now throw a <xref:System.IO.PathTooLongException> only under the following conditions:</span></span>  
  
-   <span data-ttu-id="46da2-107">Die Länge des Pfads umfasst mehr als <xref:System.Int16.MaxValue?displayProperty=fullName> (32.767) Zeichen.</span><span class="sxs-lookup"><span data-stu-id="46da2-107">The length of the path is greater than  <xref:System.Int16.MaxValue?displayProperty=fullName> (32,767) characters.</span></span>  
  
-   <span data-ttu-id="46da2-108">Das Betriebssystem gibt `COR_E_PATHTOOLONG` oder einen dazu äquivalenten Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="46da2-108">The operating system returns `COR_E_PATHTOOLONG` or its equivalent.</span></span>  
  
 <span data-ttu-id="46da2-109">Das Legacyverhalten für Apps mit der Zielplattform [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] und früher ist, dass die Runtime automatisch eine <xref:System.IO.PathTooLongException> auslöst, wenn ein Pfad die Länge von 260 Zeichen überschreitet.</span><span class="sxs-lookup"><span data-stu-id="46da2-109">The legacy behavior for apps that target the[!INCLUDE[net_v461](../../../includes/net-v461-md.md)] and earlier is that the runtime automatically throws a <xref:System.IO.PathTooLongException> whenever a path exceeds 260 characters.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="46da2-110">Problemumgehung</span><span class="sxs-lookup"><span data-stu-id="46da2-110">Mitigation</span></span>  
 <span data-ttu-id="46da2-111">Für Apps mit der Zielplattform [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] können Sie sich gegen die Unterstützung von langen Pfaden entscheiden, wenn sie nicht erwünscht ist, indem Sie Folgendes zum Abschnitt [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) Ihrer app.config-Datei hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="46da2-111">For apps that target the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], you can opt out of long path support if it is not desirable by adding the following to    to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your app.config file:</span></span>  
  
```xml  
<runtime>   
   <AppContextSwitchOverrides value="Switch.System.IO.BlockLongPaths=true" />   
</runtime>  
```  
  
 <span data-ttu-id="46da2-112">Anwendungen, die für frühere Versionen von .NET Framework vorgesehen sind, aber unter [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] oder höher ausgeführt werden, erlauben die Entscheidung für die Unterstützung von langen Pfaden, indem Folgendes zum Abschnitt [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) der app.config-Datei hinzugefügt wird:</span><span class="sxs-lookup"><span data-stu-id="46da2-112">For apps that target earlier versions of the .NET Framework but run on the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] or later., you can opt in to long path support by adding the following to    to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your app.config file:</span></span>  
  
```xml  
<runtime>   
   <AppContextSwitchOverrides value="Switch.System.IO.BlockLongPaths=false" />   
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="46da2-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="46da2-113">See Also</span></span>  
 [<span data-ttu-id="46da2-114">Neuausrichtungsänderungen</span><span class="sxs-lookup"><span data-stu-id="46da2-114">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-2.md)

