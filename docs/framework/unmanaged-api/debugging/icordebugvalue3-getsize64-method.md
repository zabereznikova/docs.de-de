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
ms.openlocfilehash: d1d057d38e16503175138c6ec978eb6c1f12bc6d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722335"
---
# <a name="icordebugvalue3getsize64-method"></a><span data-ttu-id="df60c-102">ICorDebugValue3::GetSize64-Methode</span><span class="sxs-lookup"><span data-stu-id="df60c-102">ICorDebugValue3::GetSize64 Method</span></span>

<span data-ttu-id="df60c-103">Ruft die Größe des [ICorDebugValue3](icordebugvalue3-interface.md) -Objekts in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="df60c-103">Gets the size, in bytes, of this [ICorDebugValue3](icordebugvalue3-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df60c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="df60c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize64(  
    [out] ULONG64 *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df60c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="df60c-105">Parameters</span></span>  

 <span data-ttu-id="df60c-106">Psize</span><span class="sxs-lookup"><span data-stu-id="df60c-106">pSize</span></span>  
 <span data-ttu-id="df60c-107">vorgenommen Ein Zeiger auf die Größe dieses-Objekts in Bytes.</span><span class="sxs-lookup"><span data-stu-id="df60c-107">[out] A pointer to the size, in bytes, of this object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="df60c-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="df60c-108">Remarks</span></span>  

 <span data-ttu-id="df60c-109">Wenn der Typ dieses Werts ein Referenztyp ist, gibt diese Methode die Größe des Zeigers anstelle der Größe des-Objekts zurück.</span><span class="sxs-lookup"><span data-stu-id="df60c-109">If this value's type is a reference type, this method returns the size of the pointer rather than the size of the object.</span></span>  
  
 <span data-ttu-id="df60c-110">Die- `ICorDebugValue3::GetSize` Methode unterscheidet sich von der [ICorDebugValue:: GetSize](icordebugvalue-getsize-method.md) -Methode im Typ des Ausgabe Parameters.</span><span class="sxs-lookup"><span data-stu-id="df60c-110">The `ICorDebugValue3::GetSize` method differs from the [ICorDebugValue::GetSize](icordebugvalue-getsize-method.md) method in the type of its output parameter.</span></span> <span data-ttu-id="df60c-111">In [ICorDebugValue:: GetSize](icordebugvalue-getsize-method.md)ist der Ausgabeparameter ein `ULONG32` `ICorDebugValue3::GetSize` . in ist es ein `ULONG64` .</span><span class="sxs-lookup"><span data-stu-id="df60c-111">In [ICorDebugValue::GetSize](icordebugvalue-getsize-method.md), the output parameter is a `ULONG32`; in `ICorDebugValue3::GetSize`, it is a `ULONG64`.</span></span> <span data-ttu-id="df60c-112">Dadurch kann die [ICorDebugValue3](icordebugvalue3-interface.md) -Schnittstelle die Größe von Arrays melden, die größer als 2 GB sind.</span><span class="sxs-lookup"><span data-stu-id="df60c-112">This enables the [ICorDebugValue3](icordebugvalue3-interface.md) interface to report the size of arrays that exceed 2GB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df60c-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="df60c-113">Requirements</span></span>  

 <span data-ttu-id="df60c-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df60c-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df60c-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="df60c-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="df60c-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="df60c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="df60c-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df60c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df60c-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="df60c-118">See also</span></span>

- [<span data-ttu-id="df60c-119">ICorDebugValue3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="df60c-119">ICorDebugValue3 Interface</span></span>](icordebugvalue3-interface.md)
- [<span data-ttu-id="df60c-120">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="df60c-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
