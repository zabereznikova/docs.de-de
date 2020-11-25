---
title: ICLRMetaHost::EnumerateLoadedRuntimes-Methode
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.EnumerateLoadedRuntimes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::EnumerateLoadedRuntimes
helpviewer_keywords:
- EnumerateLoadedRuntimes method [.NET Framework hosting]
- ICLRMetaHost::EnumerateLoadedRuntimes method [.NET Framework hosting]
ms.assetid: 22fc0a3f-dce4-4766-9a3c-9fab15f4b4ca
topic_type:
- apiref
ms.openlocfilehash: 98184dd6ea16df066905039b028acd689ff3f290
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730434"
---
# <a name="iclrmetahostenumerateloadedruntimes-method"></a><span data-ttu-id="b1b27-102">ICLRMetaHost::EnumerateLoadedRuntimes-Methode</span><span class="sxs-lookup"><span data-stu-id="b1b27-102">ICLRMetaHost::EnumerateLoadedRuntimes Method</span></span>

<span data-ttu-id="b1b27-103">Gibt eine Enumeration zurück, die einen gültigen [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) -Schnittstellen Zeiger für jede Version der Common Language Runtime (CLR) enthält, die in einem bestimmten Prozess geladen wird.</span><span class="sxs-lookup"><span data-stu-id="b1b27-103">Returns an enumeration that includes a valid [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface pointer for each version of the common language runtime (CLR) that is loaded in a given process.</span></span> <span data-ttu-id="b1b27-104">Diese Methode ersetzt die [GetVersionFromProcess](getversionfromprocess-function.md) -Funktion.</span><span class="sxs-lookup"><span data-stu-id="b1b27-104">This method supersedes the [GetVersionFromProcess](getversionfromprocess-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1b27-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b1b27-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateLoadedRuntimes (  
    [in] HANDLE hndProcess,  
    [out, retval] IEnumUnknown **ppEnumerator  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b1b27-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="b1b27-106">Parameters</span></span>  

 `hndProcess`  
 <span data-ttu-id="b1b27-107">in Das Handle des Prozesses, der auf geladene Runtimes überprüft werden soll.</span><span class="sxs-lookup"><span data-stu-id="b1b27-107">[in] The handle of the process to inspect for loaded runtimes.</span></span>  
  
 `ppEnumerator`  
 <span data-ttu-id="b1b27-108">vorgenommen Eine <xref:Microsoft.VisualStudio.OLE.Interop.IEnumUnknown> Enumeration von [iclrruntimeingefo](iclrruntimeinfo-interface.md) -Schnittstellen, die jeder vom Prozess geladenen CLR entsprechen.</span><span class="sxs-lookup"><span data-stu-id="b1b27-108">[out] An <xref:Microsoft.VisualStudio.OLE.Interop.IEnumUnknown> enumeration of [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interfaces corresponding to each CLR that is loaded by the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b1b27-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b1b27-109">Return Value</span></span>  

 <span data-ttu-id="b1b27-110">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="b1b27-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="b1b27-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b1b27-111">HRESULT</span></span>|<span data-ttu-id="b1b27-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b1b27-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b1b27-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="b1b27-113">S_OK</span></span>|<span data-ttu-id="b1b27-114">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="b1b27-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="b1b27-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="b1b27-115">E_POINTER</span></span>|<span data-ttu-id="b1b27-116">`ppEnumerator` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="b1b27-116">`ppEnumerator` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b1b27-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b1b27-117">Remarks</span></span>  

 <span data-ttu-id="b1b27-118">Diese Methode listet alle geladenen Runtimes auf, auch wenn Sie mit veralteten Funktionen wie [CorBindToRuntime](corbindtoruntime-function.md)geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="b1b27-118">This method is lists all loaded runtimes, even if they were loaded with deprecated functions such as [CorBindToRuntime](corbindtoruntime-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1b27-119">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b1b27-119">Requirements</span></span>  

 <span data-ttu-id="b1b27-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b1b27-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1b27-121">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="b1b27-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="b1b27-122">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="b1b27-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b1b27-123">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1b27-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1b27-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b1b27-124">See also</span></span>

- [<span data-ttu-id="b1b27-125">ICLRMetaHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b1b27-125">ICLRMetaHost Interface</span></span>](iclrmetahost-interface.md)
- [<span data-ttu-id="b1b27-126">Hosting</span><span class="sxs-lookup"><span data-stu-id="b1b27-126">Hosting</span></span>](index.md)
