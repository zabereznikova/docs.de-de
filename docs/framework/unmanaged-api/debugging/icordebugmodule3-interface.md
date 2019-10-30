---
title: ICorDebugModule3-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugModule3
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule3
helpviewer_keywords:
- ICorDebugModule3 interface [.NET Framework debugging]
ms.assetid: 0b69f945-263a-4e11-8512-89d27f6ea296
topic_type:
- apiref
ms.openlocfilehash: 07919398b658d735fe4c9818ab24d27d586b6629
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122561"
---
# <a name="icordebugmodule3-interface"></a><span data-ttu-id="8cb40-102">ICorDebugModule3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8cb40-102">ICorDebugModule3 Interface</span></span>
<span data-ttu-id="8cb40-103">Erstellt einen Symbolreader für ein dynamisches Modul.</span><span class="sxs-lookup"><span data-stu-id="8cb40-103">Creates a symbol reader for a dynamic module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8cb40-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8cb40-104">Syntax</span></span>  
  
```cpp  
interface ICorDebugModule3 : IUnknown  
{  
    HRESULT CreateReaderForInMemorySymbols  
      (  
      [in] REFIID riid,  
      [out][iid_is(riid)] void **  ppObj  
      );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="8cb40-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="8cb40-105">Methods</span></span>  
  
|<span data-ttu-id="8cb40-106">Methode</span><span class="sxs-lookup"><span data-stu-id="8cb40-106">Method</span></span>|<span data-ttu-id="8cb40-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8cb40-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8cb40-108">ICorDebugModule3::CreateReaderForInMemorySymbols-Methode</span><span class="sxs-lookup"><span data-stu-id="8cb40-108">ICorDebugModule3::CreateReaderForInMemorySymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule3-createreaderforinmemorysymbols-method.md)|<span data-ttu-id="8cb40-109">Erstellt einen Symbol Reader (in der Regel [ISymUnmanagedReader-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)) für ein dynamisches Modul.</span><span class="sxs-lookup"><span data-stu-id="8cb40-109">Creates a symbol reader (typically [ISymUnmanagedReader Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)) for a dynamic module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8cb40-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8cb40-110">Remarks</span></span>  
 <span data-ttu-id="8cb40-111">Diese Schnittstelle erweitert logisch die Schnittstellen "ICorDebugModule" und "ICorDebugModule2".</span><span class="sxs-lookup"><span data-stu-id="8cb40-111">This interface logically extends the "ICorDebugModule" and "ICorDebugModule2" interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8cb40-112">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="8cb40-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8cb40-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8cb40-113">Requirements</span></span>  
 <span data-ttu-id="8cb40-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8cb40-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8cb40-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8cb40-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8cb40-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8cb40-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8cb40-117">**.NET Framework Versionen:** 4,5, 4, 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="8cb40-117">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8cb40-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8cb40-118">See also</span></span>

- [<span data-ttu-id="8cb40-119">ICorDebugRemoteTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8cb40-119">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)
- [<span data-ttu-id="8cb40-120">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8cb40-120">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [<span data-ttu-id="8cb40-121">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="8cb40-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
