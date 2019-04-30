---
title: ICorDebugAppDomain::IsAttached-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.IsAttached
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::IsAttached
helpviewer_keywords:
- IsAttached method [.NET Framework debugging]
- ICorDebugAppDomain::IsAttached method [.NET Framework debugging]
ms.assetid: af0c67c7-f53e-47c9-b84b-be50bd04903e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fa9576f568ef1f6da3eef812abb9674aa0d81dfb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61996163"
---
# <a name="icordebugappdomainisattached-method"></a><span data-ttu-id="172e5-102">ICorDebugAppDomain::IsAttached-Methode</span><span class="sxs-lookup"><span data-stu-id="172e5-102">ICorDebugAppDomain::IsAttached Method</span></span>
<span data-ttu-id="172e5-103">Ruft einen Wert, der angibt, ob die Anwendungsdomäne der Debugger angefügt ist.</span><span class="sxs-lookup"><span data-stu-id="172e5-103">Gets a value that indicates whether the debugger is attached to the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="172e5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="172e5-104">Syntax</span></span>  
  
```  
HRESULT IsAttached (  
    [out] BOOL  *pbAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="172e5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="172e5-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="172e5-106">[out] `true` ist der Debugger an die Anwendungsdomäne angefügt ist, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="172e5-106">[out] `true` if the debugger is attached to the application domain; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="172e5-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="172e5-107">Remarks</span></span>  
 <span data-ttu-id="172e5-108">Die ICorDebugController-Methoden können nicht verwendet werden, bis der Debugger an die Anwendungsdomäne angefügt.</span><span class="sxs-lookup"><span data-stu-id="172e5-108">The ICorDebugController methods cannot be used until the debugger attaches to the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="172e5-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="172e5-109">Requirements</span></span>  
 <span data-ttu-id="172e5-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="172e5-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="172e5-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="172e5-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="172e5-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="172e5-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="172e5-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="172e5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
