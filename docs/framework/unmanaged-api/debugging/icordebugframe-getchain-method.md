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
ms.openlocfilehash: cab25738c9f4727fe3970cc1db15c38e68b08de6
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212918"
---
# <a name="icordebugframegetchain-method"></a><span data-ttu-id="6cc10-102">ICorDebugFrame::GetChain-Methode</span><span class="sxs-lookup"><span data-stu-id="6cc10-102">ICorDebugFrame::GetChain Method</span></span>
<span data-ttu-id="6cc10-103">Ruft einen Zeiger auf die Kette ab, zu der dieser Frame gehört.</span><span class="sxs-lookup"><span data-stu-id="6cc10-103">Gets a pointer to the chain this frame is a part of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6cc10-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6cc10-104">Syntax</span></span>  
  
```cpp  
HRESULT GetChain (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6cc10-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6cc10-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="6cc10-106">vorgenommen Ein Zeiger auf die Adresse eines ICorDebug-Objekts, das die Kette mit diesem Frame darstellt.</span><span class="sxs-lookup"><span data-stu-id="6cc10-106">[out] A pointer to the address of an ICorDebugChain object that represents the chain containing this frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6cc10-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="6cc10-107">Requirements</span></span>  
 <span data-ttu-id="6cc10-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6cc10-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6cc10-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6cc10-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6cc10-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6cc10-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6cc10-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6cc10-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
