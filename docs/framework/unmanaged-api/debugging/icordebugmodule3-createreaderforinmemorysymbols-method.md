---
title: ICorDebugModule3::CreateReaderForInMemorySymbols-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule3.CreateReaderForInMemorySymbols
api_location: CorDebug.dll
api_type: COM
f1_keywords: ICorDebugModule3::CreateReaderForInMemorySymbols
helpviewer_keywords:
- CreateReaderForInMemorySymbols method, ICorDebugModule3 interface [.NET Framework debugging]
- ICorDebugModule3::CreateReaderForInMemorySymbols method [.NET Framework debugging]
ms.assetid: af317171-d66d-4114-89eb-063554c74940
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2838c6c1fe8641e343fac1a3efa82a39ee177abc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmodule3createreaderforinmemorysymbols-method"></a><span data-ttu-id="15217-102">ICorDebugModule3::CreateReaderForInMemorySymbols-Methode</span><span class="sxs-lookup"><span data-stu-id="15217-102">ICorDebugModule3::CreateReaderForInMemorySymbols Method</span></span>
<span data-ttu-id="15217-103">Erstellt einen Debug-Symbolreader für ein dynamisches Modul.</span><span class="sxs-lookup"><span data-stu-id="15217-103">Creates a debug symbol reader for a dynamic module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15217-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="15217-104">Syntax</span></span>  
  
```  
HRESULT CreateReaderForInMemorySymbols (  
      [in] REFIID riid,  
      [out][iid_is(riid)] void **    ppObj  
```  
  
#### <a name="parameters"></a><span data-ttu-id="15217-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="15217-105">Parameters</span></span>  
 <span data-ttu-id="15217-106">riid</span><span class="sxs-lookup"><span data-stu-id="15217-106">riid</span></span>  
 <span data-ttu-id="15217-107">[in] Die IID der COM-Schnittstelle zurück.</span><span class="sxs-lookup"><span data-stu-id="15217-107">[in] The IID of the COM interface to return.</span></span> <span data-ttu-id="15217-108">Dies ist normalerweise ein [ISymUnmanagedReader-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md).</span><span class="sxs-lookup"><span data-stu-id="15217-108">Typically, this is an [ISymUnmanagedReader Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md).</span></span>  
  
 <span data-ttu-id="15217-109">ppObj</span><span class="sxs-lookup"><span data-stu-id="15217-109">ppObj</span></span>  
 <span data-ttu-id="15217-110">[out] Zeiger auf einen Zeiger auf die zurückgegebene Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="15217-110">[out] Pointer to a pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="15217-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="15217-111">Return Value</span></span>  
 <span data-ttu-id="15217-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="15217-112">S_OK</span></span>  
 <span data-ttu-id="15217-113">Den Reader erstellt.</span><span class="sxs-lookup"><span data-stu-id="15217-113">Successfully created the reader.</span></span>  
  
 <span data-ttu-id="15217-114">CORDBG_E_MODULE_LOADED_FROM_DISK</span><span class="sxs-lookup"><span data-stu-id="15217-114">CORDBG_E_MODULE_LOADED_FROM_DISK</span></span>  
 <span data-ttu-id="15217-115">Das Modul ist kein im Arbeitsspeicher oder dynamisches Modul.</span><span class="sxs-lookup"><span data-stu-id="15217-115">The module is not an in-memory or dynamic module.</span></span>  
  
 <span data-ttu-id="15217-116">CORDBG_E_SYMBOLS_NOT_AVAILABLE</span><span class="sxs-lookup"><span data-stu-id="15217-116">CORDBG_E_SYMBOLS_NOT_AVAILABLE</span></span>  
 <span data-ttu-id="15217-117">Symbole nicht zur Verfügung gestellt wurden von der Anwendung, oder es sind noch nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="15217-117">Symbols have not been supplied by the application or are not yet available.</span></span>  
  
 <span data-ttu-id="15217-118">E_FAIL (oder andere E_-Rückgabecodes)</span><span class="sxs-lookup"><span data-stu-id="15217-118">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="15217-119">Erstellen den Reader nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="15217-119">Unable to create the reader.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="15217-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="15217-120">Remarks</span></span>  
 <span data-ttu-id="15217-121">Diese Methode kann auch sein verwendet zum Erstellen eines Symbols Reader-Objekts für Module im Arbeitsspeicher (nicht dynamisch), jedoch nur, nachdem zuerst die Symbole verfügbar sind (angegeben durch die [UpdateModuleSymbols-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-updatemodulesymbols-method.md) Rückruf).</span><span class="sxs-lookup"><span data-stu-id="15217-121">This method can also be used to create a symbol reader object for in-memory (non-dynamic) modules, but only after the symbols are first available (indicated by the [UpdateModuleSymbols Method](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-updatemodulesymbols-method.md) callback).</span></span>  
  
 <span data-ttu-id="15217-122">Jedes Mal, wenn sie aufgerufen wird, gibt diese Methode eine neue Readerinstanz (z. B. [CComPtrBase:: CoCreateInstance](http://msdn.microsoft.com/library/c0965041-6cb6-40c5-b272-2b99f02668a6)).</span><span class="sxs-lookup"><span data-stu-id="15217-122">This method returns a new reader instance every time it is called (like [CComPtrBase::CoCreateInstance](http://msdn.microsoft.com/library/c0965041-6cb6-40c5-b272-2b99f02668a6)).</span></span> <span data-ttu-id="15217-123">Aus diesem Grund sollte der Debugger cache das Ergebnis und fordern Sie eine neue Instanz nur, wenn die zugrunde liegenden Daten geändert haben, können (d. h. bei einem [LoadClass-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) Rückruf empfangen wird).</span><span class="sxs-lookup"><span data-stu-id="15217-123">Therefore, the debugger should cache the result and request a new instance only when the underlying data may have changed (that is, when a [LoadClass Method](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) callback is received).</span></span>  
  
 <span data-ttu-id="15217-124">Dynamische Module müssen keine verfügbaren Symbole, bis der erste Typ geladen wurde (durch die [LoadClass-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) Rückruf).</span><span class="sxs-lookup"><span data-stu-id="15217-124">Dynamic modules do not have any symbols available until the first type has been loaded (as indicated by the [LoadClass Method](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) callback).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15217-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="15217-125">Requirements</span></span>  
 <span data-ttu-id="15217-126">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15217-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15217-127">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="15217-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="15217-128">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="15217-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="15217-129">**.NET Framework-Versionen:** 4.5, 4, 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="15217-129">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15217-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="15217-130">See Also</span></span>  
 [<span data-ttu-id="15217-131">ICorDebugRemoteTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="15217-131">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)  
 [<span data-ttu-id="15217-132">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="15217-132">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
    
 [<span data-ttu-id="15217-133">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="15217-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
