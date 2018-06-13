---
title: ICorDebugStepper2::SetJMC-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugStepper2.SetJMC
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper2::SetJMC
helpviewer_keywords:
- ICorDebugStepper2::SetJMC method [.NET Framework debugging]
- SetJMC method [.NET Framework debugging]
ms.assetid: f5cdc135-6db4-4b32-9dd1-260ec58b774f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4ad05d2f6226d570fc854fb48575851dd718e410
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418196"
---
# <a name="icordebugstepper2setjmc-method"></a><span data-ttu-id="5d8f9-102">ICorDebugStepper2::SetJMC-Methode</span><span class="sxs-lookup"><span data-stu-id="5d8f9-102">ICorDebugStepper2::SetJMC Method</span></span>
<span data-ttu-id="5d8f9-103">Legt einen Wert, der angibt, ob dieser ICorDebugStepper nur Code verarbeitet, die von einem Anwendungsentwickler erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="5d8f9-103">Sets a value that specifies whether this ICorDebugStepper steps only through code that is authored by an application's developer.</span></span> <span data-ttu-id="5d8f9-104">Dieser Prozess wird auch bezeichnet als nur mein ("JMC") Codedebuggen.</span><span class="sxs-lookup"><span data-stu-id="5d8f9-104">This process is also known as just my code (JMC) debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d8f9-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="5d8f9-105">Syntax</span></span>  
  
```  
HRESULT SetJMC (  
    [in] BOOL    fIsJMCStepper  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5d8f9-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="5d8f9-106">Parameters</span></span>  
 `fIsJMCStepper`  
 <span data-ttu-id="5d8f9-107">[in] Legen Sie auf `true` , nur den Code schrittweise durchlaufen, die vom Entwickler eine Anwendung erstellt wird, legen Sie andernfalls auf `false`.</span><span class="sxs-lookup"><span data-stu-id="5d8f9-107">[in] Set to `true` to step only through code that is authored by an application's developer; otherwise, set to `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d8f9-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5d8f9-108">Requirements</span></span>  
 <span data-ttu-id="5d8f9-109">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d8f9-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d8f9-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5d8f9-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5d8f9-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5d8f9-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5d8f9-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d8f9-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
