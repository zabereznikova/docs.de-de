---
title: ICorDebugValue::GetSize-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugValue interface [.NET Framework debugging]
- ICorDebugValue::GetSize method [.NET Framework debugging]
ms.assetid: 445a9ee3-e050-4f3a-931a-96b0efb00110
topic_type:
- apiref
ms.openlocfilehash: 3d6caa02333229bcd49f4c6ccf8b93265181a0b3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137086"
---
# <a name="icordebugvaluegetsize-method"></a><span data-ttu-id="de2f0-102">ICorDebugValue::GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="de2f0-102">ICorDebugValue::GetSize Method</span></span>
<span data-ttu-id="de2f0-103">Ruft die Größe des "ICorDebug Value"-Objekts in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="de2f0-103">Gets the size, in bytes, of this "ICorDebugValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de2f0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="de2f0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize (  
    [out] ULONG32   *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="de2f0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="de2f0-105">Parameters</span></span>  
 `pSize`  
 <span data-ttu-id="de2f0-106">vorgenommen Die Größe (in Bytes) dieses Wert Objekts.</span><span class="sxs-lookup"><span data-stu-id="de2f0-106">[out] The size, in bytes, of this value object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="de2f0-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="de2f0-107">Remarks</span></span>  
 <span data-ttu-id="de2f0-108">Wenn der Typ des Werts ein Referenztyp ist, gibt diese Methode die Größe des Zeigers anstelle der Größe des-Objekts zurück.</span><span class="sxs-lookup"><span data-stu-id="de2f0-108">If the value's type is a reference type, this method returns the size of the pointer rather than the size of the object.</span></span>  
  
 <span data-ttu-id="de2f0-109">Die `ICorDebugValue::GetSize`-Methode gibt `COR_E_OVERFLOW` für Objekte zurück, die auf 64-Bit-Plattformen größer als 4 GB sind.</span><span class="sxs-lookup"><span data-stu-id="de2f0-109">The `ICorDebugValue::GetSize` method returns `COR_E_OVERFLOW` for objects that are larger than 4 GB on 64-bit platforms.</span></span> <span data-ttu-id="de2f0-110">Verwenden Sie stattdessen die [ICorDebugValue3:: GetSize64](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) -Methode für Objekte, die größer als 4 GB sind.</span><span class="sxs-lookup"><span data-stu-id="de2f0-110">Use the [ICorDebugValue3::GetSize64](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) method instead for objects that are larger than 4 GB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de2f0-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="de2f0-111">Requirements</span></span>  
 <span data-ttu-id="de2f0-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de2f0-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de2f0-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="de2f0-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="de2f0-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="de2f0-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="de2f0-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de2f0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de2f0-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="de2f0-116">See also</span></span>

- [<span data-ttu-id="de2f0-117">GetSize64-Methode</span><span class="sxs-lookup"><span data-stu-id="de2f0-117">GetSize64 Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md)
