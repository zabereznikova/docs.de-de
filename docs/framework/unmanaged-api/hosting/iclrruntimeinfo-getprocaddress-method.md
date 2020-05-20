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
ms.openlocfilehash: 2690a5c2e7c499d68ef9e903c62bff8f85e72e8e
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703866"
---
# <a name="iclrruntimeinfogetprocaddress-method"></a><span data-ttu-id="fef7a-102">ICLRRuntimeInfo::GetProcAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="fef7a-102">ICLRRuntimeInfo::GetProcAddress Method</span></span>
<span data-ttu-id="fef7a-103">Ruft die Adresse einer angegebenen Funktion ab, die aus der Common Language Runtime (CLR) exportiert wurde, die dieser Schnittstelle zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="fef7a-103">Gets the address of a specified function that was exported from the common language runtime (CLR) associated with this interface.</span></span>  
  
 <span data-ttu-id="fef7a-104">Diese Methode löst die [GetRealProcAddress](getrealprocaddress-function.md) -Funktion aus.</span><span class="sxs-lookup"><span data-stu-id="fef7a-104">This method supersedes the [GetRealProcAddress](getrealprocaddress-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fef7a-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="fef7a-105">Syntax</span></span>  
  
```cpp  
HRESULT GetProcAddress(  
     [in]  LPCSTR pszProcName,  
     [out, retval] LPVOID *ppProc);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fef7a-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="fef7a-106">Parameters</span></span>  
 `pszProcName`  
 <span data-ttu-id="fef7a-107">in Der Name der exportierten Funktion.</span><span class="sxs-lookup"><span data-stu-id="fef7a-107">[in] The name of the exported function.</span></span>  
  
 `ppProc`  
 <span data-ttu-id="fef7a-108">vorgenommen Die Adresse der exportierten Funktion.</span><span class="sxs-lookup"><span data-stu-id="fef7a-108">[out] The address of the exported function.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fef7a-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="fef7a-109">Return Value</span></span>  
 <span data-ttu-id="fef7a-110">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="fef7a-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="fef7a-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fef7a-111">HRESULT</span></span>|<span data-ttu-id="fef7a-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="fef7a-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fef7a-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="fef7a-113">S_OK</span></span>|<span data-ttu-id="fef7a-114">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="fef7a-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="fef7a-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="fef7a-115">E_POINTER</span></span>|<span data-ttu-id="fef7a-116">`pszProcName` oder `ppProc` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="fef7a-116">`pszProcName` or `ppProc` is null.</span></span>|  
|<span data-ttu-id="fef7a-117">CLR_E_SHIM_RUNTIMEEXPORT</span><span class="sxs-lookup"><span data-stu-id="fef7a-117">CLR_E_SHIM_RUNTIMEEXPORT</span></span>|<span data-ttu-id="fef7a-118">Die angegebene Funktion ist keine exportierte Funktion.</span><span class="sxs-lookup"><span data-stu-id="fef7a-118">The specified function is not an exported function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fef7a-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fef7a-119">Remarks</span></span>  
 <span data-ttu-id="fef7a-120">Diese Methode bewirkt, dass die CLR geladen, aber nicht initialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="fef7a-120">This method causes the CLR to be loaded but not initialized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fef7a-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fef7a-121">Requirements</span></span>  
 <span data-ttu-id="fef7a-122">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fef7a-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fef7a-123">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="fef7a-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="fef7a-124">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="fef7a-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fef7a-125">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fef7a-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fef7a-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fef7a-126">See also</span></span>

- [<span data-ttu-id="fef7a-127">ICLRRuntimeInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fef7a-127">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="fef7a-128">Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="fef7a-128">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="fef7a-129">Hosting</span><span class="sxs-lookup"><span data-stu-id="fef7a-129">Hosting</span></span>](index.md)
