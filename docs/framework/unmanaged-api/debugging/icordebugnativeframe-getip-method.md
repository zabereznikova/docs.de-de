---
title: ICorDebugNativeFrame::GetIP-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugNativeFrame.GetIP
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugNativeFrame::GetIP
helpviewer_keywords:
- GetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
- ICorDebugNativeFrame::GetIP method [.NET Framework debugging]
ms.assetid: 99f693f3-d3b9-4fd8-9d09-b8efd03f7b67
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ceb0188ce2a52c3950b5fc89ea15c96852910d88
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugnativeframegetip-method"></a><span data-ttu-id="99aff-102">ICorDebugNativeFrame::GetIP-Methode</span><span class="sxs-lookup"><span data-stu-id="99aff-102">ICorDebugNativeFrame::GetIP Method</span></span>
<span data-ttu-id="99aff-103">Ruft der systemeigene Code offset Speicherort, der der Anweisungszeiger aktuell festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="99aff-103">Gets the native code offset location to which the instruction pointer is currently set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99aff-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="99aff-104">Syntax</span></span>  
  
```  
HRESULT GetIP (  
    [out] ULONG32           *pnOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="99aff-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="99aff-105">Parameters</span></span>  
 `pnOffset`  
 <span data-ttu-id="99aff-106">[out] Ein Zeiger auf die Offsetposition im systemeigenen Code.</span><span class="sxs-lookup"><span data-stu-id="99aff-106">[out] A pointer to the offset location in the native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99aff-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="99aff-107">Remarks</span></span>  
 <span data-ttu-id="99aff-108">Wenn der Stapelrahmen, der durch diese "ICorDebugNativeFrame" dargestellt wird aktiv ist, ist der Offset die Adresse der nächsten Anweisung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="99aff-108">If the stack frame that is represented by this "ICorDebugNativeFrame" is active, the offset is the address of the next instruction to be executed.</span></span> <span data-ttu-id="99aff-109">Wenn dieser Stapelrahmen nicht aktiv ist, ist der Offset der Adresse der nächsten Anweisung bei neuaktivierung des Stapelrahmens ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="99aff-109">If this stack frame is not active, the offset is the address of the next instruction to be executed when the stack frame is reactivated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99aff-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="99aff-110">Requirements</span></span>  
 <span data-ttu-id="99aff-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99aff-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99aff-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="99aff-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="99aff-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="99aff-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="99aff-114">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99aff-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99aff-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="99aff-115">See Also</span></span>  
 
