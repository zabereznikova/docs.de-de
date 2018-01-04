---
title: IAppDomainSetup-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAppDomainSetup
api_location: mscoree.dll
api_type: COM
f1_keywords: IAppDomainSetup
helpviewer_keywords: IAppDomainSetup interface [.NET Framework hosting]
ms.assetid: 1844da85-c031-40bf-bea4-1a3d12a36c8c
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9db1b787015231b3d9053d4ed316cb70c5db96ec
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iappdomainsetup-interface"></a><span data-ttu-id="eba6f-102">IAppDomainSetup-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="eba6f-102">IAppDomainSetup Interface</span></span>
<span data-ttu-id="eba6f-103">Enthält Eigenschaften, mit denen den Host so konfigurieren Sie eine <xref:System.AppDomain?displayProperty=nameWithType> Typ vor dem Aufruf der [ICorRuntimeHost:: CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) Methode, um ihn zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="eba6f-103">Provides properties that allow the host to configure an <xref:System.AppDomain?displayProperty=nameWithType> type before calling the [ICorRuntimeHost::CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) method to create it.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="eba6f-104">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="eba6f-104">Properties</span></span>  
  
|<span data-ttu-id="eba6f-105">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="eba6f-105">Property</span></span>|<span data-ttu-id="eba6f-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eba6f-106">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.AppDomainSetup.ApplicationBase%2A>|<span data-ttu-id="eba6f-107">Ruft ab oder legt den Namen des Verzeichnisses, das die Anwendung enthält.</span><span class="sxs-lookup"><span data-stu-id="eba6f-107">Gets or sets the name of the directory that contains the application.</span></span>|  
|<xref:System.AppDomainSetup.ApplicationName%2A>|<span data-ttu-id="eba6f-108">Ruft den Namen der Anwendung ab oder legt diesen fest.</span><span class="sxs-lookup"><span data-stu-id="eba6f-108">Gets or sets the name of the application.</span></span>|  
|<xref:System.AppDomainSetup.CachePath%2A>|<span data-ttu-id="eba6f-109">Ruft ab oder legt den Namen eines Bereichs bestimmte an die Anwendung sind, in denen Dateien Schattenkopie.</span><span class="sxs-lookup"><span data-stu-id="eba6f-109">Gets or sets the name of an area specific to the application where files are shadow-copied.</span></span>|  
|<xref:System.AppDomainSetup.ConfigurationFile%2A>|<span data-ttu-id="eba6f-110">Ruft ab oder legt den Namen der Konfigurationsdatei für eine Anwendung fest.</span><span class="sxs-lookup"><span data-stu-id="eba6f-110">Gets or sets the name of the configuration file for an application.</span></span>|  
|<xref:System.AppDomainSetup.DynamicBase%2A>|<span data-ttu-id="eba6f-111">Ruft ab oder legt den Namen des Verzeichnisses, in dem dynamisch generierte Dateien gespeichert und auf die zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="eba6f-111">Gets or sets the name of the directory where dynamically generated files are stored and accessed.</span></span>|  
|<xref:System.AppDomainSetup.LicenseFile%2A>|<span data-ttu-id="eba6f-112">Ruft ab oder legt den Pfad fest, um die Lizenzdatei, die mit dieser Domäne verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="eba6f-112">Gets or sets the path to the license file that is associated with this domain.</span></span>|  
|<xref:System.AppDomainSetup.PrivateBinPath%2A>|<span data-ttu-id="eba6f-113">Ruft ab oder legt die Liste der Verzeichnisse, die zusammen mit den <xref:System.AppDomainSetup.ApplicationBase%2A> Verzeichnis, das nach privaten Assemblys suchen.</span><span class="sxs-lookup"><span data-stu-id="eba6f-113">Gets or sets the list of directories combined with the <xref:System.AppDomainSetup.ApplicationBase%2A> directory to probe for private assemblies.</span></span>|  
|<xref:System.AppDomainSetup.PrivateBinPathProbe%2A>|<span data-ttu-id="eba6f-114">Ruft ab oder legt einen Zeichenfolgenwert, der ein- oder ausschließt <xref:System.AppDomainSetup.ApplicationBase%2A> aus den Suchpfad für die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="eba6f-114">Gets or sets a string value that includes or excludes <xref:System.AppDomainSetup.ApplicationBase%2A> from the search path for the application.</span></span>|  
|<xref:System.AppDomainSetup.ShadowCopyDirectories%2A>|<span data-ttu-id="eba6f-115">Ruft ab oder legt den Namen der Verzeichnisse, die zu Schattenkopien werden Assemblys enthalten.</span><span class="sxs-lookup"><span data-stu-id="eba6f-115">Gets or sets the names of the directories that contain assemblies to be shadow-copied.</span></span>|  
|<xref:System.AppDomainSetup.ShadowCopyFiles%2A>|<span data-ttu-id="eba6f-116">Ruft ab oder legt eine Zeichenfolge, die angibt, ob die Erstellung von Schattenkopien ein- oder ausgeschaltet ist.</span><span class="sxs-lookup"><span data-stu-id="eba6f-116">Gets or sets a string that indicates whether shadow-copying is turned on or off.</span></span> <span data-ttu-id="eba6f-117">Gültige Werte sind "true" oder "false".</span><span class="sxs-lookup"><span data-stu-id="eba6f-117">Valid values are "true" or "false".</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eba6f-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="eba6f-118">Remarks</span></span>  
 <span data-ttu-id="eba6f-119">Die `IAppDomainSetup` Schnittstelle entspricht der verwalteten <xref:System.IAppDomainSetup> Schnittstelle, die die <xref:System.AppDomainSetup> Typ implementiert.</span><span class="sxs-lookup"><span data-stu-id="eba6f-119">The `IAppDomainSetup` interface corresponds to the managed <xref:System.IAppDomainSetup> interface, which the <xref:System.AppDomainSetup> type implements.</span></span> <span data-ttu-id="eba6f-120">Finden Sie unter <xref:System.IAppDomainSetup?displayProperty=nameWithType> eine ausführliche Beschreibung der Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="eba6f-120">See <xref:System.IAppDomainSetup?displayProperty=nameWithType> for detailed descriptions of its properties.</span></span>  
  
 <span data-ttu-id="eba6f-121">`IAppDomainSetup`Stellt Assembly-Bindungsinformationen, die hinzugefügt werden, kann, ein <xref:System.AppDomain> -Instanz vor ihrer Erstellung.</span><span class="sxs-lookup"><span data-stu-id="eba6f-121">`IAppDomainSetup` represents assembly binding information that can be added to an <xref:System.AppDomain> instance before its creation.</span></span> <span data-ttu-id="eba6f-122">Ein Host kann festlegen, z. B. die <xref:System.AppDomainSetup.ApplicationBase%2A> Eigenschaft, um ein Stammverzeichnis aufbauen, die die common Language Runtime (CLR)-für Prüfpunkte verwaltete Assemblys.</span><span class="sxs-lookup"><span data-stu-id="eba6f-122">For example, a host can set the <xref:System.AppDomainSetup.ApplicationBase%2A> property to establish a root directory, which the common language runtime (CLR) probes for managed assemblies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eba6f-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="eba6f-123">Requirements</span></span>  
 <span data-ttu-id="eba6f-124">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eba6f-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eba6f-125">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="eba6f-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="eba6f-126">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="eba6f-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="eba6f-127">**.NET Framework-Versionen:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eba6f-127">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eba6f-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eba6f-128">See Also</span></span>  
 <xref:System.AppDomain>  
 <xref:System.AppDomainSetup>  
 <xref:System.IAppDomainSetup>  
 [<span data-ttu-id="eba6f-129">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="eba6f-129">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
