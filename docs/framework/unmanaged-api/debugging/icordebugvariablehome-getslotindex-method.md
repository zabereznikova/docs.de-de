---
title: ICorDebugVariableHome::GetSlotIndex-Methode
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b819f1f02870a8a85a531d7d341cbaf488a1ccd6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993667"
---
# <a name="icordebugvariablehomegetslotindex-method"></a><span data-ttu-id="9cbb7-102">ICorDebugVariableHome::GetSlotIndex-Methode</span><span class="sxs-lookup"><span data-stu-id="9cbb7-102">ICorDebugVariableHome::GetSlotIndex Method</span></span>
<span data-ttu-id="9cbb7-103">Ruft den verwalteten slotindex einer lokalen Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="9cbb7-103">Gets the managed slot-index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cbb7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9cbb7-104">Syntax</span></span>  
  
```  
HRESULT GetSlotIndex(  
    [out] ULONG32 *pSlotIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9cbb7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9cbb7-105">Parameters</span></span>  
 `pSlotIndex`  
 <span data-ttu-id="9cbb7-106">[out] Ein Zeiger auf den slotindex einer lokalen Variablen.</span><span class="sxs-lookup"><span data-stu-id="9cbb7-106">[out] A pointer to the slot-index of a local variable.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9cbb7-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9cbb7-107">Return Value</span></span>  
 <span data-ttu-id="9cbb7-108">Die Methode gibt die folgenden Werte an.</span><span class="sxs-lookup"><span data-stu-id="9cbb7-108">The method returns the following values.</span></span>  
  
|<span data-ttu-id="9cbb7-109">Wert</span><span class="sxs-lookup"><span data-stu-id="9cbb7-109">Value</span></span>|<span data-ttu-id="9cbb7-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9cbb7-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="9cbb7-111">Aufruf der Methode wurde in einen Slot-Indexwert `pSlotIndex`.</span><span class="sxs-lookup"><span data-stu-id="9cbb7-111">The method call returned a slot-index value in `pSlotIndex`.</span></span>|  
|`E_FAIL`|<span data-ttu-id="9cbb7-112">Die aktuelle [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) Instanz darstellt, ein Funktionsargument.</span><span class="sxs-lookup"><span data-stu-id="9cbb7-112">The current [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instance represents a function argument.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9cbb7-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9cbb7-113">Remarks</span></span>  
 <span data-ttu-id="9cbb7-114">Die Slot-Index kann zum Abrufen der Metadaten für diese lokale Variable verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9cbb7-114">The slot-index can be used to retrieve the metadata for this local variable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9cbb7-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9cbb7-115">Requirements</span></span>  
 <span data-ttu-id="9cbb7-116">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9cbb7-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9cbb7-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9cbb7-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9cbb7-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9cbb7-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9cbb7-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9cbb7-119">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cbb7-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9cbb7-120">See also</span></span>

- [<span data-ttu-id="9cbb7-121">ICorDebugVariableHome-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9cbb7-121">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
