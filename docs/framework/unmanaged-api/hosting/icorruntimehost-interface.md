---
title: ICorRuntimeHost-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost
helpviewer_keywords:
- ICorRuntimeHost interface [.NET Framework hosting]
ms.assetid: 4369533d-7834-4497-bc37-bfea0ad737b1
topic_type:
- apiref
ms.openlocfilehash: 9fcb5e189af9f72de7635aad550a5e8ab5522dbd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720619"
---
# <a name="icorruntimehost-interface"></a><span data-ttu-id="50854-102">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="50854-102">ICorRuntimeHost Interface</span></span>

<span data-ttu-id="50854-103">Stellt Methoden bereit, die es dem Host ermöglichen, die Common Language Runtime (CLR) explizit zu starten und zu starten, um Anwendungs Domänen zu erstellen und zu konfigurieren, um auf die Standard Domäne zuzugreifen und um alle Domänen aufzulisten, die im Prozess ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="50854-103">Provides methods that enable the host to start and stop the common language runtime (CLR) explicitly, to create and configure application domains, to access the default domain, and to enumerate all domains running in the process.</span></span>  
  
 <span data-ttu-id="50854-104">In der .NET Framework Version 2,0 wird diese Schnittstelle von [ICLRRuntimeHost](iclrruntimehost-interface.md)ersetzt.</span><span class="sxs-lookup"><span data-stu-id="50854-104">In the .NET Framework version 2.0, this interface is superceded by [ICLRRuntimeHost](iclrruntimehost-interface.md).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="50854-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="50854-105">Methods</span></span>  
  
|<span data-ttu-id="50854-106">Methode</span><span class="sxs-lookup"><span data-stu-id="50854-106">Method</span></span>|<span data-ttu-id="50854-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="50854-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="50854-108">CloseEnum-Methode</span><span class="sxs-lookup"><span data-stu-id="50854-108">CloseEnum Method</span></span>](icorruntimehost-closeenum-method.md)|<span data-ttu-id="50854-109">Setzt einen Domänen Enumerator auf den Anfang der Domänen Liste zurück.</span><span class="sxs-lookup"><span data-stu-id="50854-109">Resets a domain enumerator back to the beginning of the domain list.</span></span>|  
|[<span data-ttu-id="50854-110">CreateDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="50854-110">CreateDomain Method</span></span>](icorruntimehost-createdomain-method.md)|<span data-ttu-id="50854-111">Erstellt eine Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="50854-111">Creates an application domain.</span></span> <span data-ttu-id="50854-112">Der Aufrufer erhält einen Schnittstellen Zeiger vom Typ <xref:System._AppDomain> auf eine Instanz vom Typ <xref:System.AppDomain?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="50854-112">The caller receives an interface pointer of type <xref:System._AppDomain> to an instance of type <xref:System.AppDomain?displayProperty=nameWithType>.</span></span>|  
|[<span data-ttu-id="50854-113">CreateDomainEx-Methode</span><span class="sxs-lookup"><span data-stu-id="50854-113">CreateDomainEx Method</span></span>](icorruntimehost-createdomainex-method.md)|<span data-ttu-id="50854-114">Erstellt eine Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="50854-114">Creates an application domain.</span></span> <span data-ttu-id="50854-115">Diese Methode ermöglicht es dem Aufrufer, eine IAppDomainSetup-Instanz zu übergeben, um zusätzliche Funktionen der zurückgegebenen Instanz zu konfigurieren <xref:System._AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="50854-115">This method allows the caller to pass an IAppDomainSetup instance to configure additional features of the returned <xref:System._AppDomain> instance.</span></span>|  
|[<span data-ttu-id="50854-116">CreateDomainSetup-Methode</span><span class="sxs-lookup"><span data-stu-id="50854-116">CreateDomainSetup Method</span></span>](icorruntimehost-createdomainsetup-method.md)|<span data-ttu-id="50854-117">Ruft einen Schnittstellen Zeiger vom Typ `IAppDomainSetup` auf eine- <xref:System.AppDomainSetup> Instanz ab.</span><span class="sxs-lookup"><span data-stu-id="50854-117">Gets an interface pointer of type `IAppDomainSetup` to an <xref:System.AppDomainSetup> instance.</span></span> <span data-ttu-id="50854-118">`IAppDomainSetup` stellt Methoden bereit, um Aspekte einer Anwendungsdomäne vor der Erstellung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="50854-118">`IAppDomainSetup` provides methods to configure aspects of an application domain before it is created.</span></span>|  
|[<span data-ttu-id="50854-119">CreateEvidence-Methode</span><span class="sxs-lookup"><span data-stu-id="50854-119">CreateEvidence Method</span></span>](icorruntimehost-createevidence-method.md)|<span data-ttu-id="50854-120">Ruft einen Schnittstellen Zeiger vom Typ ab <xref:System.Security.Principal.IIdentity> , der dem Host das Erstellen von Sicherheits beweisen ermöglicht, die an " [kreatedomain](icorruntimehost-createdomain-method.md) " oder " [kreatedomainex](icorruntimehost-createdomainex-method.md)" übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="50854-120">Gets an interface pointer of type <xref:System.Security.Principal.IIdentity>, which allows the host to create security evidence to pass to [CreateDomain](icorruntimehost-createdomain-method.md) or [CreateDomainEx](icorruntimehost-createdomainex-method.md).</span></span>|  
|[<span data-ttu-id="50854-121">CreateLogicalThreadState-Methode</span><span class="sxs-lookup"><span data-stu-id="50854-121">CreateLogicalThreadState Method</span></span>](icorruntimehost-createlogicalthreadstate-method.md)|<span data-ttu-id="50854-122">Darf nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="50854-122">Do not use.</span></span>|  
|[<span data-ttu-id="50854-123">CurrentDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="50854-123">CurrentDomain Method</span></span>](icorruntimehost-currentdomain-method.md)|<span data-ttu-id="50854-124">Ruft einen Schnittstellen Zeiger vom Typ ab <xref:System._AppDomain> , der die Domäne darstellt, die für den aktuellen Thread geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="50854-124">Gets an interface pointer of type <xref:System._AppDomain> that represents the domain loaded on the current thread.</span></span>|  
|[<span data-ttu-id="50854-125">DeleteLogicalThreadState-Methode</span><span class="sxs-lookup"><span data-stu-id="50854-125">DeleteLogicalThreadState Method</span></span>](icorruntimehost-deletelogicalthreadstate-method.md)|<span data-ttu-id="50854-126">Darf nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="50854-126">Do not use.</span></span>|  
|[<span data-ttu-id="50854-127">EnumDomains-Methode</span><span class="sxs-lookup"><span data-stu-id="50854-127">EnumDomains Method</span></span>](icorruntimehost-enumdomains-method.md)|<span data-ttu-id="50854-128">Ruft einen Enumerator für die Domänen im aktuellen Prozess ab.</span><span class="sxs-lookup"><span data-stu-id="50854-128">Gets an enumerator for the domains in the current process.</span></span>|  
|[<span data-ttu-id="50854-129">GetConfiguration-Methode</span><span class="sxs-lookup"><span data-stu-id="50854-129">GetConfiguration Method</span></span>](icorruntimehost-getconfiguration-method.md)|<span data-ttu-id="50854-130">Ruft ein Objekt ab, mit dem der Host die Rückruf Konfiguration der CLR angeben kann.</span><span class="sxs-lookup"><span data-stu-id="50854-130">Gets an object that allows the host to specify the callback configuration of the CLR.</span></span>|  
|[<span data-ttu-id="50854-131">GetDefaultDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="50854-131">GetDefaultDomain Method</span></span>](icorruntimehost-getdefaultdomain-method.md)|<span data-ttu-id="50854-132">Ruft einen Schnittstellen Zeiger vom Typ ab <xref:System._AppDomain> , der die Standard Domäne für den aktuellen Prozess darstellt.</span><span class="sxs-lookup"><span data-stu-id="50854-132">Gets an interface pointer of type <xref:System._AppDomain> that represents the default domain for the current process.</span></span>|  
|[<span data-ttu-id="50854-133">LocksHeldByLogicalThread-Methode</span><span class="sxs-lookup"><span data-stu-id="50854-133">LocksHeldByLogicalThread Method</span></span>](icorruntimehost-locksheldbylogicalthread-method.md)|<span data-ttu-id="50854-134">Darf nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="50854-134">Do not use.</span></span>|  
|[<span data-ttu-id="50854-135">MapFile-Methode</span><span class="sxs-lookup"><span data-stu-id="50854-135">MapFile Method</span></span>](icorruntimehost-mapfile-method.md)|<span data-ttu-id="50854-136">Ordnet die angegebene Datei dem Arbeitsspeicher zu.</span><span class="sxs-lookup"><span data-stu-id="50854-136">Maps the specified file into memory.</span></span> <span data-ttu-id="50854-137">Diese Methode ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="50854-137">This method is obsolete.</span></span>|  
|[<span data-ttu-id="50854-138">NextDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="50854-138">NextDomain Method</span></span>](icorruntimehost-nextdomain-method.md)|<span data-ttu-id="50854-139">Ruft einen Schnittstellen Zeiger auf die nächste Domäne in der-Enumeration ab.</span><span class="sxs-lookup"><span data-stu-id="50854-139">Gets an interface pointer to the next domain in the enumeration.</span></span>|  
|[<span data-ttu-id="50854-140">Start-Methode</span><span class="sxs-lookup"><span data-stu-id="50854-140">Start Method</span></span>](icorruntimehost-start-method.md)|<span data-ttu-id="50854-141">Startet die CLR.</span><span class="sxs-lookup"><span data-stu-id="50854-141">Starts the CLR.</span></span>|  
|[<span data-ttu-id="50854-142">Stop-Methode</span><span class="sxs-lookup"><span data-stu-id="50854-142">Stop Method</span></span>](icorruntimehost-stop-method.md)|<span data-ttu-id="50854-143">Beendet die Ausführung von Code in der Laufzeit für den aktuellen Prozess.</span><span class="sxs-lookup"><span data-stu-id="50854-143">Stops the execution of code in the runtime for the current process.</span></span>|  
|[<span data-ttu-id="50854-144">SwitchInLogicalThreadState-Methode</span><span class="sxs-lookup"><span data-stu-id="50854-144">SwitchInLogicalThreadState Method</span></span>](icorruntimehost-switchinlogicalthreadstate-method.md)|<span data-ttu-id="50854-145">Darf nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="50854-145">Do not use.</span></span>|  
|[<span data-ttu-id="50854-146">SwitchOutLogicalThreadState-Methode</span><span class="sxs-lookup"><span data-stu-id="50854-146">SwitchOutLogicalThreadState Method</span></span>](icorruntimehost-switchoutlogicalthreadstate-method.md)|<span data-ttu-id="50854-147">Darf nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="50854-147">Do not use.</span></span>|  
|[<span data-ttu-id="50854-148">UnloadDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="50854-148">UnloadDomain Method</span></span>](icorruntimehost-unloaddomain-method.md)|<span data-ttu-id="50854-149">Entlädt die angegebene Anwendungsdomäne aus dem aktuellen Prozess.</span><span class="sxs-lookup"><span data-stu-id="50854-149">Unloads the specified application domain from the current process.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="50854-150">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="50854-150">Requirements</span></span>  

 <span data-ttu-id="50854-151">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50854-151">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50854-152">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="50854-152">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="50854-153">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="50854-153">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="50854-154">**.NET Framework Versionen:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="50854-154">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50854-155">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="50854-155">See also</span></span>

- <xref:System.AppDomain>
- [<span data-ttu-id="50854-156">Hosting</span><span class="sxs-lookup"><span data-stu-id="50854-156">Hosting</span></span>](index.md)
- [<span data-ttu-id="50854-157">ICLRRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="50854-157">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
- <span data-ttu-id="50854-158">[Laufzeithosts](/previous-versions/dotnet/netframework-4.0/a51xd4ze(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="50854-158">[Runtime Hosts](/previous-versions/dotnet/netframework-4.0/a51xd4ze(v=vs.100))</span></span>
- [<span data-ttu-id="50854-159">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="50854-159">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="50854-160">CorRuntimeHost-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="50854-160">CorRuntimeHost Coclass</span></span>](corruntimehost-coclass.md)
