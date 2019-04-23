---
title: ICorDebugRemoteTarget::GetHostName-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugRemoteTarget.GetHostName
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget::GetHostName
helpviewer_keywords:
- ICorDebugRemoteTarget::GetHostName method [.NET Framework debugging]
- GetHostName method, ICorDebugRemoteTarget interface [.NET Framework debugging]
ms.assetid: 1c7276f7-7e54-470c-808c-e13745ac07a1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0ca7aee79b5b8c3d58b4beb8f1ff886a7d55afab
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59127581"
---
# <a name="icordebugremotetargetgethostname-method"></a><span data-ttu-id="5b484-102">ICorDebugRemoteTarget::GetHostName-Methode</span><span class="sxs-lookup"><span data-stu-id="5b484-102">ICorDebugRemoteTarget::GetHostName Method</span></span>
<span data-ttu-id="5b484-103">Gibt den vollqualifizierten Domänennamen oder die IPv4-Adresse des Remotedebugging-Zielcomputers zurück.</span><span class="sxs-lookup"><span data-stu-id="5b484-103">Returns the fully qualified domain name or IPv4 address of the remote debugging target machine.</span></span> <span data-ttu-id="5b484-104">IPV6 wird zurzeit nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5b484-104">IPV6 is not supported at this time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b484-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="5b484-105">Syntax</span></span>  
  
```  
HRESULT GetHostName (  
    [in] ULONG32      cchHostName,  
    [out] ULONG32*    pcchHostName,  
    [out, size_is(cchHostName), length_is(*pcchHostName)]  
            WCHAR szHostName[]  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b484-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="5b484-106">Parameters</span></span>  
 `cchHostName`  
 <span data-ttu-id="5b484-107">[in] Die Größe des `szHostName`-Puffers in Zeichen.</span><span class="sxs-lookup"><span data-stu-id="5b484-107">[in] The size, in characters, of the `szHostName` buffer.</span></span> <span data-ttu-id="5b484-108">Wenn dieser Parameter 0 (Null) ist, muss `szHostName` NULL sein.</span><span class="sxs-lookup"><span data-stu-id="5b484-108">If this parameter is 0 (zero), `szHostName` must be null.</span></span>  
  
 `pcchHostName`  
 <span data-ttu-id="5b484-109">[out] Die Anzahl der Zeichen einschließlich eines NULL-Terminators im Hostnamen oder in der IP-Adresse.</span><span class="sxs-lookup"><span data-stu-id="5b484-109">[out] The number of characters, including a null terminator, in the host name or IP address.</span></span> <span data-ttu-id="5b484-110">Dieser Parameter kann NULL sein.</span><span class="sxs-lookup"><span data-stu-id="5b484-110">This parameter can be null.</span></span>  
  
 `szHostName`  
 <span data-ttu-id="5b484-111">[out] Puffer, der den Hostnamen oder die IP-Adresse enthält.</span><span class="sxs-lookup"><span data-stu-id="5b484-111">[out] Buffer that contains the host name or IP address.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5b484-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5b484-112">Return Value</span></span>  
 <span data-ttu-id="5b484-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="5b484-113">S_OK</span></span>  
 <span data-ttu-id="5b484-114">Der Hostname oder die IP-Adresse wurden erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="5b484-114">The host name or IP address was successfully returned.</span></span>  
  
 <span data-ttu-id="5b484-115">E_FAIL (oder andere E_-Rückgabecodes)</span><span class="sxs-lookup"><span data-stu-id="5b484-115">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="5b484-116">Fehler beim Zurückgeben des Hostnamens oder der IP-Adresse.</span><span class="sxs-lookup"><span data-stu-id="5b484-116">Unable to return the host name or IP address.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5b484-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5b484-117">Remarks</span></span>  
 <span data-ttu-id="5b484-118">Diese Methode wird vom Debugger-Writer implementiert.</span><span class="sxs-lookup"><span data-stu-id="5b484-118">This method is implemented by the debugger writer.</span></span> <span data-ttu-id="5b484-119">Dieser Name muss das Paradigma für mehrere Aufrufe entsprechen: Beim ersten Aufruf übergibt der Aufrufer sowohl `cchHostName` und `szHostName`, und `pcchHostName` gibt die Größe des erforderlichen Puffers zurück.</span><span class="sxs-lookup"><span data-stu-id="5b484-119">It must follow the multiple call paradigm: On the first call, the caller passes null to both `cchHostName` and `szHostName`, and `pcchHostName` returns the size of the required buffer.</span></span> <span data-ttu-id="5b484-120">Beim zweiten Aufruf wird die Größe, die zuvor zurückgegeben wurde, an `cchHostName` übergeben, und ein entsprechend skalierten Puffer wird an `szHostName` übergeben.</span><span class="sxs-lookup"><span data-stu-id="5b484-120">On the second call, the size that was previously returned is passed in `cchHostName`, and an appropriately sized buffer is passed in `szHostName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b484-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5b484-121">Requirements</span></span>  
 <span data-ttu-id="5b484-122">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b484-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b484-123">**Header:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="5b484-123">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="5b484-124">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5b484-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5b484-125">**.NET Framework-Versionen:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="5b484-125">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b484-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5b484-126">See also</span></span>

- [<span data-ttu-id="5b484-127">ICorDebugRemoteTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5b484-127">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)
- [<span data-ttu-id="5b484-128">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5b484-128">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
