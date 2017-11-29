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
ms.openlocfilehash: 056d60a56c37126163361166e16da5d7949e2dbc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugstepperdeactivate-method"></a><span data-ttu-id="d7414-102">ICorDebugStepper::Deactivate-Methode</span><span class="sxs-lookup"><span data-stu-id="d7414-102">ICorDebugStepper::Deactivate Method</span></span>
<span data-ttu-id="d7414-103">Bewirkt, dass dieser ICorDebugStepper, mit dem letzten Schrittbefehl "Abbrechen", den empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="d7414-103">Causes this ICorDebugStepper to cancel the last step command that it received.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7414-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d7414-104">Syntax</span></span>  
  
```  
HRESULT Deactivate ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="d7414-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d7414-105">Remarks</span></span>  
 <span data-ttu-id="d7414-106">Ein neuer Schrittbefehl kann ausgegeben werden, nachdem der zuletzt empfangenen Schrittbefehl abgebrochen wurde.</span><span class="sxs-lookup"><span data-stu-id="d7414-106">A new stepping command may be issued after the most recently received step command has been canceled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7414-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d7414-107">Requirements</span></span>  
 <span data-ttu-id="d7414-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7414-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7414-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d7414-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d7414-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d7414-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d7414-111">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7414-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
