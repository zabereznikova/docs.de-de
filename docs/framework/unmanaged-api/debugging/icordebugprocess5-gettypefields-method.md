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
ms.openlocfilehash: 29006eba3d3a523fd24a461207ab12222a639782
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178590"
---
# <a name="icordebugprocess5gettypefields-method"></a><span data-ttu-id="10176-102">ICorDebugProcess5::GetTypeFields-Methode</span><span class="sxs-lookup"><span data-stu-id="10176-102">ICorDebugProcess5::GetTypeFields Method</span></span>
<span data-ttu-id="10176-103">Enthält Informationen zu den Feldern, die zu einem Typ gehören.</span><span class="sxs-lookup"><span data-stu-id="10176-103">Provides information about the fields that belong to a type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10176-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="10176-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeFields(  
    [in] COR_TYPEID id,  
    [in] ULONG32 celt,  
    [out] COR_FIELD fields[],
    [out] ULONG32 *pceltNeeded  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="10176-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="10176-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="10176-106">[in] Der Bezeichner des Typs, dessen Feldinformationen abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="10176-106">[in] The identifier of the type whose field information is retrieved.</span></span>  
  
 `celt`  
 <span data-ttu-id="10176-107">[in] Die Anzahl der [COR_FIELD](cor-field-structure.md) Objekte, deren Feldinformationen abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="10176-107">[in] The number of [COR_FIELD](cor-field-structure.md) objects whose field information is to be retrieved.</span></span>  
  
 `fields`  
 <span data-ttu-id="10176-108">[out] Ein Array [COR_FIELD](cor-field-structure.md) von COR_FIELD-Objekten, die Informationen zu den Feldern bereitstellen, die zum Typ gehören.</span><span class="sxs-lookup"><span data-stu-id="10176-108">[out] An array of [COR_FIELD](cor-field-structure.md) objects that provide information about the fields that belong to the type.</span></span>  
  
 `pceltNeeded`  
 <span data-ttu-id="10176-109">[out] Ein Zeiger auf die [COR_FIELD](cor-field-structure.md) Anzahl der `fields`COR_FIELD In .</span><span class="sxs-lookup"><span data-stu-id="10176-109">[out] A pointer to the number of [COR_FIELD](cor-field-structure.md) objects included in `fields`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="10176-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="10176-110">Remarks</span></span>  
 <span data-ttu-id="10176-111">Der `celt` Parameter, der die Anzahl der Felder angibt, deren Feldinformationen die Methode zum Auffüllen `fields`verwendet, sollte dem Wert des `COR_TYPE_LAYOUT::numFields` Felds entsprechen.</span><span class="sxs-lookup"><span data-stu-id="10176-111">The `celt` parameter, which specifies the number of fields whose field information the method uses to populate `fields`, should correspond to the value of the `COR_TYPE_LAYOUT::numFields` field.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10176-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="10176-112">Requirements</span></span>  
 <span data-ttu-id="10176-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10176-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10176-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="10176-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="10176-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="10176-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="10176-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10176-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10176-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="10176-117">See also</span></span>

- [<span data-ttu-id="10176-118">ICorDebugProcess5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="10176-118">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="10176-119">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="10176-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
