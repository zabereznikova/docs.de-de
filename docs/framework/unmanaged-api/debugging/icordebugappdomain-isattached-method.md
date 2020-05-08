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
ms.openlocfilehash: a2f6df7647ffe9f2adff963b6629ed29ece053c0
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895162"
---
# <a name="icordebugappdomainisattached-method"></a><span data-ttu-id="d6795-102">ICorDebugAppDomain::IsAttached-Methode</span><span class="sxs-lookup"><span data-stu-id="d6795-102">ICorDebugAppDomain::IsAttached Method</span></span>
<span data-ttu-id="d6795-103">Ruft einen Wert ab, der angibt, ob der Debugger an die Anwendungsdomäne angefügt ist.</span><span class="sxs-lookup"><span data-stu-id="d6795-103">Gets a value that indicates whether the debugger is attached to the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6795-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d6795-104">Syntax</span></span>  
  
```cpp  
HRESULT IsAttached (  
    [out] BOOL  *pbAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d6795-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d6795-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="d6795-106">vorgenommen `true` , wenn der Debugger an die Anwendungsdomäne angefügt ist. andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="d6795-106">[out] `true` if the debugger is attached to the application domain; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d6795-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d6795-107">Remarks</span></span>  
 <span data-ttu-id="d6795-108">Die ICorDebugController-Methoden können erst verwendet werden, wenn der Debugger an die Anwendungsdomäne angefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="d6795-108">The ICorDebugController methods cannot be used until the debugger attaches to the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6795-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d6795-109">Requirements</span></span>  
 <span data-ttu-id="d6795-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6795-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6795-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d6795-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d6795-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d6795-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d6795-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6795-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
