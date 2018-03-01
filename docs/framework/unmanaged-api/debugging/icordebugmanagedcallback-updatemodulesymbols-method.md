---
title: ICorDebugManagedCallback::UpdateModuleSymbols-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ad5a84268f3810a1fb73a21a6bd8106e82ccbd78
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbackupdatemodulesymbols-method"></a><span data-ttu-id="7531c-102">ICorDebugManagedCallback::UpdateModuleSymbols-Methode</span><span class="sxs-lookup"><span data-stu-id="7531c-102">ICorDebugManagedCallback::UpdateModuleSymbols Method</span></span>
<span data-ttu-id="7531c-103">Benachrichtigt den Debugger, dass die Symbole für eine common Language Runtime-Modul geändert wurden.</span><span class="sxs-lookup"><span data-stu-id="7531c-103">Notifies the debugger that the symbols for a common language runtime module have changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7531c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7531c-104">Syntax</span></span>  
  
```  
HRESULT UpdateModuleSymbols (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugModule    *pModule,  
    [in] IStream            *pSymbolStream  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7531c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7531c-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="7531c-106">[in] Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne mit dem Modul, in dem die Symbole geändert haben, darstellt.</span><span class="sxs-lookup"><span data-stu-id="7531c-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the module in which the symbols have changed.</span></span>  
  
 `pModule`  
 <span data-ttu-id="7531c-107">[in] Ein Zeiger auf ein ICorDebugModule-Objekt, das das Modul darstellt, in dem die Symbole geändert haben.</span><span class="sxs-lookup"><span data-stu-id="7531c-107">[in] A pointer to an ICorDebugModule object that represents the module in which the symbols have changed.</span></span>  
  
 `pSymbolStream`  
 <span data-ttu-id="7531c-108">[in] Ein Zeiger auf eine Win32-COM- `IStream` -Objekt, das die geänderten Symbole enthält.</span><span class="sxs-lookup"><span data-stu-id="7531c-108">[in] A pointer to a Win32 COM `IStream` object that contains the modified symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7531c-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7531c-109">Remarks</span></span>  
 <span data-ttu-id="7531c-110">Diese Methode bietet die Möglichkeit zum Aktualisieren des Debuggers anzeigen von Symbolen für ein Modul durch Aufrufen von [ISymUnmanagedReader:: UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) oder [ISymUnmanagedReader:: ReplaceSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-replacesymbolstore-method.md).</span><span class="sxs-lookup"><span data-stu-id="7531c-110">This method provides an opportunity to update the debugger's view of a module's symbols by calling [ISymUnmanagedReader::UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) or [ISymUnmanagedReader::ReplaceSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-replacesymbolstore-method.md).</span></span>  
  
 <span data-ttu-id="7531c-111">Dieser Rückruf kann mehrmals für dasselbe Modul auftreten.</span><span class="sxs-lookup"><span data-stu-id="7531c-111">This callback can occur multiple times for the same module.</span></span>  
  
 <span data-ttu-id="7531c-112">Ein Debugger sollten ungebundenen auf Quellcodeebene Haltepunkte zu binden.</span><span class="sxs-lookup"><span data-stu-id="7531c-112">A debugger should try to bind unbound source-level breakpoints.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7531c-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7531c-113">Requirements</span></span>  
 <span data-ttu-id="7531c-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7531c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7531c-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7531c-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7531c-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7531c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7531c-117">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7531c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7531c-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7531c-118">See Also</span></span>  
 [<span data-ttu-id="7531c-119">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7531c-119">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
