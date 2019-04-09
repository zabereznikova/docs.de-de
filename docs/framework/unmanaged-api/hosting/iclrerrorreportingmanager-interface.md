---
title: ICLRErrorReportingManager-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager
helpviewer_keywords:
- ICLRErrorReportingManager interface [.NET Framework hosting]
ms.assetid: ea8af0d5-4133-4472-8a1f-50570d7e85fa
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a20b79dd5eda9c431511cc49e7e3adaa9486b2aa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59155986"
---
# <a name="iclrerrorreportingmanager-interface"></a><span data-ttu-id="e8316-102">ICLRErrorReportingManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e8316-102">ICLRErrorReportingManager Interface</span></span>
<span data-ttu-id="e8316-103">Bietet Methoden, mit die den Host benutzerdefinierte stapelabbilder für die Fehlerberichterstattung konfigurieren zu können.</span><span class="sxs-lookup"><span data-stu-id="e8316-103">Provides methods that allow the host to configure custom stack dumps for error reporting.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e8316-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="e8316-104">Methods</span></span>  
  
|<span data-ttu-id="e8316-105">Methode</span><span class="sxs-lookup"><span data-stu-id="e8316-105">Method</span></span>|<span data-ttu-id="e8316-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e8316-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e8316-107">BeginCustomDump-Methode</span><span class="sxs-lookup"><span data-stu-id="e8316-107">BeginCustomDump Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md)|<span data-ttu-id="e8316-108">Gibt die Konfiguration des benutzerdefinierten Stapeldumps für die Fehlerberichterstattung.</span><span class="sxs-lookup"><span data-stu-id="e8316-108">Specifies the configuration of custom stack dumps for error reporting.</span></span>|  
|[<span data-ttu-id="e8316-109">EndCustomDump-Methode</span><span class="sxs-lookup"><span data-stu-id="e8316-109">EndCustomDump Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md)|<span data-ttu-id="e8316-110">Löscht die Konfiguration des benutzerdefinierten Dump der von einem früheren Aufruf festgelegte `BeginCustomDump`.</span><span class="sxs-lookup"><span data-stu-id="e8316-110">Clears the custom stack dump configuration that was set by an earlier call to `BeginCustomDump`.</span></span>|  
|[<span data-ttu-id="e8316-111">GetBucketParametersForCurrentException-Methode</span><span class="sxs-lookup"><span data-stu-id="e8316-111">GetBucketParametersForCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-getbucketparametersforcurrentexception-method.md)|<span data-ttu-id="e8316-112">Ruft die Dr. Watson-Bucket für die aktuelle Ausnahme im aufrufenden Thread ab.</span><span class="sxs-lookup"><span data-stu-id="e8316-112">Gets the Watson bucket for the current exception on the calling thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e8316-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e8316-113">Remarks</span></span>  
 <span data-ttu-id="e8316-114">Die `BeginCustomDump` Methode legt die Konfiguration des benutzerdefinierten Dump fest.</span><span class="sxs-lookup"><span data-stu-id="e8316-114">The `BeginCustomDump` method sets custom stack dump configuration.</span></span> <span data-ttu-id="e8316-115">Die `EndCustomDump` Methode löscht die benutzerdefinierte Stapeldumpkonfiguration und alle zugeordneten Zustand freigibt.</span><span class="sxs-lookup"><span data-stu-id="e8316-115">The `EndCustomDump` method clears the custom stack dump configuration and frees any associated state.</span></span> <span data-ttu-id="e8316-116">Es sollte aufgerufen werden, nachdem das benutzerdefinierte Abbild abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="e8316-116">It should be called after the custom dump is complete.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e8316-117">Fehler beim Aufrufen `EndCustomDump` Speicherverluste verursacht.</span><span class="sxs-lookup"><span data-stu-id="e8316-117">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8316-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e8316-118">Requirements</span></span>  
 <span data-ttu-id="e8316-119">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8316-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8316-120">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e8316-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e8316-121">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e8316-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="e8316-122">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="e8316-122">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e8316-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e8316-123">See also</span></span>

- [<span data-ttu-id="e8316-124">ECustomDumpItemKind-Enumeration</span><span class="sxs-lookup"><span data-stu-id="e8316-124">ECustomDumpItemKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)
- [<span data-ttu-id="e8316-125">Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="e8316-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
