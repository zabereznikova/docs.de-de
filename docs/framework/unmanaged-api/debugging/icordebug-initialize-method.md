---
title: ICorDebug::Initialize-Methode
ms.date: 03/30/2017
api_name:
- ICorDebug.Initialize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::Initialize
helpviewer_keywords:
- Initialize method, ICorDebug interface [.NET Framework debugging]
- ICorDebug::Initialize method [.NET Framework debugging]
ms.assetid: 6fae3b23-5c9f-47c0-85d8-6bb75e050786
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dd09ce27c0fea9dca8fd86afc563651d68542e13
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59173146"
---
# <a name="icordebuginitialize-method"></a><span data-ttu-id="32e8a-102">ICorDebug::Initialize-Methode</span><span class="sxs-lookup"><span data-stu-id="32e8a-102">ICorDebug::Initialize Method</span></span>
<span data-ttu-id="32e8a-103">Initialisiert das `ICorDebug`-Objekt.</span><span class="sxs-lookup"><span data-stu-id="32e8a-103">Initializes the `ICorDebug` object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32e8a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="32e8a-104">Syntax</span></span>  
  
```  
HRESULT Initialize ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="32e8a-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="32e8a-105">Remarks</span></span>  
 <span data-ttu-id="32e8a-106">Der Debugger muss Aufrufen `Initialize` bei der Erstellung des services-Zeit, um das Debuggen zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="32e8a-106">The debugger must call `Initialize` at creation time to initialize the debugging services.</span></span> <span data-ttu-id="32e8a-107">Diese Methode muss vor jeder anderen Methode aufgerufen werden, auf `ICorDebug` aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="32e8a-107">This method must be called before any other method on `ICorDebug` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32e8a-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="32e8a-108">Requirements</span></span>  
 <span data-ttu-id="32e8a-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="32e8a-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32e8a-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="32e8a-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="32e8a-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="32e8a-111">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="32e8a-112">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="32e8a-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="32e8a-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="32e8a-113">See also</span></span>

- [<span data-ttu-id="32e8a-114">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="32e8a-114">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
