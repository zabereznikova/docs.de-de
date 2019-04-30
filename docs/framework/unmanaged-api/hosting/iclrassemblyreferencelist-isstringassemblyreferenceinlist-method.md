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
ms.openlocfilehash: de17a91b5093372579a4d9435532a95406addd0a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61969909"
---
# <a name="iclrassemblyreferencelistisstringassemblyreferenceinlist-method"></a><span data-ttu-id="17fb5-102">ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList-Methode</span><span class="sxs-lookup"><span data-stu-id="17fb5-102">ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList Method</span></span>
<span data-ttu-id="17fb5-103">Ruft einen Wert, der angibt, ob der Name einer Assembly in der Liste mit dem angegebene Namen übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="17fb5-103">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17fb5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="17fb5-104">Syntax</span></span>  
  
```  
HRESULT IsStringAssemblyReferenceInList (  
    [in] LPCWSTR pwzAssemblyName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="17fb5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="17fb5-105">Parameters</span></span>  
 `pwzAssemblyName`  
 <span data-ttu-id="17fb5-106">[in] Der Name der Assembly nach dem gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="17fb5-106">[in] The name of the assembly for which to search.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="17fb5-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="17fb5-107">Return Value</span></span>  
  
|<span data-ttu-id="17fb5-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="17fb5-108">HRESULT</span></span>|<span data-ttu-id="17fb5-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="17fb5-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="17fb5-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="17fb5-110">S_OK</span></span>|<span data-ttu-id="17fb5-111">Die Zeichenfolge, die in der Liste angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="17fb5-111">The string appears in the list.</span></span>|  
|<span data-ttu-id="17fb5-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="17fb5-112">S_FALSE</span></span>|<span data-ttu-id="17fb5-113">Die Zeichenfolge wird in der Liste nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="17fb5-113">The string does not appear in the list.</span></span>|  
|<span data-ttu-id="17fb5-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="17fb5-114">E_FAIL</span></span>|<span data-ttu-id="17fb5-115">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="17fb5-115">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="17fb5-116">Wenn eine Methode E_FAIL zurückgegeben, kann die common Language Runtime nicht mehr innerhalb des Prozesses verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="17fb5-116">After a method returns E_FAIL, the common language runtime is no longer usable within the process.</span></span> <span data-ttu-id="17fb5-117">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="17fb5-117">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="17fb5-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="17fb5-118">Requirements</span></span>  
 <span data-ttu-id="17fb5-119">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17fb5-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17fb5-120">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="17fb5-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="17fb5-121">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="17fb5-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="17fb5-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17fb5-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17fb5-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="17fb5-123">See also</span></span>

- [<span data-ttu-id="17fb5-124">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="17fb5-124">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="17fb5-125">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="17fb5-125">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="17fb5-126">IHostAssemblyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="17fb5-126">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="17fb5-127">IHostAssemblyStore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="17fb5-127">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
