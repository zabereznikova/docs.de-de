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
ms.openlocfilehash: 91f174cab4986882df795eb531baedfc0dd43962
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615864"
---
# <a name="iclrassemblyreferencelistisstringassemblyreferenceinlist-method"></a><span data-ttu-id="fb151-102">ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList-Methode</span><span class="sxs-lookup"><span data-stu-id="fb151-102">ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList Method</span></span>
<span data-ttu-id="fb151-103">Ruft einen Wert ab, der angibt, ob der angegebene Name mit dem Namen einer Assembly in der Liste übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="fb151-103">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb151-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fb151-104">Syntax</span></span>  
  
```cpp  
HRESULT IsStringAssemblyReferenceInList (  
    [in] LPCWSTR pwzAssemblyName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fb151-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fb151-105">Parameters</span></span>  
 `pwzAssemblyName`  
 <span data-ttu-id="fb151-106">in Der Name der Assembly, für die gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="fb151-106">[in] The name of the assembly for which to search.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fb151-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="fb151-107">Return Value</span></span>  
  
|<span data-ttu-id="fb151-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fb151-108">HRESULT</span></span>|<span data-ttu-id="fb151-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="fb151-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fb151-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="fb151-110">S_OK</span></span>|<span data-ttu-id="fb151-111">Die Zeichenfolge wird in der Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fb151-111">The string appears in the list.</span></span>|  
|<span data-ttu-id="fb151-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="fb151-112">S_FALSE</span></span>|<span data-ttu-id="fb151-113">Die Zeichenfolge wird nicht in der Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fb151-113">The string does not appear in the list.</span></span>|  
|<span data-ttu-id="fb151-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fb151-114">E_FAIL</span></span>|<span data-ttu-id="fb151-115">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="fb151-115">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fb151-116">Nachdem eine Methode E_FAIL zurückgegeben hat, kann die Common Language Runtime nicht mehr innerhalb des Prozesses verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fb151-116">After a method returns E_FAIL, the common language runtime is no longer usable within the process.</span></span> <span data-ttu-id="fb151-117">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="fb151-117">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fb151-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fb151-118">Requirements</span></span>  
 <span data-ttu-id="fb151-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb151-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb151-120">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="fb151-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fb151-121">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="fb151-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fb151-122">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb151-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb151-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fb151-123">See also</span></span>

- [<span data-ttu-id="fb151-124">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fb151-124">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="fb151-125">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fb151-125">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="fb151-126">IHostAssemblyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fb151-126">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
- [<span data-ttu-id="fb151-127">IHostAssemblyStore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fb151-127">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
