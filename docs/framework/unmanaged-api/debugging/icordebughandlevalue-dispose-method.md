---
title: ICorDebugHandleValue::Dispose-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugHandleValue.Dispose
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHandleValue::Dispose
helpviewer_keywords:
- ICorDebugHandleValue::Dispose method [.NET Framework debugging]
- Dispose method [.NET Framework debugging]
ms.assetid: c1542811-0a7f-4235-bcfd-b24370d6f24b
topic_type:
- apiref
ms.openlocfilehash: 957035591090fb5a6a615662c4840ff16509ee20
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138504"
---
# <a name="icordebughandlevaluedispose-method"></a><span data-ttu-id="1c73f-102">ICorDebugHandleValue::Dispose-Methode</span><span class="sxs-lookup"><span data-stu-id="1c73f-102">ICorDebugHandleValue::Dispose Method</span></span>
<span data-ttu-id="1c73f-103">Gibt das Handle frei, auf das von diesem ICorDebugHandleValue-Objekt verwiesen wird, ohne den Schnittstellen Zeiger explizit freizugeben.</span><span class="sxs-lookup"><span data-stu-id="1c73f-103">Releases the handle referenced by this ICorDebugHandleValue object without explicitly releasing the interface pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c73f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1c73f-104">Syntax</span></span>  
  
```cpp  
HRESULT Dispose ();  
```  
  
## <a name="requirements"></a><span data-ttu-id="1c73f-105">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1c73f-105">Requirements</span></span>  
 <span data-ttu-id="1c73f-106">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c73f-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c73f-107">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1c73f-107">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1c73f-108">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c73f-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1c73f-109">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c73f-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
