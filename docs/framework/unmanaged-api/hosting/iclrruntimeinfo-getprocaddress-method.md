---
title: ICLRRuntimeInfo::GetProcAddress-Methode
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetProcAddress
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetProcAddress
helpviewer_keywords:
- GetProcAddress method [.NET Framework hosting]
- ICLRRuntimeInfo::GetProcAddress method [.NET Framework hosting]
ms.assetid: a7732bfc-689a-4926-88fd-4f81e6f9ed78
topic_type:
- apiref
ms.openlocfilehash: 028cfd51a713d8598598566a5b1edcf3fc70ecfc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732059"
---
# <a name="iclrruntimeinfogetprocaddress-method"></a><span data-ttu-id="cc95f-102">ICLRRuntimeInfo::GetProcAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="cc95f-102">ICLRRuntimeInfo::GetProcAddress Method</span></span>

<span data-ttu-id="cc95f-103">Ruft die Adresse einer angegebenen Funktion ab, die aus der Common Language Runtime (CLR) exportiert wurde, die dieser Schnittstelle zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="cc95f-103">Gets the address of a specified function that was exported from the common language runtime (CLR) associated with this interface.</span></span>  
  
 <span data-ttu-id="cc95f-104">Diese Methode löst die [GetRealProcAddress](getrealprocaddress-function.md) -Funktion aus.</span><span class="sxs-lookup"><span data-stu-id="cc95f-104">This method supersedes the [GetRealProcAddress](getrealprocaddress-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc95f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="cc95f-105">Syntax</span></span>  
  
```cpp  
HRESULT GetProcAddress(  
     [in]  LPCSTR pszProcName,  
     [out, retval] LPVOID *ppProc);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc95f-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="cc95f-106">Parameters</span></span>  

 `pszProcName`  
 <span data-ttu-id="cc95f-107">in Der Name der exportierten Funktion.</span><span class="sxs-lookup"><span data-stu-id="cc95f-107">[in] The name of the exported function.</span></span>  
  
 `ppProc`  
 <span data-ttu-id="cc95f-108">vorgenommen Die Adresse der exportierten Funktion.</span><span class="sxs-lookup"><span data-stu-id="cc95f-108">[out] The address of the exported function.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cc95f-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="cc95f-109">Return Value</span></span>  

 <span data-ttu-id="cc95f-110">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="cc95f-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="cc95f-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cc95f-111">HRESULT</span></span>|<span data-ttu-id="cc95f-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="cc95f-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cc95f-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="cc95f-113">S_OK</span></span>|<span data-ttu-id="cc95f-114">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="cc95f-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="cc95f-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="cc95f-115">E_POINTER</span></span>|<span data-ttu-id="cc95f-116">`pszProcName` oder `ppProc` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="cc95f-116">`pszProcName` or `ppProc` is null.</span></span>|  
|<span data-ttu-id="cc95f-117">CLR_E_SHIM_RUNTIMEEXPORT</span><span class="sxs-lookup"><span data-stu-id="cc95f-117">CLR_E_SHIM_RUNTIMEEXPORT</span></span>|<span data-ttu-id="cc95f-118">Die angegebene Funktion ist keine exportierte Funktion.</span><span class="sxs-lookup"><span data-stu-id="cc95f-118">The specified function is not an exported function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cc95f-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cc95f-119">Remarks</span></span>  

 <span data-ttu-id="cc95f-120">Diese Methode bewirkt, dass die CLR geladen, aber nicht initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="cc95f-120">This method causes the CLR to be loaded but not initialized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc95f-121">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="cc95f-121">Requirements</span></span>  

 <span data-ttu-id="cc95f-122">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc95f-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc95f-123">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="cc95f-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="cc95f-124">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="cc95f-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cc95f-125">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc95f-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc95f-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cc95f-126">See also</span></span>

- [<span data-ttu-id="cc95f-127">ICLRRuntimeInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cc95f-127">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="cc95f-128">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="cc95f-128">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="cc95f-129">Hosting</span><span class="sxs-lookup"><span data-stu-id="cc95f-129">Hosting</span></span>](index.md)
