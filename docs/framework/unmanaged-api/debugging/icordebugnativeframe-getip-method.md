---
title: ICorDebugNativeFrame::GetIP-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetIP
helpviewer_keywords:
- GetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
- ICorDebugNativeFrame::GetIP method [.NET Framework debugging]
ms.assetid: 99f693f3-d3b9-4fd8-9d09-b8efd03f7b67
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 71e9149bafc866f89253c4318ac69f2705431e48
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67765303"
---
# <a name="icordebugnativeframegetip-method"></a><span data-ttu-id="3d50a-102">ICorDebugNativeFrame::GetIP-Methode</span><span class="sxs-lookup"><span data-stu-id="3d50a-102">ICorDebugNativeFrame::GetIP Method</span></span>
<span data-ttu-id="3d50a-103">Ruft der systemeigene Code offset-Speicherort, der der Anweisungszeiger derzeit festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="3d50a-103">Gets the native code offset location to which the instruction pointer is currently set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d50a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3d50a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIP (  
    [out] ULONG32           *pnOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3d50a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3d50a-105">Parameters</span></span>  
 `pnOffset`  
 <span data-ttu-id="3d50a-106">[out] Ein Zeiger auf die Offsetposition im nativen Code.</span><span class="sxs-lookup"><span data-stu-id="3d50a-106">[out] A pointer to the offset location in the native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3d50a-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3d50a-107">Remarks</span></span>  
 <span data-ttu-id="3d50a-108">Wenn der Stapelrahmen, der durch diesen "ICorDebugNativeFrame" dargestellt wird, aktiv ist, ist der Offset der Adresse, der die nächste Anweisung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="3d50a-108">If the stack frame that is represented by this "ICorDebugNativeFrame" is active, the offset is the address of the next instruction to be executed.</span></span> <span data-ttu-id="3d50a-109">Wenn dieses Stapelrahmens nicht aktiv ist, ist der Offset der Adresse der nächsten Anweisung wird ausgeführt, wenn der Stapelrahmen erneut aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="3d50a-109">If this stack frame is not active, the offset is the address of the next instruction to be executed when the stack frame is reactivated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d50a-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3d50a-110">Requirements</span></span>  
 <span data-ttu-id="3d50a-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d50a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d50a-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3d50a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3d50a-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3d50a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3d50a-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d50a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d50a-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3d50a-115">See also</span></span>
