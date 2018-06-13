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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: db1de215eaa0c0cc7021a119e54591caede76d3b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33417124"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacetypes-method"></a><span data-ttu-id="8d76f-102">ICorDebugComObjectValue::GetCachedInterfaceTypes-Methode</span><span class="sxs-lookup"><span data-stu-id="8d76f-102">ICorDebugComObjectValue::GetCachedInterfaceTypes Method</span></span>
<span data-ttu-id="8d76f-103">Stellt einen Enumerator für die Schnittstellentypen bereit, dass das aktuelle Objekt umgewandelt oder als verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="8d76f-103">Provides an enumerator for the interface types that the current object has been cast to or used as.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d76f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8d76f-104">Syntax</span></span>  
  
```  
HRESULT GetCachedInterfaceTypes(  
    [in] BOOL bIInspectableOnly,  
    [out] ICorDebugTypeEnum **ppInterfacesEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8d76f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8d76f-105">Parameters</span></span>  
 `bIInspectableOnly`  
 <span data-ttu-id="8d76f-106">[in] Ein Wert, der angibt, ob der Methodenrückgabe nur [!INCLUDE[wrt](../../../../includes/wrt-md.md)] Schnittstellen (`IInspectable` Schnittstellen) oder alle COM-Schnittstellen, die von den Runtime callable Wrapper (RCW) zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="8d76f-106">[in] A value that indicates whether the method returns only [!INCLUDE[wrt](../../../../includes/wrt-md.md)] interfaces (`IInspectable` interfaces) or all COM interfaces cached by the runtime callable wrapper (RCW).</span></span>  
  
 `ppInterfacesEnum`  
 <span data-ttu-id="8d76f-107">[out] Ein Zeiger auf die Adresse des ein ICorDebugTypeEnum-Enumerator, der Zugriff auf ICorDebugType-Objekte enthält, die zwischengespeicherten Schnittstellentypen darstellen laut gefiltert `bIInspectableOnly`.</span><span class="sxs-lookup"><span data-stu-id="8d76f-107">[out] A pointer to the address of an ICorDebugTypeEnum enumerator that provides access to ICorDebugType objects that represent cached interface types filtered according to `bIInspectableOnly`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8d76f-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8d76f-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d76f-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8d76f-109">Requirements</span></span>  
 <span data-ttu-id="8d76f-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d76f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d76f-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8d76f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8d76f-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8d76f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8d76f-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d76f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d76f-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8d76f-114">See Also</span></span>  
 [<span data-ttu-id="8d76f-115">ICorDebugComObjectValue-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8d76f-115">ICorDebugComObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-interface.md)  
 [<span data-ttu-id="8d76f-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="8d76f-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
