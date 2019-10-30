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
ms.openlocfilehash: 49a60b6b9b076138d8ff1f8a15041e9a6bacfede
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129243"
---
# <a name="iclrerrorreportingmanager-interface"></a><span data-ttu-id="268f2-102">ICLRErrorReportingManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="268f2-102">ICLRErrorReportingManager Interface</span></span>
<span data-ttu-id="268f2-103">Stellt Methoden bereit, die es dem Host ermöglichen, benutzerdefinierte stackdumps für die Fehlerberichterstattung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="268f2-103">Provides methods that allow the host to configure custom stack dumps for error reporting.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="268f2-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="268f2-104">Methods</span></span>  
  
|<span data-ttu-id="268f2-105">Methode</span><span class="sxs-lookup"><span data-stu-id="268f2-105">Method</span></span>|<span data-ttu-id="268f2-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="268f2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="268f2-107">BeginCustomDump-Methode</span><span class="sxs-lookup"><span data-stu-id="268f2-107">BeginCustomDump Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md)|<span data-ttu-id="268f2-108">Gibt die Konfiguration von benutzerdefinierten stackdumps für die Fehlerberichterstattung an.</span><span class="sxs-lookup"><span data-stu-id="268f2-108">Specifies the configuration of custom stack dumps for error reporting.</span></span>|  
|[<span data-ttu-id="268f2-109">EndCustomDump-Methode</span><span class="sxs-lookup"><span data-stu-id="268f2-109">EndCustomDump Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-endcustomdump-method.md)|<span data-ttu-id="268f2-110">Löscht die benutzerdefinierte Stapel Sicherungs Konfiguration, die durch einen früheren-`BeginCustomDump`festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="268f2-110">Clears the custom stack dump configuration that was set by an earlier call to `BeginCustomDump`.</span></span>|  
|[<span data-ttu-id="268f2-111">GetBucketParametersForCurrentException-Methode</span><span class="sxs-lookup"><span data-stu-id="268f2-111">GetBucketParametersForCurrentException Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-getbucketparametersforcurrentexception-method.md)|<span data-ttu-id="268f2-112">Ruft den Watson-Bucket für die aktuelle Ausnahme im aufrufenden Thread ab.</span><span class="sxs-lookup"><span data-stu-id="268f2-112">Gets the Watson bucket for the current exception on the calling thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="268f2-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="268f2-113">Remarks</span></span>  
 <span data-ttu-id="268f2-114">Die `BeginCustomDump`-Methode legt die benutzerdefinierte Stapel Sicherungs Konfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="268f2-114">The `BeginCustomDump` method sets custom stack dump configuration.</span></span> <span data-ttu-id="268f2-115">Die `EndCustomDump`-Methode löscht die benutzerdefinierte Stapel Sicherungs Konfiguration und gibt jeden zugeordneten Zustand frei.</span><span class="sxs-lookup"><span data-stu-id="268f2-115">The `EndCustomDump` method clears the custom stack dump configuration and frees any associated state.</span></span> <span data-ttu-id="268f2-116">Er sollte aufgerufen werden, nachdem der benutzerdefinierte Dump fertiggestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="268f2-116">It should be called after the custom dump is complete.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="268f2-117">Wenn `EndCustomDump` nicht aufgerufen wird, verursacht der Speicher einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="268f2-117">Failure to call `EndCustomDump` causes memory to leak.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="268f2-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="268f2-118">Requirements</span></span>  
 <span data-ttu-id="268f2-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="268f2-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="268f2-120">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="268f2-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="268f2-121">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="268f2-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="268f2-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="268f2-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="268f2-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="268f2-123">See also</span></span>

- [<span data-ttu-id="268f2-124">ECustomDumpItemKind-Enumeration</span><span class="sxs-lookup"><span data-stu-id="268f2-124">ECustomDumpItemKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)
- [<span data-ttu-id="268f2-125">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="268f2-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
