---
title: ICLRAssemblyReferenceList::IsAssemblyReferenceInList-Methode
ms.date: 03/30/2017
api_name:
- ICLRAssemblyReferenceList.IsAssemblyReferenceInList
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyReferenceList::IsAssemblyReferenceInList
helpviewer_keywords:
- ICLRAssemblyReferenceList::IsAssemblyReferenceInList method [.NET Framework hosting]
- IsAssemblyReferenceInList method [.NET Framework hosting]
ms.assetid: 8a570813-21be-407e-92a6-7ae8de3bc728
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e6a95a636623f0b4ea75706039194572ecf1bbe0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59136200"
---
# <a name="iclrassemblyreferencelistisassemblyreferenceinlist-method"></a><span data-ttu-id="5a73b-102">ICLRAssemblyReferenceList::IsAssemblyReferenceInList-Methode</span><span class="sxs-lookup"><span data-stu-id="5a73b-102">ICLRAssemblyReferenceList::IsAssemblyReferenceInList Method</span></span>
<span data-ttu-id="5a73b-103">Ruft einen Wert, der angibt, ob der angegebene Zeiger auf eine Assembly in der Liste verweist.</span><span class="sxs-lookup"><span data-stu-id="5a73b-103">Gets a value that indicates whether the supplied pointer refers to an assembly in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a73b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5a73b-104">Syntax</span></span>  
  
```  
HRESULT IsAssemblyReferenceInList (  
    [in] IUnknown *pName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a73b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5a73b-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="5a73b-106">[in] Ein Schnittstellenzeiger auf die Assembly nach dem gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="5a73b-106">[in] An interface pointer to the assembly for which to search.</span></span> <span data-ttu-id="5a73b-107">Gültige Werte sind vom Typ `IAssemblyName` oder `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="5a73b-107">Valid values are of type `IAssemblyName` or `IReferenceIdentity`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5a73b-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5a73b-108">Return Value</span></span>  
  
|<span data-ttu-id="5a73b-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5a73b-109">HRESULT</span></span>|<span data-ttu-id="5a73b-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5a73b-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5a73b-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="5a73b-111">S_OK</span></span>|<span data-ttu-id="5a73b-112">Die Zeichenfolge, die in der Liste angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="5a73b-112">The string appears in the list.</span></span>|  
|<span data-ttu-id="5a73b-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="5a73b-113">S_FALSE</span></span>|<span data-ttu-id="5a73b-114">Die Zeichenfolge wird in der Liste nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5a73b-114">The string does not appear in the list.</span></span>|  
|<span data-ttu-id="5a73b-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5a73b-115">E_FAIL</span></span>|<span data-ttu-id="5a73b-116">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="5a73b-116">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5a73b-117">Wenn eine Methode E_FAIL zurückgegeben, kann die common Language Runtime nicht mehr innerhalb des Prozesses verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5a73b-117">After a method returns E_FAIL, the common language runtime is no longer usable within the process.</span></span> <span data-ttu-id="5a73b-118">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="5a73b-118">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5a73b-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5a73b-119">Requirements</span></span>  
 <span data-ttu-id="5a73b-120">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a73b-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a73b-121">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5a73b-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5a73b-122">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="5a73b-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5a73b-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a73b-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a73b-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5a73b-124">See also</span></span>

- [<span data-ttu-id="5a73b-125">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5a73b-125">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="5a73b-126">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5a73b-126">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="5a73b-127">IHostAssemblyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5a73b-127">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="5a73b-128">IHostAssemblyStore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5a73b-128">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
