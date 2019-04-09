---
title: ICorDebugValue3::GetSize64-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugValue3::GetSize64
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue3::GetSize64
helpviewer_keywords:
- GetSize64 method, ICorDebugValue3 interface [.NET Framework debugging]
- ICorDebugValue3::GetSize64 method [.NET Framework debugging]
ms.assetid: fee56a29-3154-4192-958d-71da2ced3740
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7c0b45e08f7b88d9374023f95c6e3e22139c8949
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59144767"
---
# <a name="icordebugvalue3getsize64-method"></a><span data-ttu-id="08351-102">ICorDebugValue3::GetSize64-Methode</span><span class="sxs-lookup"><span data-stu-id="08351-102">ICorDebugValue3::GetSize64 Method</span></span>
<span data-ttu-id="08351-103">Ruft die Größe in Bytes, davon [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) Objekt.</span><span class="sxs-lookup"><span data-stu-id="08351-103">Gets the size, in bytes, of this [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08351-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="08351-104">Syntax</span></span>  
  
```  
HRESULT GetSize64(  
    [out] ULONG64 *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="08351-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="08351-105">Parameters</span></span>  
 <span data-ttu-id="08351-106">pSize</span><span class="sxs-lookup"><span data-stu-id="08351-106">pSize</span></span>  
 <span data-ttu-id="08351-107">[out] Ein Zeiger auf die Größe in Bytes, der dieses Objekt.</span><span class="sxs-lookup"><span data-stu-id="08351-107">[out] A pointer to the size, in bytes, of this object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="08351-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="08351-108">Remarks</span></span>  
 <span data-ttu-id="08351-109">Wenn der Typ des Werts ein Verweistyp ist, gibt diese Methode auf, die Größe des Zeigers, anstatt die Größe des Objekts.</span><span class="sxs-lookup"><span data-stu-id="08351-109">If this value's type is a reference type, this method returns the size of the pointer rather than the size of the object.</span></span>  
  
 <span data-ttu-id="08351-110">Die `ICorDebugValue3::GetSize` Methode unterscheidet sich von der [ICorDebugValue:: GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md) -Methode in den Typ des als Output-Parameter.</span><span class="sxs-lookup"><span data-stu-id="08351-110">The `ICorDebugValue3::GetSize` method differs from the [ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md) method in the type of its output parameter.</span></span> <span data-ttu-id="08351-111">In [ICorDebugValue:: GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md), der Ausgabeparameter ist eine `ULONG32`; in `ICorDebugValue3::GetSize`, es ist ein `ULONG64`.</span><span class="sxs-lookup"><span data-stu-id="08351-111">In [ICorDebugValue::GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md), the output parameter is a `ULONG32`; in `ICorDebugValue3::GetSize`, it is a `ULONG64`.</span></span> <span data-ttu-id="08351-112">Dies ermöglicht die [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) Schnittstelle, um die Größe des Arrays zu melden, die 2 GB nicht überschreiten.</span><span class="sxs-lookup"><span data-stu-id="08351-112">This enables the [ICorDebugValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md) interface to report the size of arrays that exceed 2GB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08351-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="08351-113">Requirements</span></span>  
 <span data-ttu-id="08351-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08351-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08351-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="08351-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="08351-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="08351-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="08351-117">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="08351-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="08351-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="08351-118">See also</span></span>

- [<span data-ttu-id="08351-119">ICorDebugValue3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="08351-119">ICorDebugValue3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)
- [<span data-ttu-id="08351-120">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="08351-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
