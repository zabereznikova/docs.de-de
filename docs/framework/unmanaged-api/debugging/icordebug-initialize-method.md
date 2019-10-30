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
ms.openlocfilehash: a5cda98cac0bc3fc6fb101fd0404b062224cb578
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134084"
---
# <a name="icordebuginitialize-method"></a><span data-ttu-id="eead0-102">ICorDebug::Initialize-Methode</span><span class="sxs-lookup"><span data-stu-id="eead0-102">ICorDebug::Initialize Method</span></span>
<span data-ttu-id="eead0-103">Initialisiert das `ICorDebug`-Objekt.</span><span class="sxs-lookup"><span data-stu-id="eead0-103">Initializes the `ICorDebug` object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eead0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="eead0-104">Syntax</span></span>  
  
```cpp  
HRESULT Initialize ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="eead0-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="eead0-105">Remarks</span></span>  
 <span data-ttu-id="eead0-106">Der Debugger muss `Initialize` zum Erstellungs Zeitpunkt aufzurufen, um die debuggingdienste zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="eead0-106">The debugger must call `Initialize` at creation time to initialize the debugging services.</span></span> <span data-ttu-id="eead0-107">Diese Methode muss aufgerufen werden, bevor eine andere Methode für `ICorDebug` aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="eead0-107">This method must be called before any other method on `ICorDebug` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eead0-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="eead0-108">Requirements</span></span>  
 <span data-ttu-id="eead0-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eead0-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eead0-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eead0-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eead0-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eead0-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eead0-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eead0-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eead0-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eead0-113">See also</span></span>

- [<span data-ttu-id="eead0-114">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="eead0-114">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
