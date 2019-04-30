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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a340086be042c790ae7bf750759ff80f7c9eaf23
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61942440"
---
# <a name="icordebugmodule3-interface"></a><span data-ttu-id="a4fcf-102">ICorDebugModule3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a4fcf-102">ICorDebugModule3 Interface</span></span>
<span data-ttu-id="a4fcf-103">Erstellt einen Symbolreader für ein dynamisches Modul.</span><span class="sxs-lookup"><span data-stu-id="a4fcf-103">Creates a symbol reader for a dynamic module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4fcf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a4fcf-104">Syntax</span></span>  
  
```  
interface ICorDebugModule3 : IUnknown  
{  
    HRESULT CreateReaderForInMemorySymbols  
      (  
      [in] REFIID riid,  
      [out][iid_is(riid)] void **  ppObj  
      );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="a4fcf-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="a4fcf-105">Methods</span></span>  
  
|<span data-ttu-id="a4fcf-106">Methode</span><span class="sxs-lookup"><span data-stu-id="a4fcf-106">Method</span></span>|<span data-ttu-id="a4fcf-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a4fcf-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a4fcf-108">ICorDebugModule3::CreateReaderForInMemorySymbols-Methode</span><span class="sxs-lookup"><span data-stu-id="a4fcf-108">ICorDebugModule3::CreateReaderForInMemorySymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule3-createreaderforinmemorysymbols-method.md)|<span data-ttu-id="a4fcf-109">Erstellt einen Symbolreader (in der Regel [ISymUnmanagedReader-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)) für ein dynamisches Modul.</span><span class="sxs-lookup"><span data-stu-id="a4fcf-109">Creates a symbol reader (typically [ISymUnmanagedReader Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)) for a dynamic module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a4fcf-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a4fcf-110">Remarks</span></span>  
 <span data-ttu-id="a4fcf-111">Diese Schnittstelle erweitert logisch die Schnittstellen "ICorDebugModule" und "ICorDebugModule2".</span><span class="sxs-lookup"><span data-stu-id="a4fcf-111">This interface logically extends the "ICorDebugModule" and "ICorDebugModule2" interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a4fcf-112">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="a4fcf-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4fcf-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a4fcf-113">Requirements</span></span>  
 <span data-ttu-id="a4fcf-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a4fcf-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4fcf-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a4fcf-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a4fcf-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a4fcf-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a4fcf-117">**.NET Framework-Versionen:** 4.5, 4, 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="a4fcf-117">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a4fcf-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a4fcf-118">See also</span></span>

- [<span data-ttu-id="a4fcf-119">ICorDebugRemoteTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a4fcf-119">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)
- [<span data-ttu-id="a4fcf-120">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a4fcf-120">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [<span data-ttu-id="a4fcf-121">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="a4fcf-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
