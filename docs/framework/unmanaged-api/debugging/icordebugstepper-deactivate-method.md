---
title: ICorDebugStepper::Deactivate-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.Deactivate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::Deactivate
helpviewer_keywords:
- Deactivate method [.NET Framework debugging]
- ICorDebugStepper::Deactivate method [.NET Framework debugging]
ms.assetid: 855f4199-b62d-40ce-998e-1eb4a1772142
topic_type:
- apiref
ms.openlocfilehash: 0d7d5e7e6c9bc1a68feda85c5214f3ae95df9b97
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730584"
---
# <a name="icordebugstepperdeactivate-method"></a><span data-ttu-id="55cc6-102">ICorDebugStepper::Deactivate-Methode</span><span class="sxs-lookup"><span data-stu-id="55cc6-102">ICorDebugStepper::Deactivate Method</span></span>

<span data-ttu-id="55cc6-103">Bewirkt, dass dieser icorentbugstepper den letzten Schritt Befehl abbricht, den er empfangen hat.</span><span class="sxs-lookup"><span data-stu-id="55cc6-103">Causes this ICorDebugStepper to cancel the last step command that it received.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55cc6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="55cc6-104">Syntax</span></span>  
  
```cpp  
HRESULT Deactivate ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="55cc6-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="55cc6-105">Remarks</span></span>  

 <span data-ttu-id="55cc6-106">Nachdem der Befehl zuletzt empfangener Schritt abgebrochen wurde, kann ein neuer Schritt Befehl ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="55cc6-106">A new stepping command may be issued after the most recently received step command has been canceled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55cc6-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="55cc6-107">Requirements</span></span>  

 <span data-ttu-id="55cc6-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55cc6-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55cc6-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="55cc6-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="55cc6-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="55cc6-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="55cc6-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55cc6-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
