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
ms.openlocfilehash: 0fab64c31d4a73995c16d21767f4569f21c7df9a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126870"
---
# <a name="iappdomainsetup-interface"></a><span data-ttu-id="574f4-102">IAppDomainSetup-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="574f4-102">IAppDomainSetup Interface</span></span>
<span data-ttu-id="574f4-103">Stellt Eigenschaften bereit, die es dem Host ermöglichen, einen <xref:System.AppDomain?displayProperty=nameWithType> Typ zu konfigurieren, bevor die [ICorRuntimeHost:: CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) -Methode aufgerufen wird, um ihn zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="574f4-103">Provides properties that allow the host to configure an <xref:System.AppDomain?displayProperty=nameWithType> type before calling the [ICorRuntimeHost::CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) method to create it.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="574f4-104">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="574f4-104">Properties</span></span>  
  
|<span data-ttu-id="574f4-105">property</span><span class="sxs-lookup"><span data-stu-id="574f4-105">Property</span></span>|<span data-ttu-id="574f4-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="574f4-106">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.AppDomainSetup.ApplicationBase%2A>|<span data-ttu-id="574f4-107">Ruft den Namen des Verzeichnisses ab, das die Anwendung enthält, oder legt diesen fest.</span><span class="sxs-lookup"><span data-stu-id="574f4-107">Gets or sets the name of the directory that contains the application.</span></span>|  
|<xref:System.AppDomainSetup.ApplicationName%2A>|<span data-ttu-id="574f4-108">Ruft den Namen der Anwendung ab oder legt diesen fest.</span><span class="sxs-lookup"><span data-stu-id="574f4-108">Gets or sets the name of the application.</span></span>|  
|<xref:System.AppDomainSetup.CachePath%2A>|<span data-ttu-id="574f4-109">Ruft den Namen eines für die Anwendung spezifischen Bereichs ab, in dem Dateien kopiert werden, oder legt diesen fest.</span><span class="sxs-lookup"><span data-stu-id="574f4-109">Gets or sets the name of an area specific to the application where files are shadow-copied.</span></span>|  
|<xref:System.AppDomainSetup.ConfigurationFile%2A>|<span data-ttu-id="574f4-110">Ruft den Namen der Konfigurationsdatei für eine Anwendung ab oder legt ihn fest.</span><span class="sxs-lookup"><span data-stu-id="574f4-110">Gets or sets the name of the configuration file for an application.</span></span>|  
|<xref:System.AppDomainSetup.DynamicBase%2A>|<span data-ttu-id="574f4-111">Ruft den Namen des Verzeichnisses ab, in dem dynamisch generierte Dateien gespeichert und darauf zugegriffen wird, oder legt diesen fest.</span><span class="sxs-lookup"><span data-stu-id="574f4-111">Gets or sets the name of the directory where dynamically generated files are stored and accessed.</span></span>|  
|<xref:System.AppDomainSetup.LicenseFile%2A>|<span data-ttu-id="574f4-112">Ruft den Pfad zu der Lizenzdatei ab, die dieser Domäne zugeordnet ist, oder legt diesen fest.</span><span class="sxs-lookup"><span data-stu-id="574f4-112">Gets or sets the path to the license file that is associated with this domain.</span></span>|  
|<xref:System.AppDomainSetup.PrivateBinPath%2A>|<span data-ttu-id="574f4-113">Ruft die Liste der Verzeichnisse in Kombination mit dem <xref:System.AppDomainSetup.ApplicationBase%2A> Verzeichnis ab, das nach privaten Assemblys gesucht werden soll</span><span class="sxs-lookup"><span data-stu-id="574f4-113">Gets or sets the list of directories combined with the <xref:System.AppDomainSetup.ApplicationBase%2A> directory to probe for private assemblies.</span></span>|  
|<xref:System.AppDomainSetup.PrivateBinPathProbe%2A>|<span data-ttu-id="574f4-114">Ruft einen Zeichen folgen Wert ab, der <xref:System.AppDomainSetup.ApplicationBase%2A> aus dem Suchpfad für die Anwendung einschließt oder ausschließt, oder legt diesen fest.</span><span class="sxs-lookup"><span data-stu-id="574f4-114">Gets or sets a string value that includes or excludes <xref:System.AppDomainSetup.ApplicationBase%2A> from the search path for the application.</span></span>|  
|<xref:System.AppDomainSetup.ShadowCopyDirectories%2A>|<span data-ttu-id="574f4-115">Ruft die Namen der Verzeichnisse ab, die die zu Schatten kopierenden Assemblys enthalten, oder legt diese fest.</span><span class="sxs-lookup"><span data-stu-id="574f4-115">Gets or sets the names of the directories that contain assemblies to be shadow-copied.</span></span>|  
|<xref:System.AppDomainSetup.ShadowCopyFiles%2A>|<span data-ttu-id="574f4-116">Ruft eine Zeichenfolge ab, die angibt, ob das Schatten kopieren aktiviert oder deaktiviert ist, oder legt diese fest.</span><span class="sxs-lookup"><span data-stu-id="574f4-116">Gets or sets a string that indicates whether shadow-copying is turned on or off.</span></span> <span data-ttu-id="574f4-117">Gültige Werte sind "true" oder "false".</span><span class="sxs-lookup"><span data-stu-id="574f4-117">Valid values are "true" or "false".</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="574f4-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="574f4-118">Remarks</span></span>  
 <span data-ttu-id="574f4-119">Die `IAppDomainSetup`-Schnittstelle entspricht der verwalteten <xref:System.IAppDomainSetup> Schnittstelle, die vom <xref:System.AppDomainSetup> Typ implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="574f4-119">The `IAppDomainSetup` interface corresponds to the managed <xref:System.IAppDomainSetup> interface, which the <xref:System.AppDomainSetup> type implements.</span></span> <span data-ttu-id="574f4-120">Ausführliche Beschreibungen der Eigenschaften finden Sie unter <xref:System.IAppDomainSetup?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="574f4-120">See <xref:System.IAppDomainSetup?displayProperty=nameWithType> for detailed descriptions of its properties.</span></span>  
  
 <span data-ttu-id="574f4-121">`IAppDomainSetup` stellt Assemblybindungsinformationen dar, die einer <xref:System.AppDomain> Instanz vor deren Erstellung hinzugefügt werden können.</span><span class="sxs-lookup"><span data-stu-id="574f4-121">`IAppDomainSetup` represents assembly binding information that can be added to an <xref:System.AppDomain> instance before its creation.</span></span> <span data-ttu-id="574f4-122">Beispielsweise kann ein Host die <xref:System.AppDomainSetup.ApplicationBase%2A>-Eigenschaft festlegen, um ein Stammverzeichnis einzurichten, das von der Common Language Runtime (CLR) für verwaltete Assemblys überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="574f4-122">For example, a host can set the <xref:System.AppDomainSetup.ApplicationBase%2A> property to establish a root directory, which the common language runtime (CLR) probes for managed assemblies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="574f4-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="574f4-123">Requirements</span></span>  
 <span data-ttu-id="574f4-124">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="574f4-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="574f4-125">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="574f4-125">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="574f4-126">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="574f4-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="574f4-127">**.NET Framework-Versionen:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="574f4-127">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="574f4-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="574f4-128">See also</span></span>

- <xref:System.AppDomain>
- <xref:System.AppDomainSetup>
- <xref:System.IAppDomainSetup>
- [<span data-ttu-id="574f4-129">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="574f4-129">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
