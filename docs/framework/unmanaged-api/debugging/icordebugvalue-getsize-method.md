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
ms.openlocfilehash: 9ff7128f55236ae4d0c3a9067a279c496cfb6798
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396754"
---
# <a name="icordebugvaluegetsize-method"></a><span data-ttu-id="a0061-102">ICorDebugValue::GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="a0061-102">ICorDebugValue::GetSize Method</span></span>
<span data-ttu-id="a0061-103">Ruft die Größe des "ICorDebug Value"-Objekts in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="a0061-103">Gets the size, in bytes, of this "ICorDebugValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0061-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a0061-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize (  
    [out] ULONG32   *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0061-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a0061-105">Parameters</span></span>  
 `pSize`  
 <span data-ttu-id="a0061-106">vorgenommen Die Größe (in Bytes) dieses Wert Objekts.</span><span class="sxs-lookup"><span data-stu-id="a0061-106">[out] The size, in bytes, of this value object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a0061-107">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="a0061-107">Remarks</span></span>  
 <span data-ttu-id="a0061-108">Wenn der Typ des Werts ein Referenztyp ist, gibt diese Methode die Größe des Zeigers anstelle der Größe des-Objekts zurück.</span><span class="sxs-lookup"><span data-stu-id="a0061-108">If the value's type is a reference type, this method returns the size of the pointer rather than the size of the object.</span></span>  
  
 <span data-ttu-id="a0061-109">Die `ICorDebugValue::GetSize` -Methode gibt `COR_E_OVERFLOW` für Objekte, die größer als 4 GB sind, auf 64-Bit-Plattformen zurück.</span><span class="sxs-lookup"><span data-stu-id="a0061-109">The `ICorDebugValue::GetSize` method returns `COR_E_OVERFLOW` for objects that are larger than 4 GB on 64-bit platforms.</span></span> <span data-ttu-id="a0061-110">Verwenden Sie stattdessen die [ICorDebugValue3:: GetSize64](icordebugvalue3-getsize64-method.md) -Methode für Objekte, die größer als 4 GB sind.</span><span class="sxs-lookup"><span data-stu-id="a0061-110">Use the [ICorDebugValue3::GetSize64](icordebugvalue3-getsize64-method.md) method instead for objects that are larger than 4 GB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0061-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a0061-111">Requirements</span></span>  
 <span data-ttu-id="a0061-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0061-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0061-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a0061-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a0061-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a0061-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a0061-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0061-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0061-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a0061-116">See also</span></span>

- [<span data-ttu-id="a0061-117">GetSize64-Methode</span><span class="sxs-lookup"><span data-stu-id="a0061-117">GetSize64 Method</span></span>](icordebugvalue3-getsize64-method.md)
