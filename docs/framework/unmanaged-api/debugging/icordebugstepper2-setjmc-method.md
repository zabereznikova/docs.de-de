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
ms.openlocfilehash: 1bbcbcfbb78d421f247a13f58070b68f701e4ed1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697206"
---
# <a name="icordebugstepper2setjmc-method"></a><span data-ttu-id="c8518-102">ICorDebugStepper2::SetJMC-Methode</span><span class="sxs-lookup"><span data-stu-id="c8518-102">ICorDebugStepper2::SetJMC Method</span></span>

<span data-ttu-id="c8518-103">Legt einen Wert fest, der angibt, ob dieser ICorDebugStepper nur durch Code ausgeführt wird, der vom Entwickler einer Anwendung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="c8518-103">Sets a value that specifies whether this ICorDebugStepper steps only through code that is authored by an application's developer.</span></span> <span data-ttu-id="c8518-104">Dieser Prozess wird auch als JMC-Debugging (Just my Code) bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="c8518-104">This process is also known as just my code (JMC) debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8518-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="c8518-105">Syntax</span></span>  
  
```cpp  
HRESULT SetJMC (  
    [in] BOOL    fIsJMCStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c8518-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="c8518-106">Parameters</span></span>  

 `fIsJMCStepper`  
 <span data-ttu-id="c8518-107">in Legen Sie diese Einstellung auf fest, `true` um nur den Code zu durchlaufen, der vom Entwickler einer Anwendung erstellt wurde. andernfalls legen Sie auf fest `false` .</span><span class="sxs-lookup"><span data-stu-id="c8518-107">[in] Set to `true` to step only through code that is authored by an application's developer; otherwise, set to `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8518-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c8518-108">Requirements</span></span>  

 <span data-ttu-id="c8518-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8518-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8518-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c8518-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c8518-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c8518-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c8518-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8518-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
