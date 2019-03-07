---
title: ICorDebugProcess5::GetTypeID-Methode
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugProcess5.GetTypeID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeID
helpviewer_keywords:
- ICorDebugProcess5::GetTypeID method [.NET Framework debugging]
- GetTypeID method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 47dbaea4-8857-462e-93ba-fff880fc9e50
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f58e4213959ca1cd6e65bc809a9ad964bebc31ae
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494791"
---
# <a name="icordebugprocess5gettypeid-method"></a><span data-ttu-id="34df9-102">ICorDebugProcess5::GetTypeID-Methode</span><span class="sxs-lookup"><span data-stu-id="34df9-102">ICorDebugProcess5::GetTypeID Method</span></span>
<span data-ttu-id="34df9-103">Konvertiert eine Objektadresse für einen [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) Bezeichner.</span><span class="sxs-lookup"><span data-stu-id="34df9-103">Converts an object address to a [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34df9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="34df9-104">Syntax</span></span>  
  
```cpp
HRESULT GetTypeID(  
    [in] CORDB_ADDRESS obj,  
    [out] COR_TYPEID *pId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="34df9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="34df9-105">Parameters</span></span>  
 `obj`  
 <span data-ttu-id="34df9-106">[in] Die Adresse des Objekts.</span><span class="sxs-lookup"><span data-stu-id="34df9-106">[in] The object address.</span></span>  
  
 `pId`  
 <span data-ttu-id="34df9-107">Ein Zeiger auf die [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) -Wert, der das Objekt identifiziert.</span><span class="sxs-lookup"><span data-stu-id="34df9-107">A pointer to the [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) value that identifies the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34df9-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="34df9-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34df9-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="34df9-109">Requirements</span></span>  
 <span data-ttu-id="34df9-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34df9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34df9-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="34df9-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="34df9-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="34df9-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="34df9-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34df9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34df9-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="34df9-114">See also</span></span>
- [<span data-ttu-id="34df9-115">ICorDebugProcess5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="34df9-115">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="34df9-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="34df9-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
