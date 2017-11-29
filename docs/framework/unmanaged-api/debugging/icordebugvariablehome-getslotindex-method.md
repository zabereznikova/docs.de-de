---
title: ICorDebugVariableHome::GetSlotIndex-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorDebugVariableHome.GetSlotIndex
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugVariableHome::GetSlotIndex
helpviewer_keywords:
- ICorDebugVariableHome::GetSlotIndex method [.NET Framework debugging]
- GetSlotIndex method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 966da50d-5665-4fff-bf7b-1c72bbadd9a4
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3eb8ed980fd523d0b0d29fbef770652a1d96146f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugvariablehomegetslotindex-method"></a><span data-ttu-id="4274f-102">ICorDebugVariableHome::GetSlotIndex-Methode</span><span class="sxs-lookup"><span data-stu-id="4274f-102">ICorDebugVariableHome::GetSlotIndex Method</span></span>
<span data-ttu-id="4274f-103">Ruft den verwalteten slotindex einer lokalen Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="4274f-103">Gets the managed slot-index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4274f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4274f-104">Syntax</span></span>  
  
```  
HRESULT GetSlotIndex(  
    [out] ULONG32 *pSlotIndex  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4274f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4274f-105">Parameters</span></span>  
 `pSlotIndex`  
 <span data-ttu-id="4274f-106">[out] Ein Zeiger auf den slotindex einer lokalen Variablen.</span><span class="sxs-lookup"><span data-stu-id="4274f-106">[out] A pointer to the slot-index of a local variable.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4274f-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4274f-107">Return Value</span></span>  
 <span data-ttu-id="4274f-108">Die Methode gibt die folgenden Werte zurück.</span><span class="sxs-lookup"><span data-stu-id="4274f-108">The method returns the following values.</span></span>  
  
|<span data-ttu-id="4274f-109">Wert</span><span class="sxs-lookup"><span data-stu-id="4274f-109">Value</span></span>|<span data-ttu-id="4274f-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4274f-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="4274f-111">Der Methodenaufruf zurückgegebene Slot Indexwert in `pSlotIndex`.</span><span class="sxs-lookup"><span data-stu-id="4274f-111">The method call returned a slot-index value in `pSlotIndex`.</span></span>|  
|`E_FAIL`|<span data-ttu-id="4274f-112">Die aktuelle [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) Instanz steht ein Funktionsargument.</span><span class="sxs-lookup"><span data-stu-id="4274f-112">The current [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instance represents a function argument.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4274f-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4274f-113">Remarks</span></span>  
 <span data-ttu-id="4274f-114">Der slotindex kann verwendet werden, um die Metadaten für diese lokalen Variablen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="4274f-114">The slot-index can be used to retrieve the metadata for this local variable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4274f-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4274f-115">Requirements</span></span>  
 <span data-ttu-id="4274f-116">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4274f-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4274f-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4274f-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4274f-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4274f-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4274f-119">**.NET Framework-Versionen:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4274f-119">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4274f-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4274f-120">See Also</span></span>  
 [<span data-ttu-id="4274f-121">ICorDebugVariableHome-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4274f-121">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
