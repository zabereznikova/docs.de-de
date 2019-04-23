---
title: 'Icordebugtype2:: GetTypeId-Methode'
ms.date: 03/30/2017
api_name:
- ICorDebugType2.GetTypeID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetTypeID
helpviewer_keywords:
- GetTypeID method, ICorDebugType2 interface [.NET Framework debugging]
- ICorDebugType2.GetTypeID method [.NET Framework debugging]
ms.assetid: 0b933686-226e-4373-92b7-fac579ee7b1a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2b19efdedc21f66e4692ce1850eb3947f856e436
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59083750"
---
# <a name="icordebugtype2gettypeid-method"></a><span data-ttu-id="828e2-102">Icordebugtype2:: GetTypeId-Methode</span><span class="sxs-lookup"><span data-stu-id="828e2-102">ICorDebugType2::GetTypeID Method</span></span>
<span data-ttu-id="828e2-103">Ruft eine [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) für diesen Typ.</span><span class="sxs-lookup"><span data-stu-id="828e2-103">Gets a [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) for this type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="828e2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="828e2-104">Syntax</span></span>  
  
```  
HRESULT GetTypeID(  
    ([out] COR_TYPEID *id  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="828e2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="828e2-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="828e2-106">[out] Ein Zeiger auf die [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) für ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="828e2-106">[out] A pointer to the [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) for this ICorDebugType.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="828e2-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="828e2-107">Return Value</span></span>  
 <span data-ttu-id="828e2-108">Der Rückgabewert ist `S_OK` bei Erfolg oder ein Fehler-`HRESULT`-Code bei einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="828e2-108">The return value is `S_OK` on success, or a failure `HRESULT` code on failure.</span></span> <span data-ttu-id="828e2-109">Die `HRESULT` Codes umfassen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="828e2-109">The `HRESULT` codes include the following:</span></span>  
  
|<span data-ttu-id="828e2-110">Rückgabecode</span><span class="sxs-lookup"><span data-stu-id="828e2-110">Return code</span></span>|<span data-ttu-id="828e2-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="828e2-111">Description</span></span>|  
|-----------------|-----------------|  
|`S_OK`|<span data-ttu-id="828e2-112">Methode war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="828e2-112">Method succeeded.</span></span> <span data-ttu-id="828e2-113">Die Methode verfügt über eine gültige abgerufen [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md).</span><span class="sxs-lookup"><span data-stu-id="828e2-113">The method has retrieved a valid [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md).</span></span>|  
|`CORDBG_E_CLASS_NOT_LOADED`|<span data-ttu-id="828e2-114">Der Typ wurde nicht geladen.</span><span class="sxs-lookup"><span data-stu-id="828e2-114">The type has not been loaded.</span></span>|  
|`CORDBG_E_UNSUPPORTED`|<span data-ttu-id="828e2-115">Der Typ wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="828e2-115">The type is not supported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="828e2-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="828e2-116">Remarks</span></span>  
 <span data-ttu-id="828e2-117">Diese Methode ermöglicht eine Zuordnung zwischen der ICorDebugType, die einen Typ darstellt, die möglicherweise nicht wurde geladen in die Laufzeit, zu einem [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md), welche fungiert als ein nicht transparenter, verarbeiten identifiziert einen Typ, der in der Laufzeit geladen.</span><span class="sxs-lookup"><span data-stu-id="828e2-117">This method provides a mapping from the ICorDebugType, which represents a type that may or may not have been loaded into the runtime, to a [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md), which serves as an opaque handle that identifies a type loaded into the runtime.</span></span>  
  
 <span data-ttu-id="828e2-118">Wenn der Typ, der ICorDebugType steht, noch nicht geladen wurde, gibt diese Methode zurück `CORDBG_E_CLASS_NOT_LOADED`.</span><span class="sxs-lookup"><span data-stu-id="828e2-118">When the type that the ICorDebugType represents has not yet been loaded, this method returns `CORDBG_E_CLASS_NOT_LOADED`.</span></span>  <span data-ttu-id="828e2-119">Wenn der Typ nicht unterstützt wird, gibt es `CORDBG_E_UNSUPPORTED`.</span><span class="sxs-lookup"><span data-stu-id="828e2-119">If the type is not supported, it returns `CORDBG_E_UNSUPPORTED`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="828e2-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="828e2-120">Requirements</span></span>  
 <span data-ttu-id="828e2-121">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="828e2-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="828e2-122">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="828e2-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="828e2-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="828e2-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="828e2-124">**.NET Framework-Versionen:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="828e2-124">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="828e2-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="828e2-125">See also</span></span>

- [<span data-ttu-id="828e2-126">ICorDebugType2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="828e2-126">ICorDebugType2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-interface.md)
