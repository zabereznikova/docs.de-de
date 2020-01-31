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
ms.openlocfilehash: 3d26ddb6d89af60acf6dc1214b0423ba75e488ff
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791166"
---
# <a name="icordebugvaluegetsize-method"></a><span data-ttu-id="c9827-102">ICorDebugValue::GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="c9827-102">ICorDebugValue::GetSize Method</span></span>
<span data-ttu-id="c9827-103">Ruft die Größe des "ICorDebug Value"-Objekts in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="c9827-103">Gets the size, in bytes, of this "ICorDebugValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9827-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c9827-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize (  
    [out] ULONG32   *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c9827-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="c9827-105">Parameters</span></span>  
 `pSize`  
 <span data-ttu-id="c9827-106">vorgenommen Die Größe (in Bytes) dieses Wert Objekts.</span><span class="sxs-lookup"><span data-stu-id="c9827-106">[out] The size, in bytes, of this value object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c9827-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c9827-107">Remarks</span></span>  
 <span data-ttu-id="c9827-108">Wenn der Typ des Werts ein Referenztyp ist, gibt diese Methode die Größe des Zeigers anstelle der Größe des-Objekts zurück.</span><span class="sxs-lookup"><span data-stu-id="c9827-108">If the value's type is a reference type, this method returns the size of the pointer rather than the size of the object.</span></span>  
  
 <span data-ttu-id="c9827-109">Die `ICorDebugValue::GetSize`-Methode gibt `COR_E_OVERFLOW` für Objekte zurück, die auf 64-Bit-Plattformen größer als 4 GB sind.</span><span class="sxs-lookup"><span data-stu-id="c9827-109">The `ICorDebugValue::GetSize` method returns `COR_E_OVERFLOW` for objects that are larger than 4 GB on 64-bit platforms.</span></span> <span data-ttu-id="c9827-110">Verwenden Sie stattdessen die [ICorDebugValue3:: GetSize64](icordebugvalue3-getsize64-method.md) -Methode für Objekte, die größer als 4 GB sind.</span><span class="sxs-lookup"><span data-stu-id="c9827-110">Use the [ICorDebugValue3::GetSize64](icordebugvalue3-getsize64-method.md) method instead for objects that are larger than 4 GB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9827-111">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c9827-111">Requirements</span></span>  
 <span data-ttu-id="c9827-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c9827-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9827-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c9827-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c9827-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c9827-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c9827-115">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9827-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9827-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c9827-116">See also</span></span>

- [<span data-ttu-id="c9827-117">GetSize64-Methode</span><span class="sxs-lookup"><span data-stu-id="c9827-117">GetSize64 Method</span></span>](icordebugvalue3-getsize64-method.md)
