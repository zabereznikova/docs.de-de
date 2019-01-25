---
title: ICorDebugManagedCallback::UpdateModuleSymbols-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UpdateModuleSymbols
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UpdateModuleSymbols
helpviewer_keywords:
- UpdateModuleSymbols method [.NET Framework debugging]
- ICorDebugManagedCallback::UpdateModuleSymbols method [.NET Framework debugging]
ms.assetid: 0863f644-58e8-45a0-b0c3-a28e99b20938
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7b66cc09eda1fe5ea46a55b6239e05b5acec851c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54566904"
---
# <a name="icordebugmanagedcallbackupdatemodulesymbols-method"></a><span data-ttu-id="6b424-102">ICorDebugManagedCallback::UpdateModuleSymbols-Methode</span><span class="sxs-lookup"><span data-stu-id="6b424-102">ICorDebugManagedCallback::UpdateModuleSymbols Method</span></span>
<span data-ttu-id="6b424-103">Benachrichtigt den Debugger, dass die Symbole für eine common Language Runtime-Modul geändert haben.</span><span class="sxs-lookup"><span data-stu-id="6b424-103">Notifies the debugger that the symbols for a common language runtime module have changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b424-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6b424-104">Syntax</span></span>  
  
```  
HRESULT UpdateModuleSymbols (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugModule    *pModule,  
    [in] IStream            *pSymbolStream  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6b424-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6b424-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="6b424-106">[in] Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne, die das Modul, in dem die Symbole geändert haben, darstellt.</span><span class="sxs-lookup"><span data-stu-id="6b424-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the module in which the symbols have changed.</span></span>  
  
 `pModule`  
 <span data-ttu-id="6b424-107">[in] Ein Zeiger auf ein ICorDebugModule-Objekt, das das Modul darstellt, in dem die Symbole geändert haben.</span><span class="sxs-lookup"><span data-stu-id="6b424-107">[in] A pointer to an ICorDebugModule object that represents the module in which the symbols have changed.</span></span>  
  
 `pSymbolStream`  
 <span data-ttu-id="6b424-108">[in] Ein Zeiger auf eine Win32-COM- `IStream` -Objekt, das die geänderten Symbole enthält.</span><span class="sxs-lookup"><span data-stu-id="6b424-108">[in] A pointer to a Win32 COM `IStream` object that contains the modified symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6b424-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6b424-109">Remarks</span></span>  
 <span data-ttu-id="6b424-110">Diese Methode bietet eine Möglichkeit, den datenschnellansichten des Debuggers Ansicht des Symbole eines Moduls durch den Aufruf [ISymUnmanagedReader:: UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) oder [ISymUnmanagedReader:: ReplaceSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-replacesymbolstore-method.md).</span><span class="sxs-lookup"><span data-stu-id="6b424-110">This method provides an opportunity to update the debugger's view of a module's symbols by calling [ISymUnmanagedReader::UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) or [ISymUnmanagedReader::ReplaceSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-replacesymbolstore-method.md).</span></span>  
  
 <span data-ttu-id="6b424-111">Dieser Rückruf kann mehrmals für dasselbe Modul auftreten.</span><span class="sxs-lookup"><span data-stu-id="6b424-111">This callback can occur multiple times for the same module.</span></span>  
  
 <span data-ttu-id="6b424-112">Ein Debugger sollten ungebundenen auf Quellcodeebene Haltepunkte zu binden.</span><span class="sxs-lookup"><span data-stu-id="6b424-112">A debugger should try to bind unbound source-level breakpoints.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b424-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6b424-113">Requirements</span></span>  
 <span data-ttu-id="6b424-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6b424-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b424-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6b424-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6b424-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6b424-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6b424-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b424-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b424-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6b424-118">See also</span></span>
- [<span data-ttu-id="6b424-119">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6b424-119">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
