---
title: ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList-Methode
ms.date: 03/30/2017
api_name:
- ICLRAssemblyReferenceList.IsStringAssemblyReferenceInList
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList
helpviewer_keywords:
- ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList method [.NET Framework hosting]
- IsStringAssemblyReferenceInList method [.NET Framework hosting]
ms.assetid: e6121cc3-2f11-42c7-bdae-47808581ff71
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ad7230731775cbc56dd0f1eaed72df19512d3733
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33432595"
---
# <a name="iclrassemblyreferencelistisstringassemblyreferenceinlist-method"></a><span data-ttu-id="b04e9-102">ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList-Methode</span><span class="sxs-lookup"><span data-stu-id="b04e9-102">ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList Method</span></span>
<span data-ttu-id="b04e9-103">Ruft einen Wert, der angibt, ob der angegebene Name den Namen einer Assembly in der Liste übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="b04e9-103">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b04e9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b04e9-104">Syntax</span></span>  
  
```  
HRESULT IsStringAssemblyReferenceInList (  
    [in] LPCWSTR pwzAssemblyName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b04e9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b04e9-105">Parameters</span></span>  
 `pwzAssemblyName`  
 <span data-ttu-id="b04e9-106">[in] Der Name der Assembly nach dem gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="b04e9-106">[in] The name of the assembly for which to search.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b04e9-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b04e9-107">Return Value</span></span>  
  
|<span data-ttu-id="b04e9-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b04e9-108">HRESULT</span></span>|<span data-ttu-id="b04e9-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b04e9-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b04e9-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="b04e9-110">S_OK</span></span>|<span data-ttu-id="b04e9-111">Die Zeichenfolge, die in der Liste angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b04e9-111">The string appears in the list.</span></span>|  
|<span data-ttu-id="b04e9-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="b04e9-112">S_FALSE</span></span>|<span data-ttu-id="b04e9-113">Die Zeichenfolge wird in der Liste nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b04e9-113">The string does not appear in the list.</span></span>|  
|<span data-ttu-id="b04e9-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b04e9-114">E_FAIL</span></span>|<span data-ttu-id="b04e9-115">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="b04e9-115">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b04e9-116">Nachdem eine Methode E_FAIL zurückgegeben hat, ist die common Language Runtime nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="b04e9-116">After a method returns E_FAIL, the common language runtime is no longer usable within the process.</span></span> <span data-ttu-id="b04e9-117">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="b04e9-117">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b04e9-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b04e9-118">Requirements</span></span>  
 <span data-ttu-id="b04e9-119">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b04e9-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b04e9-120">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b04e9-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b04e9-121">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="b04e9-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b04e9-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b04e9-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b04e9-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b04e9-123">See Also</span></span>  
 [<span data-ttu-id="b04e9-124">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b04e9-124">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="b04e9-125">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b04e9-125">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="b04e9-126">IHostAssemblyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b04e9-126">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [<span data-ttu-id="b04e9-127">IHostAssemblyStore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b04e9-127">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
