---
title: ICorDebugProcess5::GetTypeFields-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetTypeFields
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeFields
helpviewer_keywords:
- GetTypeFields method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::GetTypeFields method [.NET Framework debugging]
ms.assetid: 6a0ad3ee-dacb-47e9-abae-4536bcc4804b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7c2725c62105e92996bb2d8e79e8ff504904e9c7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948719"
---
# <a name="icordebugprocess5gettypefields-method"></a><span data-ttu-id="dac00-102">ICorDebugProcess5::GetTypeFields-Methode</span><span class="sxs-lookup"><span data-stu-id="dac00-102">ICorDebugProcess5::GetTypeFields Method</span></span>
<span data-ttu-id="dac00-103">Enthält Informationen zu den Feldern, die auf einen Typ gehören.</span><span class="sxs-lookup"><span data-stu-id="dac00-103">Provides information about the fields that belong to a type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dac00-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dac00-104">Syntax</span></span>  
  
```  
HRESULT GetTypeFields(  
    [in] COR_TYPEID id,  
    [in] ULONG32 celt,  
    [out] COR_FIELD fields[],   
    [out] ULONG32 *pceltNeeded  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dac00-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="dac00-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="dac00-106">[in] Der Bezeichner des Typs, dessen Feldinformationen abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="dac00-106">[in] The identifier of the type whose field information is retrieved.</span></span>  
  
 `celt`  
 <span data-ttu-id="dac00-107">[in] Die Anzahl der [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) -Objekte, deren Feldinformationen abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="dac00-107">[in] The number of [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) objects whose field information is to be retrieved.</span></span>  
  
 `fields`  
 <span data-ttu-id="dac00-108">[out] Ein Array von [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) Objekte, die Informationen zu den Feldern bereitstellen, die in den Typ gehören.</span><span class="sxs-lookup"><span data-stu-id="dac00-108">[out] An array of [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) objects that provide information about the fields that belong to the type.</span></span>  
  
 `pceltNeeded`  
 <span data-ttu-id="dac00-109">[out] Ein Zeiger auf die Anzahl der [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) Objekttypen `fields`.</span><span class="sxs-lookup"><span data-stu-id="dac00-109">[out] A pointer to the number of [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) objects included in `fields`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dac00-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dac00-110">Remarks</span></span>  
 <span data-ttu-id="dac00-111">Die `celt` -Parameter, der die Anzahl von Feldern gibt an, deren Feldinformationen, die die Methode, die zum Auffüllen verwendet `fields`, sollte auf den Wert der entsprechen den `COR_TYPE_LAYOUT::numFields` Feld.</span><span class="sxs-lookup"><span data-stu-id="dac00-111">The `celt` parameter, which specifies the number of fields whose field information the method uses to populate `fields`, should correspond to the value of the `COR_TYPE_LAYOUT::numFields` field.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dac00-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dac00-112">Requirements</span></span>  
 <span data-ttu-id="dac00-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dac00-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dac00-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dac00-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dac00-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dac00-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dac00-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dac00-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dac00-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dac00-117">See also</span></span>

- [<span data-ttu-id="dac00-118">ICorDebugProcess5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dac00-118">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="dac00-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="dac00-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
