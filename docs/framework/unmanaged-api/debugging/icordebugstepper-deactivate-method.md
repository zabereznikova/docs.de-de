---
title: ICorDebugStepper::Deactivate-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStepper.Deactivate
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStepper::Deactivate
helpviewer_keywords:
- Deactivate method [.NET Framework debugging]
- ICorDebugStepper::Deactivate method [.NET Framework debugging]
ms.assetid: 855f4199-b62d-40ce-998e-1eb4a1772142
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1541c6fa838115655c3ff176a0cb29f803733daa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugstepperdeactivate-method"></a><span data-ttu-id="4e118-102">ICorDebugStepper::Deactivate-Methode</span><span class="sxs-lookup"><span data-stu-id="4e118-102">ICorDebugStepper::Deactivate Method</span></span>
<span data-ttu-id="4e118-103">Bewirkt, dass dieser ICorDebugStepper, mit dem letzten Schrittbefehl "Abbrechen", den empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="4e118-103">Causes this ICorDebugStepper to cancel the last step command that it received.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e118-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4e118-104">Syntax</span></span>  
  
```  
HRESULT Deactivate ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="4e118-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4e118-105">Remarks</span></span>  
 <span data-ttu-id="4e118-106">Ein neuer Schrittbefehl kann ausgegeben werden, nachdem der zuletzt empfangenen Schrittbefehl abgebrochen wurde.</span><span class="sxs-lookup"><span data-stu-id="4e118-106">A new stepping command may be issued after the most recently received step command has been canceled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e118-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4e118-107">Requirements</span></span>  
 <span data-ttu-id="4e118-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e118-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e118-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4e118-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4e118-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4e118-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4e118-111">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e118-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
