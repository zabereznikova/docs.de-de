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
ms.openlocfilehash: 5cdd89ebdbb5abb9b001c1489a54bfb867808c5c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723427"
---
# <a name="icordebuginitialize-method"></a><span data-ttu-id="bdd6b-102">ICorDebug::Initialize-Methode</span><span class="sxs-lookup"><span data-stu-id="bdd6b-102">ICorDebug::Initialize Method</span></span>

<span data-ttu-id="bdd6b-103">Initialisiert das `ICorDebug`-Objekt.</span><span class="sxs-lookup"><span data-stu-id="bdd6b-103">Initializes the `ICorDebug` object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdd6b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bdd6b-104">Syntax</span></span>  
  
```cpp  
HRESULT Initialize ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="bdd6b-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bdd6b-105">Remarks</span></span>  

 <span data-ttu-id="bdd6b-106">Der Debugger muss zum `Initialize` Erstellungs Zeitpunkt aufzurufen, um die debuggingdienste zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="bdd6b-106">The debugger must call `Initialize` at creation time to initialize the debugging services.</span></span> <span data-ttu-id="bdd6b-107">Diese Methode muss aufgerufen werden, bevor eine andere Methode für `ICorDebug` aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="bdd6b-107">This method must be called before any other method on `ICorDebug` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bdd6b-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="bdd6b-108">Requirements</span></span>  

 <span data-ttu-id="bdd6b-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bdd6b-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bdd6b-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bdd6b-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bdd6b-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bdd6b-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bdd6b-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bdd6b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdd6b-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bdd6b-113">See also</span></span>

- [<span data-ttu-id="bdd6b-114">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bdd6b-114">ICorDebug Interface</span></span>](icordebug-interface.md)
