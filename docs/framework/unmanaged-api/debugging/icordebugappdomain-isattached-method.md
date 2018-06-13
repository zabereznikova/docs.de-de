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
ms.openlocfilehash: f0412089fee27e556c2f9230e9b34de3391b9bd4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402560"
---
# <a name="icordebugappdomainisattached-method"></a><span data-ttu-id="b7bb1-102">ICorDebugAppDomain::IsAttached-Methode</span><span class="sxs-lookup"><span data-stu-id="b7bb1-102">ICorDebugAppDomain::IsAttached Method</span></span>
<span data-ttu-id="b7bb1-103">Ruft einen Wert, der angibt, ob der Debugger an die Anwendungsdomäne angefügt ist.</span><span class="sxs-lookup"><span data-stu-id="b7bb1-103">Gets a value that indicates whether the debugger is attached to the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7bb1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b7bb1-104">Syntax</span></span>  
  
```  
HRESULT IsAttached (  
    [out] BOOL  *pbAttached  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b7bb1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b7bb1-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="b7bb1-106">[out] `true` ist der Debugger an die Anwendungsdomäne angefügt ist, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="b7bb1-106">[out] `true` if the debugger is attached to the application domain; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b7bb1-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b7bb1-107">Remarks</span></span>  
 <span data-ttu-id="b7bb1-108">ICorDebugController-Methoden können nicht verwendet werden, bis der Debugger an die Anwendungsdomäne angefügt.</span><span class="sxs-lookup"><span data-stu-id="b7bb1-108">The ICorDebugController methods cannot be used until the debugger attaches to the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7bb1-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b7bb1-109">Requirements</span></span>  
 <span data-ttu-id="b7bb1-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7bb1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7bb1-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b7bb1-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b7bb1-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7bb1-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b7bb1-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7bb1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
