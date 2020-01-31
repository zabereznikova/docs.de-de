---
title: ICorDebugComObjectValue::GetCachedInterfaceTypes-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugComObjectValue::GetCachedInterfaceTypes
api_location:
- mscordbi.dll
f1_keywords:
- ICorDebugComObjectValue::GetCachedInterfaceTypes
helpviewer_keywords:
- GetCachedInterface method, ICorDebugComObjectValue interface [.NET Framework debugging]
- ICorDebugComObjectValue::GetCachedInterface method [.NET Framework debugging]
ms.assetid: d492284f-d3c5-4614-adb8-d718d5042500
topic_type:
- apiref
ms.openlocfilehash: f720b06581ac60c8bd68dc5e85f15843fd9425f6
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788909"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacetypes-method"></a><span data-ttu-id="97201-102">ICorDebugComObjectValue::GetCachedInterfaceTypes-Methode</span><span class="sxs-lookup"><span data-stu-id="97201-102">ICorDebugComObjectValue::GetCachedInterfaceTypes Method</span></span>
<span data-ttu-id="97201-103">Stellt einen Enumerator für die Schnittstellentypen bereit, in die das aktuelle-Objekt umgewandelt oder verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="97201-103">Provides an enumerator for the interface types that the current object has been cast to or used as.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97201-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="97201-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedInterfaceTypes(  
    [in] BOOL bIInspectableOnly,  
    [out] ICorDebugTypeEnum **ppInterfacesEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="97201-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="97201-105">Parameters</span></span>  
 `bIInspectableOnly`  
 <span data-ttu-id="97201-106">in Ein Wert, der angibt, ob die Methode nur Windows-Runtime Schnittstellen (`IInspectable` Schnittstellen) oder alle vom Runtime Callable Wrapper (RCW) zwischengespeicherten com-Schnittstellen zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="97201-106">[in] A value that indicates whether the method returns only Windows Runtime interfaces (`IInspectable` interfaces) or all COM interfaces cached by the runtime callable wrapper (RCW).</span></span>  
  
 `ppInterfacesEnum`  
 <span data-ttu-id="97201-107">[out] Ein Zeiger auf die Adresse des ein ICorDebugTypeEnum-Enumerator, der Zugriff auf ICorDebugType-Objekte enthält, die zwischengespeicherten Schnittstellentypen darstellen laut gefiltert `bIInspectableOnly`.</span><span class="sxs-lookup"><span data-stu-id="97201-107">[out] A pointer to the address of an ICorDebugTypeEnum enumerator that provides access to ICorDebugType objects that represent cached interface types filtered according to `bIInspectableOnly`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97201-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="97201-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97201-109">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="97201-109">Requirements</span></span>  
 <span data-ttu-id="97201-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97201-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97201-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="97201-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="97201-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="97201-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="97201-113">**.NET Framework Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97201-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97201-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="97201-114">See also</span></span>

- [<span data-ttu-id="97201-115">ICorDebugComObjectValue-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="97201-115">ICorDebugComObjectValue Interface</span></span>](icordebugcomobjectvalue-interface.md)
- [<span data-ttu-id="97201-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="97201-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
