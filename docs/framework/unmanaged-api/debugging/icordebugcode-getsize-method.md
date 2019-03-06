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
ms.openlocfilehash: 3bd21e43973d116e4383d88bd5ce90f0fbfeb1a6
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471479"
---
# <a name="icordebugcodegetsize-method"></a><span data-ttu-id="f7892-102">ICorDebugCode::GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="f7892-102">ICorDebugCode::GetSize Method</span></span>
<span data-ttu-id="f7892-103">Ruft die Größe des Binärcodes dargestellt durch "ICorDebugCode" in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="f7892-103">Gets the size, in bytes, of the binary code represented by this "ICorDebugCode".</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7892-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f7892-104">Syntax</span></span>  
  
```  
HRESULT GetSize (  
    [out] ULONG32    *pcBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7892-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f7892-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="f7892-106">[out] Ein Zeiger auf die Größe in Bytes, die Binärdatei zu code, den dieses `ICorDebugCode` -Objekt darstellt.</span><span class="sxs-lookup"><span data-stu-id="f7892-106">[out] A pointer to the size, in bytes, of the binary code that this `ICorDebugCode` object represents.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7892-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f7892-107">Requirements</span></span>  
 <span data-ttu-id="f7892-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7892-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7892-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f7892-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f7892-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f7892-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f7892-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7892-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7892-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f7892-112">See also</span></span>

