---
title: In .NET Framework 4 und 4.5 hinzugefügte CLR-Hostingschnittstellen
ms.date: 03/30/2017
helpviewer_keywords:
- hosting interfaces [.NET Framework], version 4
- .NET Framework 4, hosting interfaces
- interfaces [.NET Framework hosting], version 4
ms.assetid: f6af6116-f5b0-4bda-a276-fffdba70893d
ms.openlocfilehash: a524c0b0e01fbde95ce2341874511960b3e5738e
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616852"
---
# <a name="clr-hosting-interfaces-added-in-the-net-framework-4-and-45"></a><span data-ttu-id="08b4e-102">In .NET Framework 4 und 4.5 hinzugefügte CLR-Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="08b4e-102">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>
<span data-ttu-id="08b4e-103">In diesem Abschnitt werden die Schnittstellen beschrieben, mit denen nicht verwaltete Hosts die Common Language Runtime (CLR) in den .NET Framework 4, .NET Framework 4,5 und höheren Versionen in Ihre Anwendungen integrieren können.</span><span class="sxs-lookup"><span data-stu-id="08b4e-103">This section describes interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) in the .NET Framework 4, .NET Framework 4.5, and later versions into their applications.</span></span> <span data-ttu-id="08b4e-104">Diese Schnittstellen bieten Methoden für einen Host zum Konfigurieren und Laden der Laufzeit in einen Prozess.</span><span class="sxs-lookup"><span data-stu-id="08b4e-104">These interfaces provide methods for a host to configure and load the runtime into a process.</span></span>  
  
 <span data-ttu-id="08b4e-105">Beginnend mit dem .NET Framework 4 haben alle Hostingschnittstellen die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="08b4e-105">Starting with the .NET Framework 4, all hosting interfaces have the following characteristics:</span></span>  
  
- <span data-ttu-id="08b4e-106">Sie verwenden die Lebensdauer Verwaltung ( `AddRef` und `Release` ), Kapselung (impliziter Kontext) und `QueryInterface` com.</span><span class="sxs-lookup"><span data-stu-id="08b4e-106">They use lifetime management (`AddRef` and `Release`), encapsulation (implicit context) and `QueryInterface` from COM.</span></span>  
  
- <span data-ttu-id="08b4e-107">Sie verwenden keine COM-Typen wie z `BSTR` `SAFEARRAY` . b., oder `VARIANT` .</span><span class="sxs-lookup"><span data-stu-id="08b4e-107">They do not use COM types such as `BSTR`, `SAFEARRAY`, or `VARIANT`.</span></span>  
  
- <span data-ttu-id="08b4e-108">Es gibt keine Apartment Modelle, Aggregationen oder Registrierungs Aktivierung, die die [cokreateinzustance-Funktion](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance)verwenden.</span><span class="sxs-lookup"><span data-stu-id="08b4e-108">There are no apartment models, aggregation, or registry activation that use the [CoCreateInstance function](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="08b4e-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="08b4e-109">In This Section</span></span>  
 [<span data-ttu-id="08b4e-110">ICLRAppDomainResourceMonitor-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="08b4e-110">ICLRAppDomainResourceMonitor Interface</span></span>](iclrappdomainresourcemonitor-interface.md)  
 <span data-ttu-id="08b4e-111">Stellt Methoden bereit, die den Arbeitsspeicher und die CPU-Auslastung einer Anwendungsdomäne überprüfen.</span><span class="sxs-lookup"><span data-stu-id="08b4e-111">Provides methods that inspect an application domain's memory and CPU usage.</span></span>  
  
 [<span data-ttu-id="08b4e-112">ICLRDomainManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="08b4e-112">ICLRDomainManager Interface</span></span>](iclrdomainmanager-interface.md)  
 <span data-ttu-id="08b4e-113">Ermöglicht es dem Host, den Anwendungs Domänen-Manager anzugeben, der verwendet wird, um die Standard Anwendungsdomäne zu initialisieren und Initialisierungs Eigenschaften anzugeben.</span><span class="sxs-lookup"><span data-stu-id="08b4e-113">Enables the host to specify the application domain manager that will be used to initialize the default application domain, and to specify initialization properties.</span></span>  
  
 [<span data-ttu-id="08b4e-114">ICLRGCManager2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="08b4e-114">ICLRGCManager2 Interface</span></span>](iclrgcmanager2-interface.md)  
 <span data-ttu-id="08b4e-115">Stellt die [setgcstartuplimitsex](iclrgcmanager2-setgcstartuplimitsex-method.md) -Methode bereit, die es einem Host ermöglicht, die Größe des Garbage Collection Segments und die maximale Größe der Generation 0 des Garbage Collection Systems auf Werte größer als festzulegen `DWORD` .</span><span class="sxs-lookup"><span data-stu-id="08b4e-115">Provides the [SetGCStartupLimitsEx](iclrgcmanager2-setgcstartuplimitsex-method.md) method, which enables a host to set the size of the garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than `DWORD`.</span></span>  
  
 [<span data-ttu-id="08b4e-116">ICLRMetaHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="08b4e-116">ICLRMetaHost Interface</span></span>](iclrmetahost-interface.md)  
 <span data-ttu-id="08b4e-117">Stellt Methoden bereit, die eine bestimmte Version der CLR zurückgeben, alle installierten clrs auflisten, alle in-Process-Runtimes auflisten, die Aktivierungs Schnittstelle zurückgeben und die CLR-Version ermitteln, die zum Kompilieren einer Assembly verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="08b4e-117">Provides methods that return a specific version of the CLR, list all installed CLRs, list all in-process runtimes, return the activation interface, and discover the CLR version used to compile an assembly.</span></span>  
  
 [<span data-ttu-id="08b4e-118">ICLRMetaHostPolicy-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="08b4e-118">ICLRMetaHostPolicy Interface</span></span>](iclrmetahostpolicy-interface.md)  
 <span data-ttu-id="08b4e-119">Stellt die [GetRequestedRuntime](iclrmetahostpolicy-getrequestedruntime-method.md) -Methode bereit, die eine CLR-Schnittstelle basierend auf Richtlinien Kriterien, der verwalteten Assembly, der Version und der Konfigurationsdatei bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="08b4e-119">Provides the [GetRequestedRuntime](iclrmetahostpolicy-getrequestedruntime-method.md) method that provides a CLR interface based on policy criteria, managed assembly, version, and configuration file.</span></span>  
  
 [<span data-ttu-id="08b4e-120">ICLRRuntimeInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="08b4e-120">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)  
 <span data-ttu-id="08b4e-121">Stellt Methoden bereit, die Informationen zu einer bestimmten Laufzeit, einschließlich Version, Verzeichnis und Ladestatus, zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="08b4e-121">Provides methods that return information about a specific runtime, including version, directory, and load status.</span></span>  
  
 [<span data-ttu-id="08b4e-122">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="08b4e-122">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)  
 <span data-ttu-id="08b4e-123">Stellt grundlegende globale statische Funktionen zum Signieren von Assemblys mit starken Namen bereit.</span><span class="sxs-lookup"><span data-stu-id="08b4e-123">Provides basic global static functions for signing assemblies with strong names.</span></span> <span data-ttu-id="08b4e-124">Alle [ICLRStrongName](iclrstrongname-interface.md) -Methoden geben Standard-com-HRESULTs zurück.</span><span class="sxs-lookup"><span data-stu-id="08b4e-124">All the [ICLRStrongName](iclrstrongname-interface.md) methods return standard COM HRESULTs.</span></span>  
  
 [<span data-ttu-id="08b4e-125">ICLRStrongName2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="08b4e-125">ICLRStrongName2 Interface</span></span>](iclrstrongname2-interface.md)  
 <span data-ttu-id="08b4e-126">Bietet die Möglichkeit, starke Namen mithilfe der SHA-2-Gruppe von sicheren Hash Algorithmen (SHA-256, SHA-384 und SHA-512) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="08b4e-126">Provides the ability to create strong names using the SHA-2 group of Secure Hash Algorithms (SHA-256, SHA-384, and SHA-512).</span></span>  
  
 [<span data-ttu-id="08b4e-127">ICLRTask2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="08b4e-127">ICLRTask2 Interface</span></span>](iclrtask2-interface.md)  
 <span data-ttu-id="08b4e-128">Stellt die gesamte Funktionalität der [ICLRTask-Schnittstelle](iclrtask-interface.md)bereit. Außerdem stellt Methoden bereit, mit denen Thread Abbrüche im aktuellen Thread verzögert werden können.</span><span class="sxs-lookup"><span data-stu-id="08b4e-128">Provides all the functionality of the [ICLRTask Interface](iclrtask-interface.md); in addition, provides methods that allow thread aborts to be delayed on the current thread.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="08b4e-129">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="08b4e-129">Related Sections</span></span>  
 [<span data-ttu-id="08b4e-130">Veraltete CLR-Hostingschnittstellen und Co-Klassen</span><span class="sxs-lookup"><span data-stu-id="08b4e-130">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](deprecated-clr-hosting-interfaces-and-coclasses.md)  
 <span data-ttu-id="08b4e-131">Beschreibt die Hostingschnittstellen, die mit den .NET Framework Versionen 1,0 und 1,1 bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="08b4e-131">Describes the hosting interfaces provided with the .NET Framework versions 1.0 and 1.1.</span></span>  
  
 [<span data-ttu-id="08b4e-132">CLR-Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="08b4e-132">CLR Hosting Interfaces</span></span>](clr-hosting-interfaces.md)  
 <span data-ttu-id="08b4e-133">Beschreibt die Hostingschnittstellen, die mit den .NET Framework Versionen 2,0, 3,0 und 3,5 bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="08b4e-133">Describes the hosting interfaces provided with the .NET Framework versions 2.0, 3.0, and 3.5.</span></span>  
  
 [<span data-ttu-id="08b4e-134">Hosting</span><span class="sxs-lookup"><span data-stu-id="08b4e-134">Hosting</span></span>](index.md)  
 <span data-ttu-id="08b4e-135">Führt das Hosting in der .NET Framework ein.</span><span class="sxs-lookup"><span data-stu-id="08b4e-135">Introduces hosting in the .NET Framework.</span></span>
