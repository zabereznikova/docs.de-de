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
ms.openlocfilehash: 543a1a3c79b6cf3eb799da5844f35286dfa91940
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709556"
---
# <a name="icordebugmodule3-interface"></a><span data-ttu-id="17c41-102">ICorDebugModule3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="17c41-102">ICorDebugModule3 Interface</span></span>

<span data-ttu-id="17c41-103">Erstellt einen Symbolreader für ein dynamisches Modul.</span><span class="sxs-lookup"><span data-stu-id="17c41-103">Creates a symbol reader for a dynamic module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17c41-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="17c41-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="17c41-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="17c41-105">Methods</span></span>  
  
|<span data-ttu-id="17c41-106">Methode</span><span class="sxs-lookup"><span data-stu-id="17c41-106">Method</span></span>|<span data-ttu-id="17c41-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="17c41-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="17c41-108">ICorDebugModule3::CreateReaderForInMemorySymbols-Methode</span><span class="sxs-lookup"><span data-stu-id="17c41-108">ICorDebugModule3::CreateReaderForInMemorySymbols Method</span></span>](icordebugmodule3-createreaderforinmemorysymbols-method.md)|<span data-ttu-id="17c41-109">Erstellt einen Symbol Reader (in der Regel [ISymUnmanagedReader-Schnittstelle](../diagnostics/isymunmanagedreader-interface.md)) für ein dynamisches Modul.</span><span class="sxs-lookup"><span data-stu-id="17c41-109">Creates a symbol reader (typically [ISymUnmanagedReader Interface](../diagnostics/isymunmanagedreader-interface.md)) for a dynamic module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="17c41-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="17c41-110">Remarks</span></span>  

 <span data-ttu-id="17c41-111">Diese Schnittstelle erweitert logisch die Schnittstellen "ICorDebugModule" und "ICorDebugModule2".</span><span class="sxs-lookup"><span data-stu-id="17c41-111">This interface logically extends the "ICorDebugModule" and "ICorDebugModule2" interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="17c41-112">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="17c41-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17c41-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="17c41-113">Requirements</span></span>  

 <span data-ttu-id="17c41-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17c41-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17c41-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="17c41-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="17c41-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="17c41-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="17c41-117">**.NET Framework Versionen:** 4,5, 4, 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="17c41-117">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>
  
## <a name="see-also"></a><span data-ttu-id="17c41-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="17c41-118">See also</span></span>

- [<span data-ttu-id="17c41-119">ICorDebugRemoteTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="17c41-119">ICorDebugRemoteTarget Interface</span></span>](icordebugremotetarget-interface.md)
- [<span data-ttu-id="17c41-120">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="17c41-120">ICorDebug Interface</span></span>](icordebug-interface.md)

- [<span data-ttu-id="17c41-121">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="17c41-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
