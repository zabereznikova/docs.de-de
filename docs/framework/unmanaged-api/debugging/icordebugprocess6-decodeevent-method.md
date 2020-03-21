---
title: ICorDebugProcess6::DecodeEvent-Methode
ms.date: 03/30/2017
ms.assetid: 1453bc0c-6e0d-4d5a-b176-22607f8a3e6c
ms.openlocfilehash: a0b77724a5a70461073d554a9794c5a904f6a363
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178581"
---
# <a name="icordebugprocess6decodeevent-method"></a><span data-ttu-id="542fe-102">ICorDebugProcess6::DecodeEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="542fe-102">ICorDebugProcess6::DecodeEvent Method</span></span>
<span data-ttu-id="542fe-103">Decodiert verwaltete Debug-Ereignisse, die in den Nutzdaten der speziell gestalteten systemeigenen Ausnahme-Debug-Ereignissen gekapselt sind.</span><span class="sxs-lookup"><span data-stu-id="542fe-103">Decodes managed debug events that have been encapsulated in the payload of specially crafted native exception debug events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="542fe-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="542fe-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="542fe-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="542fe-105">Parameters</span></span>  
 `pRecord`  
 <span data-ttu-id="542fe-106">[in] Ein Zeiger auf ein Byte-Array aus einem systemeigenen Ausnahme-Debug-Ereignis, das Informationen über ein verwaltetes Debug-Ereignis enthält.</span><span class="sxs-lookup"><span data-stu-id="542fe-106">[in] A pointer to a byte array from a native exception debug event that includes information about a managed debug event.</span></span>  
  
 `countBytes`  
 <span data-ttu-id="542fe-107">[in] Die Anzahl der Elemente im `pRecord`-Bytearray.</span><span class="sxs-lookup"><span data-stu-id="542fe-107">[in] The number of elements in the `pRecord` byte array.</span></span>  
  
 `format`  
 <span data-ttu-id="542fe-108">[in] Ein [CorDebugRecordFormat](cordebugrecordformat-enumeration.md) CorDebugRecordFormat-Enumerationsmember, der das Format des nicht verwalteten Debugereignisses angibt.</span><span class="sxs-lookup"><span data-stu-id="542fe-108">[in] A [CorDebugRecordFormat](cordebugrecordformat-enumeration.md) enumeration member that specifies the format of the unmanaged debug event.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="542fe-109">[in] Ein Bitfeld, das von der Zielarchitektur abhängt und zusätzliche Informationen über das Debug-Ereignis enthält.</span><span class="sxs-lookup"><span data-stu-id="542fe-109">[in] A bit field that depends on the target architecture and that specifies additional information about the debug event.</span></span> <span data-ttu-id="542fe-110">Für Windows-Systeme kann es ein Mitglied der [CorDebugDecodeEventFlagsWindows-Enumeration](cordebugdecodeeventflagswindows-enumeration.md) sein.</span><span class="sxs-lookup"><span data-stu-id="542fe-110">For Windows systems, it can be a member of the [CorDebugDecodeEventFlagsWindows](cordebugdecodeeventflagswindows-enumeration.md) enumeration.</span></span>  
  
 `dwThreadId`  
 <span data-ttu-id="542fe-111">[in] Die Betriebssystem-ID des Threads, in dem die Ausnahme ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="542fe-111">[in] The operating system identifier of the thread on which the exception was thrown.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="542fe-112">[out] Ein Zeiger auf die Adresse eines [ICorDebugDebugEvent-Objekts,](icordebugdebugevent-interface.md) das ein decodiertes verwaltetes Debugereignis darstellt.</span><span class="sxs-lookup"><span data-stu-id="542fe-112">[out] A pointer to the address of an [ICorDebugDebugEvent](icordebugdebugevent-interface.md) object that represents a decoded managed debug event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="542fe-113">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="542fe-113">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="542fe-114">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="542fe-114">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="542fe-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="542fe-115">Requirements</span></span>  
 <span data-ttu-id="542fe-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="542fe-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="542fe-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="542fe-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="542fe-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="542fe-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="542fe-119">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="542fe-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="542fe-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="542fe-120">See also</span></span>

- [<span data-ttu-id="542fe-121">ICorDebugProcess6-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="542fe-121">ICorDebugProcess6 Interface</span></span>](icordebugprocess6-interface.md)
- [<span data-ttu-id="542fe-122">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="542fe-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
