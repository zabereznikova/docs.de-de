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
ms.openlocfilehash: f177d441da3bd967750781e487d9fed42bc132f5
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791945"
---
# <a name="icordebugremotetargetgethostname-method"></a><span data-ttu-id="6a5e3-102">ICorDebugRemoteTarget::GetHostName-Methode</span><span class="sxs-lookup"><span data-stu-id="6a5e3-102">ICorDebugRemoteTarget::GetHostName Method</span></span>
<span data-ttu-id="6a5e3-103">Gibt den vollqualifizierten Domänennamen oder die IPv4-Adresse des Remotedebugging-Zielcomputers zurück.</span><span class="sxs-lookup"><span data-stu-id="6a5e3-103">Returns the fully qualified domain name or IPv4 address of the remote debugging target machine.</span></span> <span data-ttu-id="6a5e3-104">IPV6 wird zurzeit nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6a5e3-104">IPV6 is not supported at this time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a5e3-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="6a5e3-105">Syntax</span></span>  
  
```cpp  
HRESULT GetHostName (  
    [in] ULONG32      cchHostName,  
    [out] ULONG32*    pcchHostName,  
    [out, size_is(cchHostName), length_is(*pcchHostName)]  
            WCHAR szHostName[]  
```  
  
## <a name="parameters"></a><span data-ttu-id="6a5e3-106">Parameters</span><span class="sxs-lookup"><span data-stu-id="6a5e3-106">Parameters</span></span>  
 `cchHostName`  
 <span data-ttu-id="6a5e3-107">[in] Die Größe des `szHostName`-Puffers in Zeichen.</span><span class="sxs-lookup"><span data-stu-id="6a5e3-107">[in] The size, in characters, of the `szHostName` buffer.</span></span> <span data-ttu-id="6a5e3-108">Wenn dieser Parameter 0 (Null) ist, muss `szHostName` NULL sein.</span><span class="sxs-lookup"><span data-stu-id="6a5e3-108">If this parameter is 0 (zero), `szHostName` must be null.</span></span>  
  
 `pcchHostName`  
 <span data-ttu-id="6a5e3-109">[out] Die Anzahl der Zeichen einschließlich eines NULL-Terminators im Hostnamen oder in der IP-Adresse.</span><span class="sxs-lookup"><span data-stu-id="6a5e3-109">[out] The number of characters, including a null terminator, in the host name or IP address.</span></span> <span data-ttu-id="6a5e3-110">Dieser Parameter kann null sein.</span><span class="sxs-lookup"><span data-stu-id="6a5e3-110">This parameter can be null.</span></span>  
  
 `szHostName`  
 <span data-ttu-id="6a5e3-111">[out] Puffer, der den Hostnamen oder die IP-Adresse enthält.</span><span class="sxs-lookup"><span data-stu-id="6a5e3-111">[out] Buffer that contains the host name or IP address.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6a5e3-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6a5e3-112">Return Value</span></span>  
 <span data-ttu-id="6a5e3-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="6a5e3-113">S_OK</span></span>  
 <span data-ttu-id="6a5e3-114">Der Hostname oder die IP-Adresse wurden erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="6a5e3-114">The host name or IP address was successfully returned.</span></span>  
  
 <span data-ttu-id="6a5e3-115">E_FAIL (oder andere E_-Rückgabecodes)</span><span class="sxs-lookup"><span data-stu-id="6a5e3-115">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="6a5e3-116">Fehler beim Zurückgeben des Hostnamens oder der IP-Adresse.</span><span class="sxs-lookup"><span data-stu-id="6a5e3-116">Unable to return the host name or IP address.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6a5e3-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6a5e3-117">Remarks</span></span>  
 <span data-ttu-id="6a5e3-118">Diese Methode wird vom Debugger-Writer implementiert.</span><span class="sxs-lookup"><span data-stu-id="6a5e3-118">This method is implemented by the debugger writer.</span></span> <span data-ttu-id="6a5e3-119">Er muss dem Paradigma für mehrere Aufrufe folgen: beim ersten Aufruf übergibt der Aufrufer NULL an `cchHostName` und `szHostName`, und `pcchHostName` gibt die Größe des erforderlichen Puffers zurück.</span><span class="sxs-lookup"><span data-stu-id="6a5e3-119">It must follow the multiple call paradigm: On the first call, the caller passes null to both `cchHostName` and `szHostName`, and `pcchHostName` returns the size of the required buffer.</span></span> <span data-ttu-id="6a5e3-120">Beim zweiten Aufruf wird die Größe, die zuvor zurückgegeben wurde, an `cchHostName` übergeben, und ein entsprechend skalierten Puffer wird an `szHostName` übergeben.</span><span class="sxs-lookup"><span data-stu-id="6a5e3-120">On the second call, the size that was previously returned is passed in `cchHostName`, and an appropriately sized buffer is passed in `szHostName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a5e3-121">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6a5e3-121">Requirements</span></span>  
 <span data-ttu-id="6a5e3-122">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6a5e3-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a5e3-123">**Header:** Cordebug. idl</span><span class="sxs-lookup"><span data-stu-id="6a5e3-123">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="6a5e3-124">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6a5e3-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6a5e3-125">**.NET Framework Versionen:** 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="6a5e3-125">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a5e3-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6a5e3-126">See also</span></span>

- [<span data-ttu-id="6a5e3-127">ICorDebugRemoteTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6a5e3-127">ICorDebugRemoteTarget Interface</span></span>](icordebugremotetarget-interface.md)
- [<span data-ttu-id="6a5e3-128">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6a5e3-128">ICorDebug Interface</span></span>](icordebug-interface.md)
