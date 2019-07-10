---
title: ICorDebugProcess::ReadMemory-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.ReadMemory
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::ReadMemory
helpviewer_keywords:
- ReadMemory method [.NET Framework debugging]
- ICorDebugProcess::ReadMemory method [.NET Framework debugging]
ms.assetid: 28e4b2f6-9589-445c-be24-24a3306795e7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0d74da502492065dbffb5e5499581263760636c7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737070"
---
# <a name="icordebugprocessreadmemory-method"></a><span data-ttu-id="f9640-102">ICorDebugProcess::ReadMemory-Methode</span><span class="sxs-lookup"><span data-stu-id="f9640-102">ICorDebugProcess::ReadMemory Method</span></span>
<span data-ttu-id="f9640-103">Liest einen angegebenen Bereich des Arbeitsspeichers für diesen Prozess.</span><span class="sxs-lookup"><span data-stu-id="f9640-103">Reads a specified area of memory for this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9640-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f9640-104">Syntax</span></span>  
  
```cpp  
HRESULT ReadMemory(  
    [in]  CORDB_ADDRESS address,   
    [in]  DWORD size,  
    [out, size_is(size), length_is(size)] BYTE buffer[],  
    [out] SIZE_T *read);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f9640-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f9640-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="f9640-106">[in] Ein `CORDB_ADDRESS` Wert, der angibt, die Basisadresse des Arbeitsspeichers, die gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="f9640-106">[in] A `CORDB_ADDRESS` value that specifies the base address of the memory to be read.</span></span>  
  
 `size`  
 <span data-ttu-id="f9640-107">[in] Die Anzahl der Bytes, die aus dem Arbeitsspeicher gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="f9640-107">[in] The number of bytes to be read from memory.</span></span>  
  
 `buffer`  
 <span data-ttu-id="f9640-108">[out] Ein Puffer, der den Inhalt des Arbeitsspeichers empfängt.</span><span class="sxs-lookup"><span data-stu-id="f9640-108">[out] A buffer that receives the contents of the memory.</span></span>  
  
 `read`  
 <span data-ttu-id="f9640-109">[out] Ein Zeiger auf die Anzahl der Bytes, die in den angegebenen Puffer übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="f9640-109">[out] A pointer to the number of bytes transferred into the specified buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f9640-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f9640-110">Remarks</span></span>  
 <span data-ttu-id="f9640-111">Die `ReadMemory` Methode dient in erster Linie von interop-Debuggen verwendet werden, um Speicherbereiche zu überprüfen, die durch den nicht verwalteten Teil der zu debuggenden Komponente verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f9640-111">The `ReadMemory` method is primarily intended to be used by interop debugging to inspect memory regions that are being used by the unmanaged portion of the debuggee.</span></span> <span data-ttu-id="f9640-112">Diese Methode kann auch verwendet werden, zum Lesen von Microsoft intermediate Language (MSIL)-Code und das native JIT-kompiliertem Code.</span><span class="sxs-lookup"><span data-stu-id="f9640-112">This method can also be used to read Microsoft intermediate language (MSIL) code and native JIT-compiled code.</span></span>  
  
 <span data-ttu-id="f9640-113">Alle verwalteten Haltepunkte aus den Daten, die in zurückgegeben werden, entfernt werden die `buffer` Parameter.</span><span class="sxs-lookup"><span data-stu-id="f9640-113">Any managed breakpoints will be removed from the data that is returned in the `buffer` parameter.</span></span> <span data-ttu-id="f9640-114">Werden keine Anpassungen vorgenommen werden, für native Haltepunkte, indem festlegen [ICorDebugProcess2:: SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md).</span><span class="sxs-lookup"><span data-stu-id="f9640-114">No adjustments will be made for native breakpoints set by [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md).</span></span>  
  
 <span data-ttu-id="f9640-115">Kein Zwischenspeichern der Prozessspeicher wird ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f9640-115">No caching of process memory is performed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9640-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f9640-116">Requirements</span></span>  
 <span data-ttu-id="f9640-117">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f9640-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9640-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f9640-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f9640-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f9640-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f9640-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9640-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
