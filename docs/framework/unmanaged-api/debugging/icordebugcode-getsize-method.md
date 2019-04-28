---
title: ICorDebugCode::GetSize-Methode
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 678b7fbd595b1238b7025c22b0ed80b02ed4becd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61750206"
---
# <a name="icordebugcodegetsize-method"></a><span data-ttu-id="8147d-102">ICorDebugCode::GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="8147d-102">ICorDebugCode::GetSize Method</span></span>
<span data-ttu-id="8147d-103">Ruft die Größe des Binärcodes dargestellt durch "ICorDebugCode" in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="8147d-103">Gets the size, in bytes, of the binary code represented by this "ICorDebugCode".</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8147d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8147d-104">Syntax</span></span>  
  
```  
HRESULT GetSize (  
    [out] ULONG32    *pcBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8147d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8147d-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="8147d-106">[out] Ein Zeiger auf die Größe in Bytes, die Binärdatei zu code, den dieses `ICorDebugCode` -Objekt darstellt.</span><span class="sxs-lookup"><span data-stu-id="8147d-106">[out] A pointer to the size, in bytes, of the binary code that this `ICorDebugCode` object represents.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8147d-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8147d-107">Requirements</span></span>  
 <span data-ttu-id="8147d-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8147d-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8147d-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8147d-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8147d-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8147d-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8147d-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8147d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8147d-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8147d-112">See also</span></span>
