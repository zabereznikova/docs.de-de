---
title: "In .NET Framework 4 und 4.5 hinzugefügte CLR-Hostingschnittstellen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- hosting interfaces [.NET Framework], version 4
- .NET Framework 4, hosting interfaces
- interfaces [.NET Framework hosting], version 4
ms.assetid: f6af6116-f5b0-4bda-a276-fffdba70893d
caps.latest.revision: "26"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 65d80734bfbe16c8b5052f8de1e4c6280b663707
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="clr-hosting-interfaces-added-in-the-net-framework-4-and-45"></a><span data-ttu-id="b8cd7-102">In .NET Framework 4 und 4.5 hinzugefügte CLR-Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="b8cd7-102">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>
<span data-ttu-id="b8cd7-103">Dieser Abschnitt beschreibt die Schnittstellen, die nicht verwaltete Hosts können Sie integrieren die common Language Runtime (CLR) in der [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], und höheren Versionen in ihre Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="b8cd7-103">This section describes interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], and later versions into their applications.</span></span> <span data-ttu-id="b8cd7-104">Diese Schnittstellen bieten Methoden für einen Host zu konfigurieren und die Common Language Runtime in einen Prozess zu laden.</span><span class="sxs-lookup"><span data-stu-id="b8cd7-104">These interfaces provide methods for a host to configure and load the runtime into a process.</span></span>  
  
 <span data-ttu-id="b8cd7-105">Beginnend mit der [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)], alle hosting Schnittstellen haben die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="b8cd7-105">Starting with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)], all hosting interfaces have the following characteristics:</span></span>  
  
-   <span data-ttu-id="b8cd7-106">Sie verwenden die Verwaltung der Objektlebensdauer (`AddRef` und `Release`), für die Kapselung (implizite Kontext) und `QueryInterface` aus COM</span><span class="sxs-lookup"><span data-stu-id="b8cd7-106">They use lifetime management (`AddRef` and `Release`), encapsulation (implicit context) and `QueryInterface` from COM.</span></span>  
  
-   <span data-ttu-id="b8cd7-107">Gibt es keine nicht-COM-Typen wie `BSTR`, `SAFEARRAY`, oder `VARIANT`.</span><span class="sxs-lookup"><span data-stu-id="b8cd7-107">There do not use COM types such as `BSTR`, `SAFEARRAY`, or `VARIANT`.</span></span>  
  
-   <span data-ttu-id="b8cd7-108">Es sind keine Modelle Apartment, Aggregation oder Registrierung die Aktivierung, mit denen die [CoCreateInstance-Funktion](http://go.microsoft.com/fwlink/?LinkId=142894).</span><span class="sxs-lookup"><span data-stu-id="b8cd7-108">There are no apartment models, aggregation, or registry activation that use the [CoCreateInstance function](http://go.microsoft.com/fwlink/?LinkId=142894).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b8cd7-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="b8cd7-109">In This Section</span></span>  
 [<span data-ttu-id="b8cd7-110">ICLRAppDomainResourceMonitor-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b8cd7-110">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)  
 <span data-ttu-id="b8cd7-111">Enthält Methoden, die einer Anwendungsdomäne Arbeitsspeicher und CPU-Auslastung zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="b8cd7-111">Provides methods that inspect an application domain's memory and CPU usage.</span></span>  
  
 [<span data-ttu-id="b8cd7-112">ICLRDomainManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b8cd7-112">ICLRDomainManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)  
 <span data-ttu-id="b8cd7-113">Ermöglicht es dem Host den Anwendungsdomänen-Manager an, der die Standardanwendungsdomäne initialisiert werden, sowie an Initialisierungseigenschaften verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b8cd7-113">Enables the host to specify the application domain manager that will be used to initialize the default application domain, and to specify initialization properties.</span></span>  
  
 [<span data-ttu-id="b8cd7-114">ICLRGCManager2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b8cd7-114">ICLRGCManager2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md)  
 <span data-ttu-id="b8cd7-115">Stellt die [SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) Methode, die einen Host für die Größe der Garbage Collection-Segment und die maximale Größe der der Garbage Collection-System Generation 0 Werte größer als festzulegen ermöglicht `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="b8cd7-115">Provides the [SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) method, which enables a host to set the size of the garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than `DWORD`.</span></span>  
  
 [<span data-ttu-id="b8cd7-116">ICLRMetaHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b8cd7-116">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 <span data-ttu-id="b8cd7-117">Enthält Methoden, die eine bestimmte Version der CLR zurückgeben, alle installierten clrs, Listen Sie alle in-Process-Laufzeiten, die Aktivierungsschnittstelle zurückgeben und ermitteln die CLR-Version verwendet, um eine Assembly zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="b8cd7-117">Provides methods that return a specific version of the CLR, list all installed CLRs, list all in-process runtimes, return the activation interface, and discover the CLR version used to compile an assembly.</span></span>  
  
 [<span data-ttu-id="b8cd7-118">ICLRMetaHostPolicy-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b8cd7-118">ICLRMetaHostPolicy Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md)  
 <span data-ttu-id="b8cd7-119">Stellt die [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) Methode, die eine CLR-Schnittstelle bereitstellt, anhand von Kriterien, die verwaltete Assembly, die Version und die Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="b8cd7-119">Provides the [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method that provides a CLR interface based on policy criteria, managed assembly, version, and configuration file.</span></span>  
  
 [<span data-ttu-id="b8cd7-120">ICLRRuntimeInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b8cd7-120">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 <span data-ttu-id="b8cd7-121">Enthält Methoden, die Informationen zu einer bestimmten Laufzeit, einschließlich der Version, Verzeichnis und Auslastungsstatus zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="b8cd7-121">Provides methods that return information about a specific runtime, including version, directory, and load status.</span></span>  
  
 [<span data-ttu-id="b8cd7-122">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b8cd7-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)  
 <span data-ttu-id="b8cd7-123">Stellt grundlegende globale statische Funktionen zum Signieren von Assemblys mit starken Namen an.</span><span class="sxs-lookup"><span data-stu-id="b8cd7-123">Provides basic global static functions for signing assemblies with strong names.</span></span> <span data-ttu-id="b8cd7-124">Alle der [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md) Methoden geben standard-COM-HRESULTs zurück.</span><span class="sxs-lookup"><span data-stu-id="b8cd7-124">All the [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md) methods return standard COM HRESULTs.</span></span>  
  
 [<span data-ttu-id="b8cd7-125">ICLRStrongName2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b8cd7-125">ICLRStrongName2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname2-interface.md)  
 <span data-ttu-id="b8cd7-126">Bietet die Möglichkeit zum Erstellen von starken Namen unter Verwendung der SHA-2-Gruppe des Secure Hash-Algorithmus (SHA-256, SHA-384 und SHA-512).</span><span class="sxs-lookup"><span data-stu-id="b8cd7-126">Provides the ability to create strong names using the SHA-2 group of Secure Hash Algorithms (SHA-256, SHA-384, and SHA-512).</span></span>  
  
 [<span data-ttu-id="b8cd7-127">ICLRTask2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b8cd7-127">ICLRTask2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)  
 <span data-ttu-id="b8cd7-128">Stellt die Funktionalität von der [ICLRTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md); darüber hinaus bietet Methoden, die es ermöglichen, Thread-Abbrüche um für den aktuellen Thread verzögert werden.</span><span class="sxs-lookup"><span data-stu-id="b8cd7-128">Provides all the functionality of the [ICLRTask Interface](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md); in addition, provides methods that allow thread aborts to be delayed on the current thread.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="b8cd7-129">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="b8cd7-129">Related Sections</span></span>  
 [<span data-ttu-id="b8cd7-130">Veraltete CLR-Hostingschnittstellen und Co-Klassen</span><span class="sxs-lookup"><span data-stu-id="b8cd7-130">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 <span data-ttu-id="b8cd7-131">Beschreibt die hosting-Schnittstellen mit den .NET Framework-Versionen 1.0 und 1.1 bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="b8cd7-131">Describes the hosting interfaces provided with the .NET Framework versions 1.0 and 1.1.</span></span>  
  
 [<span data-ttu-id="b8cd7-132">CLR-Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="b8cd7-132">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 <span data-ttu-id="b8cd7-133">Beschreibt die hosting-Schnittstellen mit den .NET Framework-Versionen 2.0, 3.0 und 3.5 bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="b8cd7-133">Describes the hosting interfaces provided with the .NET Framework versions 2.0, 3.0, and 3.5.</span></span>  
  
 [<span data-ttu-id="b8cd7-134">Hosting</span><span class="sxs-lookup"><span data-stu-id="b8cd7-134">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 <span data-ttu-id="b8cd7-135">Führt die in .NET Framework-hosting.</span><span class="sxs-lookup"><span data-stu-id="b8cd7-135">Introduces hosting in the .NET Framework.</span></span>
