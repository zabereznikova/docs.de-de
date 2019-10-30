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
ms.openlocfilehash: 6c076dd2912a22e4f9492492a2d7a9fb73db88e8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139040"
---
# <a name="icordebugstepper2setjmc-method"></a><span data-ttu-id="b7eb2-102">ICorDebugStepper2::SetJMC-Methode</span><span class="sxs-lookup"><span data-stu-id="b7eb2-102">ICorDebugStepper2::SetJMC Method</span></span>
<span data-ttu-id="b7eb2-103">Legt einen Wert fest, der angibt, ob dieser ICorDebugStepper nur durch Code ausgeführt wird, der vom Entwickler einer Anwendung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="b7eb2-103">Sets a value that specifies whether this ICorDebugStepper steps only through code that is authored by an application's developer.</span></span> <span data-ttu-id="b7eb2-104">Dieser Prozess wird auch als JMC-Debugging (Just my Code) bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="b7eb2-104">This process is also known as just my code (JMC) debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7eb2-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b7eb2-105">Syntax</span></span>  
  
```cpp  
HRESULT SetJMC (  
    [in] BOOL    fIsJMCStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b7eb2-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="b7eb2-106">Parameters</span></span>  
 `fIsJMCStepper`  
 <span data-ttu-id="b7eb2-107">in Legen Sie auf `true`, um nur den Code zu durchlaufen, der vom Entwickler einer Anwendung erstellt wurde. Legen Sie andernfalls auf `false`fest.</span><span class="sxs-lookup"><span data-stu-id="b7eb2-107">[in] Set to `true` to step only through code that is authored by an application's developer; otherwise, set to `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7eb2-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b7eb2-108">Requirements</span></span>  
 <span data-ttu-id="b7eb2-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7eb2-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7eb2-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b7eb2-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b7eb2-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7eb2-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b7eb2-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7eb2-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
