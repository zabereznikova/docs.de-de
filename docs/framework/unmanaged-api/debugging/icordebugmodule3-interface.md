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
ms.openlocfilehash: 33acc4d9a0819c43d17c362fcbea2e7636521fd3
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792935"
---
# <a name="icordebugmodule3-interface"></a><span data-ttu-id="cb612-102">ICorDebugModule3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cb612-102">ICorDebugModule3 Interface</span></span>
<span data-ttu-id="cb612-103">Erstellt einen Symbolreader für ein dynamisches Modul.</span><span class="sxs-lookup"><span data-stu-id="cb612-103">Creates a symbol reader for a dynamic module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb612-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cb612-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="cb612-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="cb612-105">Methods</span></span>  
  
|<span data-ttu-id="cb612-106">-Methode</span><span class="sxs-lookup"><span data-stu-id="cb612-106">Method</span></span>|<span data-ttu-id="cb612-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cb612-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cb612-108">ICorDebugModule3::CreateReaderForInMemorySymbols-Methode</span><span class="sxs-lookup"><span data-stu-id="cb612-108">ICorDebugModule3::CreateReaderForInMemorySymbols Method</span></span>](icordebugmodule3-createreaderforinmemorysymbols-method.md)|<span data-ttu-id="cb612-109">Erstellt einen Symbol Reader (in der Regel [ISymUnmanagedReader-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)) für ein dynamisches Modul.</span><span class="sxs-lookup"><span data-stu-id="cb612-109">Creates a symbol reader (typically [ISymUnmanagedReader Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)) for a dynamic module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cb612-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cb612-110">Remarks</span></span>  
 <span data-ttu-id="cb612-111">Diese Schnittstelle erweitert logisch die Schnittstellen "ICorDebugModule" und "ICorDebugModule2".</span><span class="sxs-lookup"><span data-stu-id="cb612-111">This interface logically extends the "ICorDebugModule" and "ICorDebugModule2" interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cb612-112">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="cb612-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb612-113">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cb612-113">Requirements</span></span>  
 <span data-ttu-id="cb612-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb612-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb612-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cb612-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cb612-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cb612-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cb612-117">**.NET Framework Versionen:** 4,5, 4, 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="cb612-117">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>
  
## <a name="see-also"></a><span data-ttu-id="cb612-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cb612-118">See also</span></span>

- [<span data-ttu-id="cb612-119">ICorDebugRemoteTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cb612-119">ICorDebugRemoteTarget Interface</span></span>](icordebugremotetarget-interface.md)
- [<span data-ttu-id="cb612-120">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cb612-120">ICorDebug Interface</span></span>](icordebug-interface.md)

- [<span data-ttu-id="cb612-121">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="cb612-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
