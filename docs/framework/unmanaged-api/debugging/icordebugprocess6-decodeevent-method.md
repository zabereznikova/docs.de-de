---
title: ICorDebugProcess6::DecodeEvent-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 1453bc0c-6e0d-4d5a-b176-22607f8a3e6c
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c0186fb91a4c47f1988af58577cee1b7a64987a3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess6decodeevent-method"></a><span data-ttu-id="9a855-102">ICorDebugProcess6::DecodeEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="9a855-102">ICorDebugProcess6::DecodeEvent Method</span></span>
<span data-ttu-id="9a855-103">Decodiert verwaltete Debug-Ereignisse, die in den Nutzdaten der speziell gestalteten systemeigenen Ausnahme-Debug-Ereignissen gekapselt sind.</span><span class="sxs-lookup"><span data-stu-id="9a855-103">Decodes managed debug events that have been encapsulated in the payload of specially crafted native exception debug events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a855-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9a855-104">Syntax</span></span>  
  
```  
HRESULT DecodeEvent(  
        [in, length_is(countBytes), size_is(countBytes)]  const BYTE pRecord[],  
        [in] DWORD countBytes,  
        [in] CorDebugRecordFormat format,  
        [in] DWORD dwFlags,   
        [in] DWORD dwThreadId,   
        [out] ICorDebugDebugEvent **ppEvent  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9a855-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9a855-105">Parameters</span></span>  
 `pRecord`  
 <span data-ttu-id="9a855-106">[in] Ein Zeiger auf ein Byte-Array aus einem systemeigenen Ausnahme-Debug-Ereignis, das Informationen über ein verwaltetes Debug-Ereignis enthält.</span><span class="sxs-lookup"><span data-stu-id="9a855-106">[in] A pointer to a byte array from a native exception debug event that includes information about a managed debug event.</span></span>  
  
 `countBytes`  
 <span data-ttu-id="9a855-107">[in] Die Anzahl der Elemente im `pRecord`-Bytearray.</span><span class="sxs-lookup"><span data-stu-id="9a855-107">[in] The number of elements in the `pRecord` byte array.</span></span>  
  
 `format`  
 <span data-ttu-id="9a855-108">[in] Ein [CorDebugRecordFormat](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md) Enumerationsmember, der das Format der nicht verwalteten Debug-Ereignis angibt.</span><span class="sxs-lookup"><span data-stu-id="9a855-108">[in] A [CorDebugRecordFormat](../../../../docs/framework/unmanaged-api/debugging/cordebugrecordformat-enumeration.md) enumeration member that specifies the format of the unmanaged debug event.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="9a855-109">[in] Ein Bitfeld, das von der Zielarchitektur abhängt und zusätzliche Informationen über das Debug-Ereignis enthält.</span><span class="sxs-lookup"><span data-stu-id="9a855-109">[in] A bit field that depends on the target architecture and that specifies additional information about the debug event.</span></span> <span data-ttu-id="9a855-110">Für Windows-Systemen kann es ein Mitglied der [CorDebugDecodeEventFlagsWindows](../../../../docs/framework/unmanaged-api/debugging/cordebugdecodeeventflagswindows-enumeration.md) Enumeration.</span><span class="sxs-lookup"><span data-stu-id="9a855-110">For Windows systems, it can be a member of the [CorDebugDecodeEventFlagsWindows](../../../../docs/framework/unmanaged-api/debugging/cordebugdecodeeventflagswindows-enumeration.md) enumeration.</span></span>  
  
 `dwThreadId`  
 <span data-ttu-id="9a855-111">[in] Die Betriebssystem-ID des Threads, in dem die Ausnahme ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="9a855-111">[in] The operating system identifier of the thread on which the exception was thrown.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="9a855-112">[out] Ein Zeiger auf die Adresse des ein [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) -Objekt, das ein decodiertes verwaltetes Debug-Ereignis darstellt.</span><span class="sxs-lookup"><span data-stu-id="9a855-112">[out] A pointer to the address of an [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) object that represents a decoded managed debug event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9a855-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9a855-113">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9a855-114">Diese Methode ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9a855-114">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a855-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9a855-115">Requirements</span></span>  
 <span data-ttu-id="9a855-116">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a855-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a855-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9a855-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9a855-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9a855-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a855-119">**.NET Framework-Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a855-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a855-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9a855-120">See Also</span></span>  
 [<span data-ttu-id="9a855-121">ICorDebugProcess6-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9a855-121">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)  
 [<span data-ttu-id="9a855-122">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="9a855-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
