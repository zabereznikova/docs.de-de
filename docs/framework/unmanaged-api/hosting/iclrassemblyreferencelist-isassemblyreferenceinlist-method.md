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
ms.openlocfilehash: 0632a7f5feee87c386d9488a6c989413af68a47f
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615890"
---
# <a name="iclrassemblyreferencelistisassemblyreferenceinlist-method"></a><span data-ttu-id="9a5a6-102">ICLRAssemblyReferenceList::IsAssemblyReferenceInList-Methode</span><span class="sxs-lookup"><span data-stu-id="9a5a6-102">ICLRAssemblyReferenceList::IsAssemblyReferenceInList Method</span></span>
<span data-ttu-id="9a5a6-103">Ruft einen Wert ab, der angibt, ob der angegebene Zeiger auf eine Assembly in der Liste verweist.</span><span class="sxs-lookup"><span data-stu-id="9a5a6-103">Gets a value that indicates whether the supplied pointer refers to an assembly in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a5a6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9a5a6-104">Syntax</span></span>  
  
```cpp  
HRESULT IsAssemblyReferenceInList (  
    [in] IUnknown *pName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a5a6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9a5a6-105">Parameters</span></span>  
 `pName`  
 <span data-ttu-id="9a5a6-106">in Ein Schnittstellen Zeiger auf die Assembly, für die gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="9a5a6-106">[in] An interface pointer to the assembly for which to search.</span></span> <span data-ttu-id="9a5a6-107">Gültige Werte sind vom Typ `IAssemblyName` oder `IReferenceIdentity` .</span><span class="sxs-lookup"><span data-stu-id="9a5a6-107">Valid values are of type `IAssemblyName` or `IReferenceIdentity`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9a5a6-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9a5a6-108">Return Value</span></span>  
  
|<span data-ttu-id="9a5a6-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9a5a6-109">HRESULT</span></span>|<span data-ttu-id="9a5a6-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9a5a6-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9a5a6-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="9a5a6-111">S_OK</span></span>|<span data-ttu-id="9a5a6-112">Die Zeichenfolge wird in der Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9a5a6-112">The string appears in the list.</span></span>|  
|<span data-ttu-id="9a5a6-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="9a5a6-113">S_FALSE</span></span>|<span data-ttu-id="9a5a6-114">Die Zeichenfolge wird nicht in der Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9a5a6-114">The string does not appear in the list.</span></span>|  
|<span data-ttu-id="9a5a6-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9a5a6-115">E_FAIL</span></span>|<span data-ttu-id="9a5a6-116">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="9a5a6-116">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9a5a6-117">Nachdem eine Methode E_FAIL zurückgegeben hat, kann die Common Language Runtime nicht mehr innerhalb des Prozesses verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9a5a6-117">After a method returns E_FAIL, the common language runtime is no longer usable within the process.</span></span> <span data-ttu-id="9a5a6-118">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="9a5a6-118">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9a5a6-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9a5a6-119">Requirements</span></span>  
 <span data-ttu-id="9a5a6-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a5a6-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a5a6-121">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="9a5a6-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9a5a6-122">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="9a5a6-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9a5a6-123">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a5a6-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a5a6-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9a5a6-124">See also</span></span>

- [<span data-ttu-id="9a5a6-125">ICLRAssemblyIdentityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9a5a6-125">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="9a5a6-126">ICLRAssemblyReferenceList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9a5a6-126">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="9a5a6-127">IHostAssemblyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9a5a6-127">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
- [<span data-ttu-id="9a5a6-128">IHostAssemblyStore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9a5a6-128">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
