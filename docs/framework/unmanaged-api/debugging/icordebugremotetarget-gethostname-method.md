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
ms.openlocfilehash: 1536a89d0e85480d3829939c40cd986fe65883df
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422470"
---
# <a name="icordebugremotetargetgethostname-method"></a><span data-ttu-id="fa5f2-102">ICorDebugRemoteTarget::GetHostName-Methode</span><span class="sxs-lookup"><span data-stu-id="fa5f2-102">ICorDebugRemoteTarget::GetHostName Method</span></span>
<span data-ttu-id="fa5f2-103">Gibt den vollqualifizierten Domänennamen oder die IPv4-Adresse des Remotedebugging-Zielcomputers zurück.</span><span class="sxs-lookup"><span data-stu-id="fa5f2-103">Returns the fully qualified domain name or IPv4 address of the remote debugging target machine.</span></span> <span data-ttu-id="fa5f2-104">IPV6 wird zurzeit nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fa5f2-104">IPV6 is not supported at this time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa5f2-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="fa5f2-105">Syntax</span></span>  
  
```  
HRESULT GetHostName (  
    [in] ULONG32      cchHostName,  
    [out] ULONG32*    pcchHostName,  
    [out, size_is(cchHostName), length_is(*pcchHostName)]  
            WCHAR szHostName[]  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fa5f2-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="fa5f2-106">Parameters</span></span>  
 `cchHostName`  
 <span data-ttu-id="fa5f2-107">[in] Die Größe des `szHostName`-Puffers in Zeichen.</span><span class="sxs-lookup"><span data-stu-id="fa5f2-107">[in] The size, in characters, of the `szHostName` buffer.</span></span> <span data-ttu-id="fa5f2-108">Wenn dieser Parameter 0 (Null) ist, muss `szHostName` NULL sein.</span><span class="sxs-lookup"><span data-stu-id="fa5f2-108">If this parameter is 0 (zero), `szHostName` must be null.</span></span>  
  
 `pcchHostName`  
 <span data-ttu-id="fa5f2-109">[out] Die Anzahl der Zeichen einschließlich eines NULL-Terminators im Hostnamen oder in der IP-Adresse.</span><span class="sxs-lookup"><span data-stu-id="fa5f2-109">[out] The number of characters, including a null terminator, in the host name or IP address.</span></span> <span data-ttu-id="fa5f2-110">Dieser Parameter kann NULL sein.</span><span class="sxs-lookup"><span data-stu-id="fa5f2-110">This parameter can be null.</span></span>  
  
 `szHostName`  
 <span data-ttu-id="fa5f2-111">[out] Puffer, der den Hostnamen oder die IP-Adresse enthält.</span><span class="sxs-lookup"><span data-stu-id="fa5f2-111">[out] Buffer that contains the host name or IP address.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fa5f2-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="fa5f2-112">Return Value</span></span>  
 <span data-ttu-id="fa5f2-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="fa5f2-113">S_OK</span></span>  
 <span data-ttu-id="fa5f2-114">Der Hostname oder die IP-Adresse wurden erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="fa5f2-114">The host name or IP address was successfully returned.</span></span>  
  
 <span data-ttu-id="fa5f2-115">E_FAIL (oder andere E_-Rückgabecodes)</span><span class="sxs-lookup"><span data-stu-id="fa5f2-115">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="fa5f2-116">Fehler beim Zurückgeben des Hostnamens oder der IP-Adresse.</span><span class="sxs-lookup"><span data-stu-id="fa5f2-116">Unable to return the host name or IP address.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa5f2-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fa5f2-117">Remarks</span></span>  
 <span data-ttu-id="fa5f2-118">Diese Methode wird vom Debugger-Writer implementiert.</span><span class="sxs-lookup"><span data-stu-id="fa5f2-118">This method is implemented by the debugger writer.</span></span> <span data-ttu-id="fa5f2-119">Sie muss dem Paradigma für mehrere Aufrufe entsprechen: Beim ersten Aufruf übergibt der Aufrufer sowohl `cchHostName` als auch `szHostName`, und `pcchHostName` gibt die Größe des erforderlichen Puffers zurück.</span><span class="sxs-lookup"><span data-stu-id="fa5f2-119">It must follow the multiple call paradigm: On the first call, the caller passes null to both `cchHostName` and `szHostName`, and `pcchHostName` returns the size of the required buffer .</span></span> <span data-ttu-id="fa5f2-120">Beim zweiten Aufruf wird die Größe, die zuvor zurückgegeben wurde, an `cchHostName` übergeben, und ein entsprechend skalierten Puffer wird an `szHostName` übergeben.</span><span class="sxs-lookup"><span data-stu-id="fa5f2-120">On the second call, the size that was previously returned is passed in `cchHostName`, and an appropriately sized buffer is passed in `szHostName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa5f2-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fa5f2-121">Requirements</span></span>  
 <span data-ttu-id="fa5f2-122">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa5f2-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa5f2-123">**Header:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="fa5f2-123">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="fa5f2-124">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fa5f2-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fa5f2-125">**.NET Framework-Versionen:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="fa5f2-125">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa5f2-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fa5f2-126">See Also</span></span>  
 [<span data-ttu-id="fa5f2-127">ICorDebugRemoteTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fa5f2-127">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)  
 [<span data-ttu-id="fa5f2-128">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fa5f2-128">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
