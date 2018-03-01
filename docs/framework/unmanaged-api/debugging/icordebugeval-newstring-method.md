---
title: ICorDebugEval::NewString-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugEval.NewString
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewString
helpviewer_keywords:
- NewString method [.NET Framework debugging]
- ICorDebugEval::NewString method [.NET Framework debugging]
ms.assetid: 29e7a14b-d50e-4852-bfda-011b76c0c9ee
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6cc45d766801391fcd157c39357058be17759f8d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugevalnewstring-method"></a><span data-ttu-id="4e10a-102">ICorDebugEval::NewString-Methode</span><span class="sxs-lookup"><span data-stu-id="4e10a-102">ICorDebugEval::NewString Method</span></span>
<span data-ttu-id="4e10a-103">Ordnet eine neue Zeichenfolgeninstanz mit dem angegebenen Inhalt.</span><span class="sxs-lookup"><span data-stu-id="4e10a-103">Allocates a new string instance with the specified contents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e10a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4e10a-104">Syntax</span></span>  
  
```  
HRESULT NewString (  
    [in] LPCWSTR   string  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4e10a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4e10a-105">Parameters</span></span>  
 `string`  
 <span data-ttu-id="4e10a-106">[in] Ein Zeiger auf den Inhalt für die Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="4e10a-106">[in] Pointer to the contents for the string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4e10a-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4e10a-107">Remarks</span></span>  
 <span data-ttu-id="4e10a-108">Die Zeichenfolge wird immer in der Anwendungsdomäne erstellt, in dem der Thread gerade ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4e10a-108">The string is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e10a-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4e10a-109">Requirements</span></span>  
 <span data-ttu-id="4e10a-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e10a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e10a-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4e10a-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4e10a-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4e10a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4e10a-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e10a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
