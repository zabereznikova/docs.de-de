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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 931a0cbd8dd15a62780a7bcf03d3d354f552232c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54628343"
---
# <a name="icordebugmodule3createreaderforinmemorysymbols-method"></a><span data-ttu-id="cee57-102">ICorDebugModule3::CreateReaderForInMemorySymbols-Methode</span><span class="sxs-lookup"><span data-stu-id="cee57-102">ICorDebugModule3::CreateReaderForInMemorySymbols Method</span></span>
<span data-ttu-id="cee57-103">Erstellt einen Debug-Symbolreader für ein dynamisches Modul.</span><span class="sxs-lookup"><span data-stu-id="cee57-103">Creates a debug symbol reader for a dynamic module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cee57-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cee57-104">Syntax</span></span>  
  
```  
HRESULT CreateReaderForInMemorySymbols (  
      [in] REFIID riid,  
      [out][iid_is(riid)] void **    ppObj  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cee57-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cee57-105">Parameters</span></span>  
 <span data-ttu-id="cee57-106">riid</span><span class="sxs-lookup"><span data-stu-id="cee57-106">riid</span></span>  
 <span data-ttu-id="cee57-107">[in] Die IID der COM-Schnittstelle zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="cee57-107">[in] The IID of the COM interface to return.</span></span> <span data-ttu-id="cee57-108">Dies ist normalerweise ein [ISymUnmanagedReader-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md).</span><span class="sxs-lookup"><span data-stu-id="cee57-108">Typically, this is an [ISymUnmanagedReader Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md).</span></span>  
  
 <span data-ttu-id="cee57-109">ppObj</span><span class="sxs-lookup"><span data-stu-id="cee57-109">ppObj</span></span>  
 <span data-ttu-id="cee57-110">[out] Zeiger auf einen Zeiger auf die zurückgegebene Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="cee57-110">[out] Pointer to a pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cee57-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="cee57-111">Return Value</span></span>  
 <span data-ttu-id="cee57-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="cee57-112">S_OK</span></span>  
 <span data-ttu-id="cee57-113">Wurde erfolgreich erstellt. den Reader.</span><span class="sxs-lookup"><span data-stu-id="cee57-113">Successfully created the reader.</span></span>  
  
 <span data-ttu-id="cee57-114">CORDBG_E_MODULE_LOADED_FROM_DISK</span><span class="sxs-lookup"><span data-stu-id="cee57-114">CORDBG_E_MODULE_LOADED_FROM_DISK</span></span>  
 <span data-ttu-id="cee57-115">Das Modul ist es sich nicht um ein im Arbeitsspeicher oder dynamischen Modul.</span><span class="sxs-lookup"><span data-stu-id="cee57-115">The module is not an in-memory or dynamic module.</span></span>  
  
 <span data-ttu-id="cee57-116">CORDBG_E_SYMBOLS_NOT_AVAILABLE</span><span class="sxs-lookup"><span data-stu-id="cee57-116">CORDBG_E_SYMBOLS_NOT_AVAILABLE</span></span>  
 <span data-ttu-id="cee57-117">Symbole nicht von der Anwendung bereitgestellt haben, oder es sind noch nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="cee57-117">Symbols have not been supplied by the application or are not yet available.</span></span>  
  
 <span data-ttu-id="cee57-118">E_FAIL (oder andere E_-Rückgabecodes)</span><span class="sxs-lookup"><span data-stu-id="cee57-118">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="cee57-119">Erstellen des Readers nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="cee57-119">Unable to create the reader.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cee57-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cee57-120">Remarks</span></span>  
 <span data-ttu-id="cee57-121">Diese Methode kann auch sein verwendet, um ein Symbol Reader-Objekt zu (nicht dynamisch) im Arbeitsspeicher-Modulen zu erstellen, aber nur, wenn die Symbole zuerst zur Verfügung stehen (angegeben durch die [UpdateModuleSymbols-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-updatemodulesymbols-method.md) Rückruf).</span><span class="sxs-lookup"><span data-stu-id="cee57-121">This method can also be used to create a symbol reader object for in-memory (non-dynamic) modules, but only after the symbols are first available (indicated by the [UpdateModuleSymbols Method](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-updatemodulesymbols-method.md) callback).</span></span>  
  
 <span data-ttu-id="cee57-122">Diese Methode gibt eine neue Readerinstanz zurück, jedes Mal, wenn sie aufgerufen wird (z. B. [CComPtrBase:: CoCreateInstance](/cpp/atl/reference/ccomptrbase-class#cocreateinstance)).</span><span class="sxs-lookup"><span data-stu-id="cee57-122">This method returns a new reader instance every time it is called (like [CComPtrBase::CoCreateInstance](/cpp/atl/reference/ccomptrbase-class#cocreateinstance)).</span></span> <span data-ttu-id="cee57-123">Aus diesem Grund sollte der Debugger Zwischenspeicherung des Ergebnisses und fordern Sie eine neue Instanz nur, wenn die zugrunde liegenden Daten geändert haben können (d. h. bei einer [LoadClass-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) -Rückruf empfangen wird).</span><span class="sxs-lookup"><span data-stu-id="cee57-123">Therefore, the debugger should cache the result and request a new instance only when the underlying data may have changed (that is, when a [LoadClass Method](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) callback is received).</span></span>  
  
 <span data-ttu-id="cee57-124">Dynamische Module müssen keine verfügbaren Symbole aus, bis der erste Typ geladen wurde (wie durch die [LoadClass-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) Rückruf).</span><span class="sxs-lookup"><span data-stu-id="cee57-124">Dynamic modules do not have any symbols available until the first type has been loaded (as indicated by the [LoadClass Method](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) callback).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cee57-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cee57-125">Requirements</span></span>  
 <span data-ttu-id="cee57-126">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cee57-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cee57-127">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cee57-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cee57-128">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cee57-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cee57-129">**.NET Framework-Versionen:** 4.5, 4, 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="cee57-129">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cee57-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cee57-130">See also</span></span>
- [<span data-ttu-id="cee57-131">ICorDebugRemoteTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cee57-131">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)
- [<span data-ttu-id="cee57-132">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cee57-132">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [<span data-ttu-id="cee57-133">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="cee57-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
