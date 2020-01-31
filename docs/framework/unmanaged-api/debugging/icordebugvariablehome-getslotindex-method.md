---
title: 'Icordebugvariablehome:: gezlotindex-Methode'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetSlotIndex
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetSlotIndex
helpviewer_keywords:
- ICorDebugVariableHome::GetSlotIndex method [.NET Framework debugging]
- GetSlotIndex method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 966da50d-5665-4fff-bf7b-1c72bbadd9a4
topic_type:
- apiref
ms.openlocfilehash: 542bfa05c55ef224d1b9111f9af6c069e9e23542
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790974"
---
# <a name="icordebugvariablehomegetslotindex-method"></a><span data-ttu-id="95af4-102">Icordebugvariablehome:: gezlotindex-Methode</span><span class="sxs-lookup"><span data-stu-id="95af4-102">ICorDebugVariableHome::GetSlotIndex Method</span></span>
<span data-ttu-id="95af4-103">Ruft den verwalteten Slot-Index einer lokalen Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="95af4-103">Gets the managed slot-index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95af4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="95af4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSlotIndex(  
    [out] ULONG32 *pSlotIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="95af4-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="95af4-105">Parameters</span></span>  
 `pSlotIndex`  
 <span data-ttu-id="95af4-106">vorgenommen Ein Zeiger auf den slotindex einer lokalen Variablen.</span><span class="sxs-lookup"><span data-stu-id="95af4-106">[out] A pointer to the slot-index of a local variable.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="95af4-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="95af4-107">Return Value</span></span>  
 <span data-ttu-id="95af4-108">Die-Methode gibt die folgenden Werte zurück.</span><span class="sxs-lookup"><span data-stu-id="95af4-108">The method returns the following values.</span></span>  
  
|<span data-ttu-id="95af4-109">{2&gt;Wert&lt;2}</span><span class="sxs-lookup"><span data-stu-id="95af4-109">Value</span></span>|<span data-ttu-id="95af4-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="95af4-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="95af4-111">Der Methodenaufrufe hat einen Slot-Index-Wert in `pSlotIndex`zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="95af4-111">The method call returned a slot-index value in `pSlotIndex`.</span></span>|  
|`E_FAIL`|<span data-ttu-id="95af4-112">Die aktuelle [icorentbugvariablehome](icordebugvariablehome-interface.md) -Instanz stellt ein Funktions Argument dar.</span><span class="sxs-lookup"><span data-stu-id="95af4-112">The current [ICorDebugVariableHome](icordebugvariablehome-interface.md) instance represents a function argument.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95af4-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="95af4-113">Remarks</span></span>  
 <span data-ttu-id="95af4-114">Der Slot-Index kann verwendet werden, um die Metadaten für diese lokale Variable abzurufen.</span><span class="sxs-lookup"><span data-stu-id="95af4-114">The slot-index can be used to retrieve the metadata for this local variable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95af4-115">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="95af4-115">Requirements</span></span>  
 <span data-ttu-id="95af4-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95af4-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95af4-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="95af4-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="95af4-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="95af4-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="95af4-119">**.NET Framework Versionen:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95af4-119">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95af4-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="95af4-120">See also</span></span>

- [<span data-ttu-id="95af4-121">ICorDebugVariableHome-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="95af4-121">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
