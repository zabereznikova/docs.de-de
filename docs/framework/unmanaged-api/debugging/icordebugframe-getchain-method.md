---
title: ICorDebugFrame::GetChain-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetChain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetChain
helpviewer_keywords:
- ICorDebugFrame::GetChain method [.NET Framework debugging]
- GetChain method [.NET Framework debugging]
ms.assetid: e28e51d3-8f73-494f-bcd4-48bac239fbe1
topic_type:
- apiref
ms.openlocfilehash: 9677fd14f50cf93eac7eeaef784082d45e8884c7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137688"
---
# <a name="icordebugframegetchain-method"></a><span data-ttu-id="acf95-102">ICorDebugFrame::GetChain-Methode</span><span class="sxs-lookup"><span data-stu-id="acf95-102">ICorDebugFrame::GetChain Method</span></span>
<span data-ttu-id="acf95-103">Ruft einen Zeiger auf die Kette ab, zu der dieser Frame gehört.</span><span class="sxs-lookup"><span data-stu-id="acf95-103">Gets a pointer to the chain this frame is a part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acf95-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="acf95-104">Syntax</span></span>  
  
```cpp  
HRESULT GetChain (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="acf95-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="acf95-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="acf95-106">vorgenommen Ein Zeiger auf die Adresse eines ICorDebug-Objekts, das die Kette mit diesem Frame darstellt.</span><span class="sxs-lookup"><span data-stu-id="acf95-106">[out] A pointer to the address of an ICorDebugChain object that represents the chain containing this frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="acf95-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="acf95-107">Requirements</span></span>  
 <span data-ttu-id="acf95-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="acf95-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="acf95-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="acf95-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="acf95-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="acf95-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="acf95-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="acf95-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
