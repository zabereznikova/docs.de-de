---
title: "MEF für .NET für Windows Store-Apps"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7667770e-d163-4ad6-a303-085cf73db2f2
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7f427656f9b385214db5b3bd26c4addb1122b35a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="mef-for-net-for-windows-store-apps"></a><span data-ttu-id="efdd4-102">MEF für .NET für Windows Store-Apps</span><span class="sxs-lookup"><span data-stu-id="efdd4-102">MEF for .NET for Windows Store Apps</span></span>
<span data-ttu-id="efdd4-103"><xref:System.Composition?displayProperty=nameWithType>und die dazugehörigen untergeordneten Namespaces enthalten Typen zum Entwickeln von erweiterbaren [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps mit Managed Extensibility Framework (MEF).</span><span class="sxs-lookup"><span data-stu-id="efdd4-103"><xref:System.Composition?displayProperty=nameWithType> and its child namespaces contain types for developing extensible [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps with Managed Extensibility Framework (MEF).</span></span> <span data-ttu-id="efdd4-104">Diese Namespaces sind Teil der [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] Teilmenge für den [!INCLUDE[win8](../../../includes/win8-md.md)] Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="efdd4-104">These namespaces are part of the [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] subset for the [!INCLUDE[win8](../../../includes/win8-md.md)] operating system.</span></span>  
  
 <span data-ttu-id="efdd4-105">Diese Namespaces sind nicht Teil der Kernklassenbibliothek, die mit .NET Framework verteilt wird.</span><span class="sxs-lookup"><span data-stu-id="efdd4-105">These namespaces are not part of the core class library distributed with the .NET Framework.</span></span> <span data-ttu-id="efdd4-106">Um diese Namespaces zu installieren, öffnen Sie das Projekt in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], wählen Sie **NuGet-Pakete verwalten** aus der **Projekt** Menü, und suchen Sie online nach dem Microsoft.Composition-Paket.</span><span class="sxs-lookup"><span data-stu-id="efdd4-106">To install these namespaces, open your project in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], choose **Manage NuGet Packages** from the **Project** menu, and search online for the Microsoft.Composition package.</span></span>  
  
-   <span data-ttu-id="efdd4-107"><xref:System.Composition?displayProperty=nameWithType>enthält Klassen, die bilden das Kernstück MEF für [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps.</span><span class="sxs-lookup"><span data-stu-id="efdd4-107"><xref:System.Composition?displayProperty=nameWithType> provides classes that constitute the core MEF for [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] apps.</span></span>  
  
-   <span data-ttu-id="efdd4-108"><xref:System.Composition.Convention?displayProperty=nameWithType>enthält Typen, die mithilfe von MEF mit einem konventionsbasierten Konfigurationsmodell unterstützen.</span><span class="sxs-lookup"><span data-stu-id="efdd4-108"><xref:System.Composition.Convention?displayProperty=nameWithType> provides types that support using MEF with a convention-based configuration model.</span></span>  
  
-   <span data-ttu-id="efdd4-109"><xref:System.Composition.Hosting?displayProperty=nameWithType>Stellt MEF-Typen, die für Entwickler von hostanwendungen hilfreich sind.</span><span class="sxs-lookup"><span data-stu-id="efdd4-109"><xref:System.Composition.Hosting?displayProperty=nameWithType> provides MEF types that are useful to developers of host applications.</span></span>  
  
-   <span data-ttu-id="efdd4-110"><xref:System.Composition.Hosting.Core?displayProperty=nameWithType>Stellt MEF-Typen, die intern vom Kompositionsmodul verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="efdd4-110"><xref:System.Composition.Hosting.Core?displayProperty=nameWithType> provides MEF types used internally by the composition engine.</span></span>  
  
 <span data-ttu-id="efdd4-111">Weitere Informationen zu [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] und eine Liste der Namespaces und Typen, die es enthält, finden Sie unter [.NET für Windows Store-apps – Übersicht](http://go.microsoft.com/fwlink/p/?LinkID=238312) im Windows Developer Center.</span><span class="sxs-lookup"><span data-stu-id="efdd4-111">For more information about [!INCLUDE[net_win8_profile](../../../includes/net-win8-profile-md.md)] and a list of namespaces and types that it contains, see [.NET for Windows Store apps overview](http://go.microsoft.com/fwlink/p/?LinkID=238312) in the Windows Dev Center.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efdd4-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="efdd4-112">See Also</span></span>  
 [<span data-ttu-id="efdd4-113">.NET für Windows Store-apps – Übersicht</span><span class="sxs-lookup"><span data-stu-id="efdd4-113">.NET for Windows Store apps overview</span></span>](http://go.microsoft.com/fwlink/p/?LinkID=238312)  
 [<span data-ttu-id="efdd4-114">.NET für Windows Store-Apps – unterstützte APIs</span><span class="sxs-lookup"><span data-stu-id="efdd4-114">.NET for Windows Store apps – supported APIs</span></span>](http://go.microsoft.com/fwlink/p/?LinkID=247912)  
 [<span data-ttu-id="efdd4-115">Managed Extensibility Framework (MEF)</span><span class="sxs-lookup"><span data-stu-id="efdd4-115">Managed Extensibility Framework (MEF)</span></span>](../../../docs/framework/mef/index.md)
