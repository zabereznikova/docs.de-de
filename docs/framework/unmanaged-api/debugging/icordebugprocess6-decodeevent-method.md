---
title: ICorDebugProcess6::DecodeEvent-Methode
ms.date: 03/30/2017
ms.assetid: 1453bc0c-6e0d-4d5a-b176-22607f8a3e6c
ms.openlocfilehash: ed75b3c5657fed805f187285a576b81598be331c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690277"
---
# <a name="icordebugprocess6decodeevent-method"></a><span data-ttu-id="d48bb-102">ICorDebugProcess6::DecodeEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="d48bb-102">ICorDebugProcess6::DecodeEvent Method</span></span>

<span data-ttu-id="d48bb-103">Decodiert verwaltete Debug-Ereignisse, die in den Nutzdaten der speziell gestalteten systemeigenen Ausnahme-Debug-Ereignissen gekapselt sind.</span><span class="sxs-lookup"><span data-stu-id="d48bb-103">Decodes managed debug events that have been encapsulated in the payload of specially crafted native exception debug events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d48bb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d48bb-104">Syntax</span></span>  
  
```cpp  
HRESULT DecodeEvent(  
        [in, length_is(countBytes), size_is(countBytes)]  const BYTE pRecord[],  
        [in] DWORD countBytes,  
        [in] CorDebugRecordFormat format,  
        [in] DWORD dwFlags,
        [in] DWORD dwThreadId,
        [out] ICorDebugDebugEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d48bb-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d48bb-105">Parameters</span></span>  

 `pRecord`  
 <span data-ttu-id="d48bb-106">[in] Ein Zeiger auf ein Byte-Array aus einem systemeigenen Ausnahme-Debug-Ereignis, das Informationen über ein verwaltetes Debug-Ereignis enthält.</span><span class="sxs-lookup"><span data-stu-id="d48bb-106">[in] A pointer to a byte array from a native exception debug event that includes information about a managed debug event.</span></span>  
  
 `countBytes`  
 <span data-ttu-id="d48bb-107">[in] Die Anzahl der Elemente im `pRecord`-Bytearray.</span><span class="sxs-lookup"><span data-stu-id="d48bb-107">[in] The number of elements in the `pRecord` byte array.</span></span>  
  
 `format`  
 <span data-ttu-id="d48bb-108">in Ein [cordebugrecordformat](cordebugrecordformat-enumeration.md) -Enumerationsmember, der das Format des nicht verwalteten Debug-Ereignisses angibt.</span><span class="sxs-lookup"><span data-stu-id="d48bb-108">[in] A [CorDebugRecordFormat](cordebugrecordformat-enumeration.md) enumeration member that specifies the format of the unmanaged debug event.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="d48bb-109">[in] Ein Bitfeld, das von der Zielarchitektur abhängt und zusätzliche Informationen über das Debug-Ereignis enthält.</span><span class="sxs-lookup"><span data-stu-id="d48bb-109">[in] A bit field that depends on the target architecture and that specifies additional information about the debug event.</span></span> <span data-ttu-id="d48bb-110">Bei Windows-Systemen kann es ein Member der [cordebugdecodeeventflagswindows](cordebugdecodeeventflagswindows-enumeration.md) -Enumeration sein.</span><span class="sxs-lookup"><span data-stu-id="d48bb-110">For Windows systems, it can be a member of the [CorDebugDecodeEventFlagsWindows](cordebugdecodeeventflagswindows-enumeration.md) enumeration.</span></span>  
  
 `dwThreadId`  
 <span data-ttu-id="d48bb-111">[in] Die Betriebssystem-ID des Threads, in dem die Ausnahme ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="d48bb-111">[in] The operating system identifier of the thread on which the exception was thrown.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="d48bb-112">vorgenommen Ein Zeiger auf die Adresse eines [icordebugdebugevent](icordebugdebugevent-interface.md) -Objekts, das ein decodierte verwaltetes Debugereignis darstellt.</span><span class="sxs-lookup"><span data-stu-id="d48bb-112">[out] A pointer to the address of an [ICorDebugDebugEvent](icordebugdebugevent-interface.md) object that represents a decoded managed debug event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d48bb-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d48bb-113">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d48bb-114">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d48bb-114">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d48bb-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d48bb-115">Requirements</span></span>  

 <span data-ttu-id="d48bb-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d48bb-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d48bb-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d48bb-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d48bb-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d48bb-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d48bb-119">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d48bb-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d48bb-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d48bb-120">See also</span></span>

- [<span data-ttu-id="d48bb-121">ICorDebugProcess6-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d48bb-121">ICorDebugProcess6 Interface</span></span>](icordebugprocess6-interface.md)
- [<span data-ttu-id="d48bb-122">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="d48bb-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
