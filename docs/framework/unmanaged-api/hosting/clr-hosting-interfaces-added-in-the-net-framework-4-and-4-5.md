---
title: In .NET Framework 4 und 4.5 hinzugefügte CLR-Hostingschnittstellen
ms.date: 03/30/2017
helpviewer_keywords:
- hosting interfaces [.NET Framework], version 4
- .NET Framework 4, hosting interfaces
- interfaces [.NET Framework hosting], version 4
ms.assetid: f6af6116-f5b0-4bda-a276-fffdba70893d
ms.openlocfilehash: 8484b47549f83795778420048d610e2d1626d87b
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2020
ms.locfileid: "75899720"
---
# <a name="clr-hosting-interfaces-added-in-the-net-framework-4-and-45"></a><span data-ttu-id="29ce2-102">In .NET Framework 4 und 4.5 hinzugefügte CLR-Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="29ce2-102">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>
<span data-ttu-id="29ce2-103">In diesem Abschnitt werden die Schnittstellen beschrieben, mit denen nicht verwaltete Hosts die Common Language Runtime (CLR) in den .NET Framework 4, .NET Framework 4,5 und höheren Versionen in Ihre Anwendungen integrieren können.</span><span class="sxs-lookup"><span data-stu-id="29ce2-103">This section describes interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) in the .NET Framework 4, .NET Framework 4.5, and later versions into their applications.</span></span> <span data-ttu-id="29ce2-104">Diese Schnittstellen bieten Methoden für einen Host zum Konfigurieren und Laden der Laufzeit in einen Prozess.</span><span class="sxs-lookup"><span data-stu-id="29ce2-104">These interfaces provide methods for a host to configure and load the runtime into a process.</span></span>  
  
 <span data-ttu-id="29ce2-105">Beginnend mit dem .NET Framework 4 haben alle Hostingschnittstellen die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="29ce2-105">Starting with the .NET Framework 4, all hosting interfaces have the following characteristics:</span></span>  
  
- <span data-ttu-id="29ce2-106">Sie verwenden die Lebensdauer Verwaltung (`AddRef` und `Release`), Kapselung (impliziter Kontext) und `QueryInterface` von com.</span><span class="sxs-lookup"><span data-stu-id="29ce2-106">They use lifetime management (`AddRef` and `Release`), encapsulation (implicit context) and `QueryInterface` from COM.</span></span>  
  
- <span data-ttu-id="29ce2-107">Sie verwenden keine COM-Typen wie `BSTR`, `SAFEARRAY`oder `VARIANT`.</span><span class="sxs-lookup"><span data-stu-id="29ce2-107">They do not use COM types such as `BSTR`, `SAFEARRAY`, or `VARIANT`.</span></span>  
  
- <span data-ttu-id="29ce2-108">Es gibt keine Apartment Modelle, Aggregationen oder Registrierungs Aktivierung, die die [cokreateinzustance-Funktion](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance)verwenden.</span><span class="sxs-lookup"><span data-stu-id="29ce2-108">There are no apartment models, aggregation, or registry activation that use the [CoCreateInstance function](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="29ce2-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="29ce2-109">In This Section</span></span>  
 [<span data-ttu-id="29ce2-110">ICLRAppDomainResourceMonitor-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="29ce2-110">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)  
 <span data-ttu-id="29ce2-111">Stellt Methoden bereit, die den Arbeitsspeicher und die CPU-Auslastung einer Anwendungsdomäne überprüfen.</span><span class="sxs-lookup"><span data-stu-id="29ce2-111">Provides methods that inspect an application domain's memory and CPU usage.</span></span>  
  
 [<span data-ttu-id="29ce2-112">ICLRDomainManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="29ce2-112">ICLRDomainManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)  
 <span data-ttu-id="29ce2-113">Ermöglicht es dem Host, den Anwendungs Domänen-Manager anzugeben, der verwendet wird, um die Standard Anwendungsdomäne zu initialisieren und Initialisierungs Eigenschaften anzugeben.</span><span class="sxs-lookup"><span data-stu-id="29ce2-113">Enables the host to specify the application domain manager that will be used to initialize the default application domain, and to specify initialization properties.</span></span>  
  
 [<span data-ttu-id="29ce2-114">ICLRGCManager2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="29ce2-114">ICLRGCManager2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md)  
 <span data-ttu-id="29ce2-115">Stellt die [setgcstartuplimitsex](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) -Methode bereit, mit der ein Host die Größe des Garbage Collection Segments und die maximale Größe der Generation 0 des Garbage Collection Systems auf Werte festlegen kann, die größer als `DWORD`sind.</span><span class="sxs-lookup"><span data-stu-id="29ce2-115">Provides the [SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) method, which enables a host to set the size of the garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than `DWORD`.</span></span>  
  
 [<span data-ttu-id="29ce2-116">ICLRMetaHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="29ce2-116">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 <span data-ttu-id="29ce2-117">Stellt Methoden bereit, die eine bestimmte Version der CLR zurückgeben, alle installierten clrs auflisten, alle in-Process-Runtimes auflisten, die Aktivierungs Schnittstelle zurückgeben und die CLR-Version ermitteln, die zum Kompilieren einer Assembly verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="29ce2-117">Provides methods that return a specific version of the CLR, list all installed CLRs, list all in-process runtimes, return the activation interface, and discover the CLR version used to compile an assembly.</span></span>  
  
 [<span data-ttu-id="29ce2-118">ICLRMetaHostPolicy-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="29ce2-118">ICLRMetaHostPolicy Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md)  
 <span data-ttu-id="29ce2-119">Stellt die [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) -Methode bereit, die eine CLR-Schnittstelle basierend auf Richtlinien Kriterien, der verwalteten Assembly, der Version und der Konfigurationsdatei bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="29ce2-119">Provides the [GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method that provides a CLR interface based on policy criteria, managed assembly, version, and configuration file.</span></span>  
  
 [<span data-ttu-id="29ce2-120">ICLRRuntimeInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="29ce2-120">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 <span data-ttu-id="29ce2-121">Stellt Methoden bereit, die Informationen zu einer bestimmten Laufzeit, einschließlich Version, Verzeichnis und Ladestatus, zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="29ce2-121">Provides methods that return information about a specific runtime, including version, directory, and load status.</span></span>  
  
 [<span data-ttu-id="29ce2-122">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="29ce2-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)  
 <span data-ttu-id="29ce2-123">Stellt grundlegende globale statische Funktionen zum Signieren von Assemblys mit starken Namen bereit.</span><span class="sxs-lookup"><span data-stu-id="29ce2-123">Provides basic global static functions for signing assemblies with strong names.</span></span> <span data-ttu-id="29ce2-124">Alle [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md) -Methoden geben Standard-com-HRESULTs zurück.</span><span class="sxs-lookup"><span data-stu-id="29ce2-124">All the [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md) methods return standard COM HRESULTs.</span></span>  
  
 [<span data-ttu-id="29ce2-125">ICLRStrongName2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="29ce2-125">ICLRStrongName2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname2-interface.md)  
 <span data-ttu-id="29ce2-126">Bietet die Möglichkeit, starke Namen mithilfe der SHA-2-Gruppe von sicheren Hash Algorithmen (SHA-256, SHA-384 und SHA-512) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="29ce2-126">Provides the ability to create strong names using the SHA-2 group of Secure Hash Algorithms (SHA-256, SHA-384, and SHA-512).</span></span>  
  
 [<span data-ttu-id="29ce2-127">ICLRTask2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="29ce2-127">ICLRTask2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)  
 <span data-ttu-id="29ce2-128">Stellt die gesamte Funktionalität der [ICLRTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)bereit. Außerdem stellt Methoden bereit, mit denen Thread Abbrüche im aktuellen Thread verzögert werden können.</span><span class="sxs-lookup"><span data-stu-id="29ce2-128">Provides all the functionality of the [ICLRTask Interface](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md); in addition, provides methods that allow thread aborts to be delayed on the current thread.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="29ce2-129">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="29ce2-129">Related Sections</span></span>  
 [<span data-ttu-id="29ce2-130">Veraltete CLR-Hostingschnittstellen und Co-Klassen</span><span class="sxs-lookup"><span data-stu-id="29ce2-130">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 <span data-ttu-id="29ce2-131">Beschreibt die Hostingschnittstellen, die mit den .NET Framework Versionen 1,0 und 1,1 bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="29ce2-131">Describes the hosting interfaces provided with the .NET Framework versions 1.0 and 1.1.</span></span>  
  
 [<span data-ttu-id="29ce2-132">CLR-Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="29ce2-132">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 <span data-ttu-id="29ce2-133">Beschreibt die Hostingschnittstellen, die mit den .NET Framework Versionen 2,0, 3,0 und 3,5 bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="29ce2-133">Describes the hosting interfaces provided with the .NET Framework versions 2.0, 3.0, and 3.5.</span></span>  
  
 [<span data-ttu-id="29ce2-134">Hosting</span><span class="sxs-lookup"><span data-stu-id="29ce2-134">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 <span data-ttu-id="29ce2-135">Führt das Hosting in der .NET Framework ein.</span><span class="sxs-lookup"><span data-stu-id="29ce2-135">Introduces hosting in the .NET Framework.</span></span>
