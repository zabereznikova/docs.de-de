---
title: IAppDomainSetup-Schnittstelle
ms.date: 03/30/2017
api_name:
- IAppDomainSetup
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IAppDomainSetup
helpviewer_keywords:
- IAppDomainSetup interface [.NET Framework hosting]
ms.assetid: 1844da85-c031-40bf-bea4-1a3d12a36c8c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bbde873481aea9de94862117a99079301965f33c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59220070"
---
# <a name="iappdomainsetup-interface"></a><span data-ttu-id="d0d0c-102">IAppDomainSetup-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d0d0c-102">IAppDomainSetup Interface</span></span>
<span data-ttu-id="d0d0c-103">Enthält Eigenschaften, die dem Host so konfigurieren Sie eine <xref:System.AppDomain?displayProperty=nameWithType> Typ vor dem Aufruf der [ICorRuntimeHost:: CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) Methode, um es zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d0d0c-103">Provides properties that allow the host to configure an <xref:System.AppDomain?displayProperty=nameWithType> type before calling the [ICorRuntimeHost::CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) method to create it.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="d0d0c-104">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="d0d0c-104">Properties</span></span>  
  
|<span data-ttu-id="d0d0c-105">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="d0d0c-105">Property</span></span>|<span data-ttu-id="d0d0c-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d0d0c-106">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.AppDomainSetup.ApplicationBase%2A>|<span data-ttu-id="d0d0c-107">Übernimmt oder bestimmt den Namen des Verzeichnisses, das die Anwendung enthält.</span><span class="sxs-lookup"><span data-stu-id="d0d0c-107">Gets or sets the name of the directory that contains the application.</span></span>|  
|<xref:System.AppDomainSetup.ApplicationName%2A>|<span data-ttu-id="d0d0c-108">Ruft den Namen der Anwendung ab oder legt diesen fest.</span><span class="sxs-lookup"><span data-stu-id="d0d0c-108">Gets or sets the name of the application.</span></span>|  
|<xref:System.AppDomainSetup.CachePath%2A>|<span data-ttu-id="d0d0c-109">Übernimmt oder bestimmt den Namen eines Bereichs bestimmte für die Anwendung, in denen Dateien Schattenkopien sind.</span><span class="sxs-lookup"><span data-stu-id="d0d0c-109">Gets or sets the name of an area specific to the application where files are shadow-copied.</span></span>|  
|<xref:System.AppDomainSetup.ConfigurationFile%2A>|<span data-ttu-id="d0d0c-110">Ruft ab oder legt den Namen der Konfigurationsdatei für eine Anwendung fest.</span><span class="sxs-lookup"><span data-stu-id="d0d0c-110">Gets or sets the name of the configuration file for an application.</span></span>|  
|<xref:System.AppDomainSetup.DynamicBase%2A>|<span data-ttu-id="d0d0c-111">Übernimmt oder bestimmt den Namen des Verzeichnisses, in dem dynamisch generierte Dateien gespeichert und auf die zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="d0d0c-111">Gets or sets the name of the directory where dynamically generated files are stored and accessed.</span></span>|  
|<xref:System.AppDomainSetup.LicenseFile%2A>|<span data-ttu-id="d0d0c-112">Übernimmt oder bestimmt den Pfad zu der Lizenzdatei, die mit dieser Domäne verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="d0d0c-112">Gets or sets the path to the license file that is associated with this domain.</span></span>|  
|<xref:System.AppDomainSetup.PrivateBinPath%2A>|<span data-ttu-id="d0d0c-113">Übernimmt oder bestimmt die Liste der Verzeichnisse, die in Kombination mit der <xref:System.AppDomainSetup.ApplicationBase%2A> Verzeichnis nach privaten Assemblys suchen.</span><span class="sxs-lookup"><span data-stu-id="d0d0c-113">Gets or sets the list of directories combined with the <xref:System.AppDomainSetup.ApplicationBase%2A> directory to probe for private assemblies.</span></span>|  
|<xref:System.AppDomainSetup.PrivateBinPathProbe%2A>|<span data-ttu-id="d0d0c-114">Übernimmt oder bestimmt die Zeichenfolge zurück, das ein- oder ausschließt <xref:System.AppDomainSetup.ApplicationBase%2A> in den Suchpfad für die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="d0d0c-114">Gets or sets a string value that includes or excludes <xref:System.AppDomainSetup.ApplicationBase%2A> from the search path for the application.</span></span>|  
|<xref:System.AppDomainSetup.ShadowCopyDirectories%2A>|<span data-ttu-id="d0d0c-115">Übernimmt oder bestimmt den Namen der Verzeichnisse, die Assemblys werden Schattenkopien enthalten.</span><span class="sxs-lookup"><span data-stu-id="d0d0c-115">Gets or sets the names of the directories that contain assemblies to be shadow-copied.</span></span>|  
|<xref:System.AppDomainSetup.ShadowCopyFiles%2A>|<span data-ttu-id="d0d0c-116">Ruft ab oder legt eine Zeichenfolge, die angibt, ob die Erstellung von Schattenkopien aktiviert oder deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="d0d0c-116">Gets or sets a string that indicates whether shadow-copying is turned on or off.</span></span> <span data-ttu-id="d0d0c-117">Gültige Werte sind "true" oder "false".</span><span class="sxs-lookup"><span data-stu-id="d0d0c-117">Valid values are "true" or "false".</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d0d0c-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d0d0c-118">Remarks</span></span>  
 <span data-ttu-id="d0d0c-119">Die `IAppDomainSetup` Schnittstelle entspricht der verwalteten <xref:System.IAppDomainSetup> Schnittstelle, die die <xref:System.AppDomainSetup> Typ implementiert.</span><span class="sxs-lookup"><span data-stu-id="d0d0c-119">The `IAppDomainSetup` interface corresponds to the managed <xref:System.IAppDomainSetup> interface, which the <xref:System.AppDomainSetup> type implements.</span></span> <span data-ttu-id="d0d0c-120">Finden Sie unter <xref:System.IAppDomainSetup?displayProperty=nameWithType> ausführliche Beschreibungen der Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="d0d0c-120">See <xref:System.IAppDomainSetup?displayProperty=nameWithType> for detailed descriptions of its properties.</span></span>  
  
 `IAppDomainSetup` <span data-ttu-id="d0d0c-121">Stellt Assembly-Bindungsinformationen, die hinzugefügt werden, kann, ein <xref:System.AppDomain> Instanz vor ihrer Erstellung.</span><span class="sxs-lookup"><span data-stu-id="d0d0c-121">represents assembly binding information that can be added to an <xref:System.AppDomain> instance before its creation.</span></span> <span data-ttu-id="d0d0c-122">Ein Host kann festlegen, z. B. die <xref:System.AppDomainSetup.ApplicationBase%2A> Eigenschaft ein Stammverzeichnis, zu ermitteln, welche die Tests die common Language Runtime (CLR) für verwaltete Assemblys.</span><span class="sxs-lookup"><span data-stu-id="d0d0c-122">For example, a host can set the <xref:System.AppDomainSetup.ApplicationBase%2A> property to establish a root directory, which the common language runtime (CLR) probes for managed assemblies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0d0c-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d0d0c-123">Requirements</span></span>  
 <span data-ttu-id="d0d0c-124">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d0d0c-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0d0c-125">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d0d0c-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d0d0c-126">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d0d0c-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="d0d0c-127">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="d0d0c-127">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d0d0c-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d0d0c-128">See also</span></span>

- <xref:System.AppDomain>
- <xref:System.AppDomainSetup>
- <xref:System.IAppDomainSetup>
- [<span data-ttu-id="d0d0c-129">Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="d0d0c-129">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
