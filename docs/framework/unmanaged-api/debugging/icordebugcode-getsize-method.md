---
title: ICorDebugCode::GetSize-Methode
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
- ICorDebugCode.GetSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetSize method [.NET Framework debugging]
ms.assetid: 115bc6de-f5e2-4e8e-bb38-c7cf54045434
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 69c28cba90c8ebef1b178263c8edac2cb5914c0f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcodegetsize-method"></a><span data-ttu-id="c85bc-102">ICorDebugCode::GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="c85bc-102">ICorDebugCode::GetSize Method</span></span>
<span data-ttu-id="c85bc-103">Ruft die Größe des Binärcodes dargestellt durch "ICorDebugCode" in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="c85bc-103">Gets the size, in bytes, of the binary code represented by this "ICorDebugCode".</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c85bc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c85bc-104">Syntax</span></span>  
  
```  
HRESULT GetSize (  
    [out] ULONG32    *pcBytes  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c85bc-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c85bc-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="c85bc-106">[out] Ein Zeiger auf die Größe in Bytes, der Binärdatei code, die von diesem `ICorDebugCode` -Objekt darstellt.</span><span class="sxs-lookup"><span data-stu-id="c85bc-106">[out] A pointer to the size, in bytes, of the binary code that this `ICorDebugCode` object represents.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c85bc-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c85bc-107">Requirements</span></span>  
 <span data-ttu-id="c85bc-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c85bc-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c85bc-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c85bc-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c85bc-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c85bc-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c85bc-111">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c85bc-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c85bc-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c85bc-112">See Also</span></span>  
 
