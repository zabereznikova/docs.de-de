---
title: ICorDebugModule3::CreateReaderForInMemorySymbols-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugModule3.CreateReaderForInMemorySymbols
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule3::CreateReaderForInMemorySymbols
helpviewer_keywords:
- CreateReaderForInMemorySymbols method, ICorDebugModule3 interface [.NET Framework debugging]
- ICorDebugModule3::CreateReaderForInMemorySymbols method [.NET Framework debugging]
ms.assetid: af317171-d66d-4114-89eb-063554c74940
topic_type:
- apiref
ms.openlocfilehash: 2655151d34275b1b0fdc5d0903dd57fcea646014
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137303"
---
# <a name="icordebugmodule3createreaderforinmemorysymbols-method"></a><span data-ttu-id="72e94-102">ICorDebugModule3::CreateReaderForInMemorySymbols-Methode</span><span class="sxs-lookup"><span data-stu-id="72e94-102">ICorDebugModule3::CreateReaderForInMemorySymbols Method</span></span>
<span data-ttu-id="72e94-103">Erstellt einen debugsymbolreader für ein dynamisches Modul.</span><span class="sxs-lookup"><span data-stu-id="72e94-103">Creates a debug symbol reader for a dynamic module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72e94-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="72e94-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateReaderForInMemorySymbols (  
      [in] REFIID riid,  
      [out][iid_is(riid)] void **    ppObj  
```  
  
## <a name="parameters"></a><span data-ttu-id="72e94-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="72e94-105">Parameters</span></span>  
 <span data-ttu-id="72e94-106">riid</span><span class="sxs-lookup"><span data-stu-id="72e94-106">riid</span></span>  
 <span data-ttu-id="72e94-107">in Die IID der zurück zugebende com-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="72e94-107">[in] The IID of the COM interface to return.</span></span> <span data-ttu-id="72e94-108">In der Regel ist dies eine [ISymUnmanagedReader-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md).</span><span class="sxs-lookup"><span data-stu-id="72e94-108">Typically, this is an [ISymUnmanagedReader Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md).</span></span>  
  
 <span data-ttu-id="72e94-109">ppobj</span><span class="sxs-lookup"><span data-stu-id="72e94-109">ppObj</span></span>  
 <span data-ttu-id="72e94-110">vorgenommen Zeiger auf einen Zeiger auf die zurückgegebene Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="72e94-110">[out] Pointer to a pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="72e94-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="72e94-111">Return Value</span></span>  
 <span data-ttu-id="72e94-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="72e94-112">S_OK</span></span>  
 <span data-ttu-id="72e94-113">Der Reader wurde erfolgreich erstellt.</span><span class="sxs-lookup"><span data-stu-id="72e94-113">Successfully created the reader.</span></span>  
  
 <span data-ttu-id="72e94-114">CORDBG_E_MODULE_LOADED_FROM_DISK</span><span class="sxs-lookup"><span data-stu-id="72e94-114">CORDBG_E_MODULE_LOADED_FROM_DISK</span></span>  
 <span data-ttu-id="72e94-115">Das Modul ist kein in-Memory-oder dynamisches Modul.</span><span class="sxs-lookup"><span data-stu-id="72e94-115">The module is not an in-memory or dynamic module.</span></span>  
  
 <span data-ttu-id="72e94-116">CORDBG_E_SYMBOLS_NOT_AVAILABLE</span><span class="sxs-lookup"><span data-stu-id="72e94-116">CORDBG_E_SYMBOLS_NOT_AVAILABLE</span></span>  
 <span data-ttu-id="72e94-117">Es wurden keine Symbole von der Anwendung bereitgestellt oder sind noch nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="72e94-117">Symbols have not been supplied by the application or are not yet available.</span></span>  
  
 <span data-ttu-id="72e94-118">E_FAIL (oder andere E_-Rückgabecodes)</span><span class="sxs-lookup"><span data-stu-id="72e94-118">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="72e94-119">Der Reader kann nicht erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="72e94-119">Unable to create the reader.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="72e94-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="72e94-120">Remarks</span></span>  
 <span data-ttu-id="72e94-121">Diese Methode kann auch verwendet werden, um ein Symbol Reader-Objekt für in-Memory-Module (nicht dynamisch) zu erstellen, aber erst nach der ersten Verfügbarkeit der Symbole (angegeben durch den [UpdateModuleSymbols-Methoden](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-updatemodulesymbols-method.md) Rückruf).</span><span class="sxs-lookup"><span data-stu-id="72e94-121">This method can also be used to create a symbol reader object for in-memory (non-dynamic) modules, but only after the symbols are first available (indicated by the [UpdateModuleSymbols Method](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-updatemodulesymbols-method.md) callback).</span></span>  
  
 <span data-ttu-id="72e94-122">Diese Methode gibt jedes Mal, wenn Sie aufgerufen wird, eine neue Reader-Instanz zurück (z. b. [CComPtrBase:: cokreateinstance](/cpp/atl/reference/ccomptrbase-class#cocreateinstance)).</span><span class="sxs-lookup"><span data-stu-id="72e94-122">This method returns a new reader instance every time it is called (like [CComPtrBase::CoCreateInstance](/cpp/atl/reference/ccomptrbase-class#cocreateinstance)).</span></span> <span data-ttu-id="72e94-123">Daher sollte der Debugger das Ergebnis Zwischenspeichern und eine neue Instanz nur dann anfordern, wenn sich die zugrunde liegenden Daten möglicherweise geändert haben (d. h., wenn ein [LoadClass-Methoden](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) Rückruf empfangen wird).</span><span class="sxs-lookup"><span data-stu-id="72e94-123">Therefore, the debugger should cache the result and request a new instance only when the underlying data may have changed (that is, when a [LoadClass Method](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) callback is received).</span></span>  
  
 <span data-ttu-id="72e94-124">Für dynamische Module sind keine Symbole verfügbar, bis der erste Typ geladen wurde (wie durch den [LoadClass-Methoden](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) Rückruf angegeben).</span><span class="sxs-lookup"><span data-stu-id="72e94-124">Dynamic modules do not have any symbols available until the first type has been loaded (as indicated by the [LoadClass Method](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) callback).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72e94-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="72e94-125">Requirements</span></span>  
 <span data-ttu-id="72e94-126">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72e94-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72e94-127">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="72e94-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="72e94-128">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="72e94-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="72e94-129">**.NET Framework Versionen:** 4,5, 4, 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="72e94-129">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72e94-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="72e94-130">See also</span></span>

- [<span data-ttu-id="72e94-131">ICorDebugRemoteTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="72e94-131">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)
- [<span data-ttu-id="72e94-132">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="72e94-132">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [<span data-ttu-id="72e94-133">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="72e94-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
