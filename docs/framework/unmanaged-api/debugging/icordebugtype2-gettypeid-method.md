---
title: 'ICorDebugType2:: GetTypeId-Methode'
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
ms.openlocfilehash: 2a4a0bfae6f9a1970f0d4aca8b37f8fc68194462
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725689"
---
# <a name="icordebugtype2gettypeid-method"></a><span data-ttu-id="49876-102">ICorDebugType2:: GetTypeId-Methode</span><span class="sxs-lookup"><span data-stu-id="49876-102">ICorDebugType2::GetTypeID Method</span></span>

<span data-ttu-id="49876-103">Ruft eine [COR_TYPEID](cor-typeid-structure.md) für diesen Typ ab.</span><span class="sxs-lookup"><span data-stu-id="49876-103">Gets a [COR_TYPEID](cor-typeid-structure.md) for this type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49876-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="49876-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeID(  
    ([out] COR_TYPEID *id  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="49876-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="49876-105">Parameters</span></span>  

 `id`  
 <span data-ttu-id="49876-106">vorgenommen Ein Zeiger auf die [COR_TYPEID](cor-typeid-structure.md) für diesen ICorDebugType.</span><span class="sxs-lookup"><span data-stu-id="49876-106">[out] A pointer to the [COR_TYPEID](cor-typeid-structure.md) for this ICorDebugType.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="49876-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="49876-107">Return Value</span></span>  

 <span data-ttu-id="49876-108">Der Rückgabewert ist `S_OK` bei Erfolg oder ein Fehler-`HRESULT`-Code bei einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="49876-108">The return value is `S_OK` on success, or a failure `HRESULT` code on failure.</span></span> <span data-ttu-id="49876-109">Die `HRESULT` Codes umfassen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="49876-109">The `HRESULT` codes include the following:</span></span>  
  
|<span data-ttu-id="49876-110">Rückgabecode</span><span class="sxs-lookup"><span data-stu-id="49876-110">Return code</span></span>|<span data-ttu-id="49876-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="49876-111">Description</span></span>|  
|-----------------|-----------------|  
|`S_OK`|<span data-ttu-id="49876-112">Methode war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="49876-112">Method succeeded.</span></span> <span data-ttu-id="49876-113">Die Methode hat einen gültigen [COR_TYPEID](cor-typeid-structure.md)abgerufen.</span><span class="sxs-lookup"><span data-stu-id="49876-113">The method has retrieved a valid [COR_TYPEID](cor-typeid-structure.md).</span></span>|  
|`CORDBG_E_CLASS_NOT_LOADED`|<span data-ttu-id="49876-114">Der Typ wurde nicht geladen.</span><span class="sxs-lookup"><span data-stu-id="49876-114">The type has not been loaded.</span></span>|  
|`CORDBG_E_UNSUPPORTED`|<span data-ttu-id="49876-115">Der Typ wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="49876-115">The type is not supported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="49876-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="49876-116">Remarks</span></span>  

 <span data-ttu-id="49876-117">Diese Methode stellt eine Zuordnung aus dem ICorDebugType bereit, der einen Typ darstellt, der möglicherweise nicht in die Laufzeit geladen wurde, in einen [COR_TYPEID](cor-typeid-structure.md), der als nicht transparentes Handle fungiert, das einen Typ identifiziert, der in die Laufzeit geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="49876-117">This method provides a mapping from the ICorDebugType, which represents a type that may or may not have been loaded into the runtime, to a [COR_TYPEID](cor-typeid-structure.md), which serves as an opaque handle that identifies a type loaded into the runtime.</span></span>  
  
 <span data-ttu-id="49876-118">Wenn der Typ, den der ICorDebugType darstellt, noch nicht geladen wurde, gibt diese Methode zurück `CORDBG_E_CLASS_NOT_LOADED` .</span><span class="sxs-lookup"><span data-stu-id="49876-118">When the type that the ICorDebugType represents has not yet been loaded, this method returns `CORDBG_E_CLASS_NOT_LOADED`.</span></span>  <span data-ttu-id="49876-119">Wenn der Typ nicht unterstützt wird, wird zurückgegeben `CORDBG_E_UNSUPPORTED` .</span><span class="sxs-lookup"><span data-stu-id="49876-119">If the type is not supported, it returns `CORDBG_E_UNSUPPORTED`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49876-120">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="49876-120">Requirements</span></span>  

 <span data-ttu-id="49876-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49876-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49876-122">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="49876-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="49876-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="49876-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="49876-124">**.NET Framework Versionen:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49876-124">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49876-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="49876-125">See also</span></span>

- [<span data-ttu-id="49876-126">ICorDebugType2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49876-126">ICorDebugType2 Interface</span></span>](icordebugtype2-interface.md)
