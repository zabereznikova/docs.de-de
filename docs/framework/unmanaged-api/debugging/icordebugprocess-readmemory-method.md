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
ms.openlocfilehash: ef9e339c74b2d2785d758ed9c4adfc1901073253
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139363"
---
# <a name="icordebugprocessreadmemory-method"></a><span data-ttu-id="4c1a3-102">ICorDebugProcess::ReadMemory-Methode</span><span class="sxs-lookup"><span data-stu-id="4c1a3-102">ICorDebugProcess::ReadMemory Method</span></span>
<span data-ttu-id="4c1a3-103">Liest einen angegebenen Speicherbereich für diesen Prozess.</span><span class="sxs-lookup"><span data-stu-id="4c1a3-103">Reads a specified area of memory for this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c1a3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4c1a3-104">Syntax</span></span>  
  
```cpp  
HRESULT ReadMemory(  
    [in]  CORDB_ADDRESS address,   
    [in]  DWORD size,  
    [out, size_is(size), length_is(size)] BYTE buffer[],  
    [out] SIZE_T *read);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4c1a3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4c1a3-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="4c1a3-106">in Ein `CORDB_ADDRESS` Wert, der die Basisadresse des zu lesenden Speichers angibt.</span><span class="sxs-lookup"><span data-stu-id="4c1a3-106">[in] A `CORDB_ADDRESS` value that specifies the base address of the memory to be read.</span></span>  
  
 `size`  
 <span data-ttu-id="4c1a3-107">in Die Anzahl der Bytes, die aus dem Arbeitsspeicher gelesen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="4c1a3-107">[in] The number of bytes to be read from memory.</span></span>  
  
 `buffer`  
 <span data-ttu-id="4c1a3-108">vorgenommen Ein Puffer, der den Inhalt des Arbeitsspeichers empfängt.</span><span class="sxs-lookup"><span data-stu-id="4c1a3-108">[out] A buffer that receives the contents of the memory.</span></span>  
  
 `read`  
 <span data-ttu-id="4c1a3-109">vorgenommen Ein Zeiger auf die Anzahl von Bytes, die in den angegebenen Puffer übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="4c1a3-109">[out] A pointer to the number of bytes transferred into the specified buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4c1a3-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4c1a3-110">Remarks</span></span>  
 <span data-ttu-id="4c1a3-111">Die `ReadMemory`-Methode ist hauptsächlich für das Interop-Debuggen vorgesehen, um Speicherbereiche zu überprüfen, die vom nicht verwalteten Teil der zu debuggenden Komponente verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4c1a3-111">The `ReadMemory` method is primarily intended to be used by interop debugging to inspect memory regions that are being used by the unmanaged portion of the debuggee.</span></span> <span data-ttu-id="4c1a3-112">Diese Methode kann auch zum Lesen von MSIL-Code (Microsoft Intermediate Language) und nativem JIT-kompiliertem Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4c1a3-112">This method can also be used to read Microsoft intermediate language (MSIL) code and native JIT-compiled code.</span></span>  
  
 <span data-ttu-id="4c1a3-113">Alle verwalteten Breakpoints werden aus den Daten entfernt, die im `buffer`-Parameter zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="4c1a3-113">Any managed breakpoints will be removed from the data that is returned in the `buffer` parameter.</span></span> <span data-ttu-id="4c1a3-114">Für Native Breakpoints, die von [ICorDebugProcess2:: SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md)festgelegt werden, werden keine Anpassungen vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="4c1a3-114">No adjustments will be made for native breakpoints set by [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md).</span></span>  
  
 <span data-ttu-id="4c1a3-115">Es wird kein Zwischenspeichern des Prozess Arbeitsspeichers ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4c1a3-115">No caching of process memory is performed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c1a3-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4c1a3-116">Requirements</span></span>  
 <span data-ttu-id="4c1a3-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4c1a3-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c1a3-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4c1a3-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4c1a3-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4c1a3-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4c1a3-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c1a3-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
