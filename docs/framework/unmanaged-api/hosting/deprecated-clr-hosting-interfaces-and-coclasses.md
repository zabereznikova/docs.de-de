---
title: Veraltete CLR-Hostingschnittstellen und Co-Klassen
ms.date: 03/30/2017
helpviewer_keywords:
- interfaces [.NET Framework hosting], version 1
- .NET Framework 1.1, hosting interfaces
- hosting interfaces [.NET Framework], version 1
- .NET Framework 1.0, hosting interfaces
ms.assetid: 7b3d2755-cbab-4160-bc69-eb85791e38c7
ms.openlocfilehash: 814f148b39045ad5454a23dfce8e7f9441f69041
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616410"
---
# <a name="deprecated-clr-hosting-interfaces-and-coclasses"></a><span data-ttu-id="d5c30-102">Veraltete CLR-Hostingschnittstellen und Co-Klassen</span><span class="sxs-lookup"><span data-stu-id="d5c30-102">Deprecated CLR Hosting Interfaces and Coclasses</span></span>
<span data-ttu-id="d5c30-103">In diesem Abschnitt werden die Schnittstellen beschrieben, mit denen nicht verwaltete Hosts die Common Language Runtime (CLR) in den .NET Framework Versionen 1,0 und 1,1 in Ihre Anwendungen integrieren können.</span><span class="sxs-lookup"><span data-stu-id="d5c30-103">This section describes the interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) in the .NET Framework versions 1.0 and 1.1 into their applications.</span></span> <span data-ttu-id="d5c30-104">Diese Schnittstellen bieten Methoden für einen Host zum Konfigurieren und Laden der Laufzeit in einen Prozess.</span><span class="sxs-lookup"><span data-stu-id="d5c30-104">These interfaces provide methods for a host to configure and load the runtime into a process.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d5c30-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="d5c30-105">In This Section</span></span>  
 <span data-ttu-id="d5c30-106">IAppDomainSetup</span><span class="sxs-lookup"><span data-stu-id="d5c30-106">IAppDomainSetup</span></span>  
 <span data-ttu-id="d5c30-107">Stellt Methoden bereit, mit denen der Host eine konfigurieren können <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="d5c30-107">Provides methods for the host to configure an <xref:System.AppDomain>.</span></span>  
  
 [<span data-ttu-id="d5c30-108">ICeeFileGen-Klasse</span><span class="sxs-lookup"><span data-stu-id="d5c30-108">ICeeFileGen Class</span></span>](iceefilegen-class.md)  
 <span data-ttu-id="d5c30-109">Veraltet Stellt Funktionen zum Erstellen einer nativen PE-Datei (Portable portable ausführbare Datei) bereit.</span><span class="sxs-lookup"><span data-stu-id="d5c30-109">(Deprecated) Provides functionality for creating a native portable executable (PE) file.</span></span>  
  
 [<span data-ttu-id="d5c30-110">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d5c30-110">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)  
 <span data-ttu-id="d5c30-111">Stellt Methoden für den Host zum Konfigurieren von CLR-Einstellungen bereit.</span><span class="sxs-lookup"><span data-stu-id="d5c30-111">Provides methods for the host to configure CLR settings.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d5c30-112">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="d5c30-112">Related Sections</span></span>  
 [<span data-ttu-id="d5c30-113">CLR-Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="d5c30-113">CLR Hosting Interfaces</span></span>](clr-hosting-interfaces.md)  
 <span data-ttu-id="d5c30-114">Enthält Themen, in denen die Hostingschnittstellen beschrieben werden, die mit dem .NET Framework Version 2,0 und höheren Versionen bereitgestellt werden</span><span class="sxs-lookup"><span data-stu-id="d5c30-114">Contains topics that describe the hosting interfaces provided with the .NET Framework version 2.0 and later versions.</span></span>
