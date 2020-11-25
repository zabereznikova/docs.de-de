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
ms.openlocfilehash: 1615d00a9a25cd2f4aa7d9b84de54b5e7670a3fc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730582"
---
# <a name="icordebugmanagedcallbackupdatemodulesymbols-method"></a><span data-ttu-id="268c7-102">ICorDebugManagedCallback::UpdateModuleSymbols-Methode</span><span class="sxs-lookup"><span data-stu-id="268c7-102">ICorDebugManagedCallback::UpdateModuleSymbols Method</span></span>

<span data-ttu-id="268c7-103">Benachrichtigt den Debugger, dass die Symbole für ein Common Language Runtime Modul geändert wurden.</span><span class="sxs-lookup"><span data-stu-id="268c7-103">Notifies the debugger that the symbols for a common language runtime module have changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="268c7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="268c7-104">Syntax</span></span>  
  
```cpp  
HRESULT UpdateModuleSymbols (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugModule    *pModule,  
    [in] IStream            *pSymbolStream  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="268c7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="268c7-105">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="268c7-106">in Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne mit dem Modul darstellt, in dem sich die Symbole geändert haben.</span><span class="sxs-lookup"><span data-stu-id="268c7-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the module in which the symbols have changed.</span></span>  
  
 `pModule`  
 <span data-ttu-id="268c7-107">in Ein Zeiger auf ein ICorDebugModule-Objekt, das das Modul darstellt, in dem die Symbole geändert wurden.</span><span class="sxs-lookup"><span data-stu-id="268c7-107">[in] A pointer to an ICorDebugModule object that represents the module in which the symbols have changed.</span></span>  
  
 `pSymbolStream`  
 <span data-ttu-id="268c7-108">in Ein Zeiger auf ein Win32-com- `IStream` Objekt, das die geänderten Symbole enthält.</span><span class="sxs-lookup"><span data-stu-id="268c7-108">[in] A pointer to a Win32 COM `IStream` object that contains the modified symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="268c7-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="268c7-109">Remarks</span></span>  

 <span data-ttu-id="268c7-110">Diese Methode bietet die Möglichkeit, die Debugger-Ansicht der Symbole eines Moduls zu aktualisieren, indem [ISymUnmanagedReader:: UpdateSymbolStore](../diagnostics/isymunmanagedreader-updatesymbolstore-method.md) oder [ISymUnmanagedReader:: ReplaceSymbolStore](../diagnostics/isymunmanagedreader-replacesymbolstore-method.md)aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="268c7-110">This method provides an opportunity to update the debugger's view of a module's symbols by calling [ISymUnmanagedReader::UpdateSymbolStore](../diagnostics/isymunmanagedreader-updatesymbolstore-method.md) or [ISymUnmanagedReader::ReplaceSymbolStore](../diagnostics/isymunmanagedreader-replacesymbolstore-method.md).</span></span>  
  
 <span data-ttu-id="268c7-111">Dieser Rückruf kann mehrmals für dasselbe Modul auftreten.</span><span class="sxs-lookup"><span data-stu-id="268c7-111">This callback can occur multiple times for the same module.</span></span>  
  
 <span data-ttu-id="268c7-112">Ein Debugger sollte versuchen, nicht gebundene Breakpoints auf Quell Ebene zu binden.</span><span class="sxs-lookup"><span data-stu-id="268c7-112">A debugger should try to bind unbound source-level breakpoints.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="268c7-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="268c7-113">Requirements</span></span>  

 <span data-ttu-id="268c7-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="268c7-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="268c7-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="268c7-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="268c7-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="268c7-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="268c7-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="268c7-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="268c7-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="268c7-118">See also</span></span>

- [<span data-ttu-id="268c7-119">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="268c7-119">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
