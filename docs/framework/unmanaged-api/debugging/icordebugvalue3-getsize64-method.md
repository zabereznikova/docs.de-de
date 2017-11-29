---
title: ICorDebugValue3::GetSize64-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugValue3::GetSize64
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugValue3::GetSize64
helpviewer_keywords:
- GetSize64 method, ICorDebugValue3 interface [.NET Framework debugging]
- ICorDebugValue3::GetSize64 method [.NET Framework debugging]
ms.assetid: fee56a29-3154-4192-958d-71da2ced3740
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b129ebe666972052775c2c3e44e38bb6a25a176e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugvalue3getsize64-method"></a><span data-ttu-id="717dd-102">ICorDebugValue3::GetSize64-Methode</span><span class="sxs-lookup"><span data-stu-id="717dd-102">ICorDebugValue3::GetSize64 Method</span></span>
<span data-ttu-id="717dd-103">Ruft die Größe in Bytes dieses [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) Objekt.</span><span class="sxs-lookup"><span data-stu-id="717dd-103">Gets the size, in bytes, of this [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="717dd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="717dd-104">Syntax</span></span>  
  
```  
HRESULT GetSize64(  
    [out] ULONG64 *pSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="717dd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="717dd-105">Parameters</span></span>  
 <span data-ttu-id="717dd-106">pSize</span><span class="sxs-lookup"><span data-stu-id="717dd-106">pSize</span></span>  
 <span data-ttu-id="717dd-107">[out] Ein Zeiger auf die Größe in Bytes, der dieses Objekt.</span><span class="sxs-lookup"><span data-stu-id="717dd-107">[out] A pointer to the size, in bytes, of this object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="717dd-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="717dd-108">Remarks</span></span>  
 <span data-ttu-id="717dd-109">Wenn dieser Wert Typ ein Verweistyp ist, gibt diese Methode die Größe des Zeigers statt der Größe des Objekts.</span><span class="sxs-lookup"><span data-stu-id="717dd-109">If this value's type is a reference type, this method returns the size of the pointer rather than the size of the object.</span></span>  
  
 <span data-ttu-id="717dd-110">Die `ICorDebugValue3::GetSize` -Methode unterscheidet sich von der [ICorDebugValue:: GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md) Methode in der Art von der Output-Parameter.</span><span class="sxs-lookup"><span data-stu-id="717dd-110">The `ICorDebugValue3::GetSize` method differs from the [ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md) method in the type of its output parameter.</span></span> <span data-ttu-id="717dd-111">In [ICorDebugValue:: GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md), die Output-Parameter ist ein `ULONG32`, in `ICorDebugValue3::GetSize`, es ist eine `ULONG64`.</span><span class="sxs-lookup"><span data-stu-id="717dd-111">In [ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md), the output parameter is a `ULONG32`; in `ICorDebugValue3::GetSize`, it is a `ULONG64`.</span></span> <span data-ttu-id="717dd-112">Dies ermöglicht die [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) Schnittstelle, um die Größe des Arrays zu melden, die 2 GB nicht überschreiten.</span><span class="sxs-lookup"><span data-stu-id="717dd-112">This enables the [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) interface to report the size of arrays that exceed 2GB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="717dd-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="717dd-113">Requirements</span></span>  
 <span data-ttu-id="717dd-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="717dd-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="717dd-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="717dd-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="717dd-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="717dd-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="717dd-117">**.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="717dd-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="717dd-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="717dd-118">See Also</span></span>  
 [<span data-ttu-id="717dd-119">ICorDebugValue3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="717dd-119">ICorDebugValue3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)  
 [<span data-ttu-id="717dd-120">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="717dd-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
