---
title: ICorDebugCode::GetAddress-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetAddress
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetAddress
helpviewer_keywords:
- GetAddress method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetAddress method [.NET Framework debugging]
ms.assetid: cc507cb0-df2e-49c2-b32e-0c3271a8df9a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 11ced90b88f083eb69b06d197d64a8ef4252f9d5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59141492"
---
# <a name="icordebugcodegetaddress-method"></a><span data-ttu-id="5dbd3-102">ICorDebugCode::GetAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="5dbd3-102">ICorDebugCode::GetAddress Method</span></span>
<span data-ttu-id="5dbd3-103">Ruft die relative virtuelle Adresse (RVA) des Codesegments, die diese Schnittstelle "ICorDebugCode" darstellt.</span><span class="sxs-lookup"><span data-stu-id="5dbd3-103">Gets the relative virtual address (RVA) of the code segment that this "ICorDebugCode" interface represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5dbd3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5dbd3-104">Syntax</span></span>  
  
```  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS *pStart  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5dbd3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5dbd3-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="5dbd3-106">[out] Ein Zeiger auf die RVA des Codesegments.</span><span class="sxs-lookup"><span data-stu-id="5dbd3-106">[out] A pointer to the RVA of the code segment.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5dbd3-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5dbd3-107">Requirements</span></span>  
 <span data-ttu-id="5dbd3-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5dbd3-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5dbd3-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5dbd3-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5dbd3-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5dbd3-110">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="5dbd3-111">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="5dbd3-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5dbd3-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5dbd3-112">See also</span></span>
