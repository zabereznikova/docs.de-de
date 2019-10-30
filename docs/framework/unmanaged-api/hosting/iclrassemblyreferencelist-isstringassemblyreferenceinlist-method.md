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
ms.openlocfilehash: 4dc91723f009d46f9c57b1c99aa66ba7a1b127e4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126635"
---
# <a name="iclrassemblyreferencelistisstringassemblyreferenceinlist-method"></a><span data-ttu-id="4b286-102">ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList-Methode</span><span class="sxs-lookup"><span data-stu-id="4b286-102">ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList Method</span></span>
<span data-ttu-id="4b286-103">Ruft einen Wert ab, der angibt, ob der angegebene Name mit dem Namen einer Assembly in der Liste übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="4b286-103">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b286-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4b286-104">Syntax</span></span>  
  
```cpp  
HRESULT IsStringAssemblyReferenceInList (  
    [in] LPCWSTR pwzAssemblyName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4b286-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4b286-105">Parameters</span></span>  
 `pwzAssemblyName`  
 <span data-ttu-id="4b286-106">in Der Name der Assembly, für die gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="4b286-106">[in] The name of the assembly for which to search.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4b286-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4b286-107">Return Value</span></span>  
  
|<span data-ttu-id="4b286-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4b286-108">HRESULT</span></span>|<span data-ttu-id="4b286-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4b286-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4b286-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="4b286-110">S_OK</span></span>|<span data-ttu-id="4b286-111">Die Zeichenfolge wird in der Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4b286-111">The string appears in the list.</span></span>|  
|<span data-ttu-id="4b286-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="4b286-112">S_FALSE</span></span>|<span data-ttu-id="4b286-113">Die Zeichenfolge wird nicht in der Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4b286-113">The string does not appear in the list.</span></span>|  
|<span data-ttu-id="4b286-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4b286-114">E_FAIL</span></span>|<span data-ttu-id="4b286-115">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="4b286-115">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4b286-116">Nachdem eine Methode E_FAIL zurückgegeben hat, kann die Common Language Runtime nicht mehr innerhalb des Prozesses verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4b286-116">After a method returns E_FAIL, the common language runtime is no longer usable within the process.</span></span> <span data-ttu-id="4b286-117">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="4b286-117">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4b286-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4b286-118">Requirements</span></span>  
 <span data-ttu-id="4b286-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b286-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b286-120">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="4b286-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4b286-121">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="4b286-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4b286-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b286-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b286-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4b286-123">See also</span></span>

- [<span data-ttu-id="4b286-124">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4b286-124">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="4b286-125">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4b286-125">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="4b286-126">IHostAssemblyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4b286-126">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="4b286-127">IHostAssemblyStore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4b286-127">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
