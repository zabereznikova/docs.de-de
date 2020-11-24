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
ms.openlocfilehash: e4eba37487ca2ee0a88caf5a59f86949a6521e40
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95670939"
---
# <a name="icordebugprocess5gettypefields-method"></a><span data-ttu-id="a1094-102">ICorDebugProcess5::GetTypeFields-Methode</span><span class="sxs-lookup"><span data-stu-id="a1094-102">ICorDebugProcess5::GetTypeFields Method</span></span>

<span data-ttu-id="a1094-103">Stellt Informationen zu den Feldern bereit, die zu einem-Typ gehören.</span><span class="sxs-lookup"><span data-stu-id="a1094-103">Provides information about the fields that belong to a type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1094-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a1094-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeFields(  
    [in] COR_TYPEID id,  
    [in] ULONG32 celt,  
    [out] COR_FIELD fields[],
    [out] ULONG32 *pceltNeeded  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a1094-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a1094-105">Parameters</span></span>  

 `id`  
 <span data-ttu-id="a1094-106">in Der Bezeichner des Typs, dessen Feldinformationen abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="a1094-106">[in] The identifier of the type whose field information is retrieved.</span></span>  
  
 `celt`  
 <span data-ttu-id="a1094-107">in Die Anzahl der [COR_FIELD](cor-field-structure.md) -Objekte, deren Feldinformationen abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a1094-107">[in] The number of [COR_FIELD](cor-field-structure.md) objects whose field information is to be retrieved.</span></span>  
  
 `fields`  
 <span data-ttu-id="a1094-108">vorgenommen Ein Array von [COR_FIELD](cor-field-structure.md) -Objekten, die Informationen zu den Feldern bereitstellen, die zum Typ gehören.</span><span class="sxs-lookup"><span data-stu-id="a1094-108">[out] An array of [COR_FIELD](cor-field-structure.md) objects that provide information about the fields that belong to the type.</span></span>  
  
 `pceltNeeded`  
 <span data-ttu-id="a1094-109">vorgenommen Ein Zeiger auf die Anzahl der [COR_FIELD](cor-field-structure.md) -Objekte, die in enthalten sind `fields` .</span><span class="sxs-lookup"><span data-stu-id="a1094-109">[out] A pointer to the number of [COR_FIELD](cor-field-structure.md) objects included in `fields`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a1094-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a1094-110">Remarks</span></span>  

 <span data-ttu-id="a1094-111">Der- `celt` Parameter, der die Anzahl der Felder angibt, deren Feldinformationen die Methode zum Auffüllen verwendet `fields` , sollte dem Wert des- `COR_TYPE_LAYOUT::numFields` Felds entsprechen.</span><span class="sxs-lookup"><span data-stu-id="a1094-111">The `celt` parameter, which specifies the number of fields whose field information the method uses to populate `fields`, should correspond to the value of the `COR_TYPE_LAYOUT::numFields` field.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1094-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a1094-112">Requirements</span></span>  

 <span data-ttu-id="a1094-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1094-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1094-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a1094-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a1094-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a1094-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a1094-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1094-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1094-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a1094-117">See also</span></span>

- [<span data-ttu-id="a1094-118">ICorDebugProcess5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a1094-118">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="a1094-119">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="a1094-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
