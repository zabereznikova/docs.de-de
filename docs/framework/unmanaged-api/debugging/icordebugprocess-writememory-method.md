---
title: ICorDebugProcess::WriteMemory-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.WriteMemory
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::WriteMemory
helpviewer_keywords:
- ICorDebugProcess::WriteMemory method [.NET Framework debugging]
- WriteMemory method [.NET Framework debugging]
ms.assetid: d5c07d86-045d-4391-893b-0bcd2959f90e
topic_type:
- apiref
ms.openlocfilehash: 18416954517c3cac09d013b8075bd097305a1dca
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673963"
---
# <a name="icordebugprocesswritememory-method"></a><span data-ttu-id="6071f-102">ICorDebugProcess::WriteMemory-Methode</span><span class="sxs-lookup"><span data-stu-id="6071f-102">ICorDebugProcess::WriteMemory Method</span></span>

<span data-ttu-id="6071f-103">Schreibt Daten in diesem Prozess in einen Arbeitsspeicher Bereich.</span><span class="sxs-lookup"><span data-stu-id="6071f-103">Writes data to an area of memory in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6071f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6071f-104">Syntax</span></span>  
  
```cpp  
HRESULT WriteMemory(  
    [in]  CORDB_ADDRESS address,  
    [in]  DWORD size,  
    [in, size_is(size)] BYTE buffer[],  
    [out] SIZE_T *written);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6071f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6071f-105">Parameters</span></span>  

 `address`  
 <span data-ttu-id="6071f-106">in Ein- `CORDB_ADDRESS` Wert, der die Basisadresse des Speicherbereichs ist, in den Daten geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="6071f-106">[in] A `CORDB_ADDRESS` value that is the base address of the memory area to which data is written.</span></span> <span data-ttu-id="6071f-107">Vor der Datenübertragung überprüft das System, ob der Speicherbereich der angegebenen Größe, beginnend bei der Basisadresse, zum Schreiben zugänglich ist.</span><span class="sxs-lookup"><span data-stu-id="6071f-107">Before data transfer occurs, the system verifies that the memory area of the specified size, beginning at the base address, is accessible for writing.</span></span> <span data-ttu-id="6071f-108">Wenn nicht auf Sie zugegriffen werden kann, schlägt die Methode fehl.</span><span class="sxs-lookup"><span data-stu-id="6071f-108">If it is not accessible, the method fails.</span></span>  
  
 `size`  
 <span data-ttu-id="6071f-109">in Die Anzahl der Bytes, die in den Speicherbereich geschrieben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6071f-109">[in] The number of bytes to be written to the memory area.</span></span>  
  
 `buffer`  
 <span data-ttu-id="6071f-110">in Ein Puffer, der die zu schreibenden Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="6071f-110">[in] A buffer that contains data to be written.</span></span>  
  
 `written`  
 <span data-ttu-id="6071f-111">vorgenommen Ein Zeiger auf eine Variable, die die Anzahl von Bytes empfängt, die in diesem Prozess in den Speicherbereich geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="6071f-111">[out] A pointer to a variable that receives the number of bytes written to the memory area in this process.</span></span> <span data-ttu-id="6071f-112">Wenn `written` NULL ist, wird dieser Parameter ignoriert.</span><span class="sxs-lookup"><span data-stu-id="6071f-112">If `written` is NULL, this parameter is ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6071f-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6071f-113">Remarks</span></span>  

 <span data-ttu-id="6071f-114">Daten werden automatisch hinter Breakpoints geschrieben.</span><span class="sxs-lookup"><span data-stu-id="6071f-114">Data is automatically written behind any breakpoints.</span></span> <span data-ttu-id="6071f-115">In der .NET Framework Version 2,0 sollten Native Debugger diese Methode nicht verwenden, um Breakpoints in den Anweisungs Datenstrom einzufügen.</span><span class="sxs-lookup"><span data-stu-id="6071f-115">In the .NET Framework version 2.0, native debuggers should not use this method to inject breakpoints into the instruction stream.</span></span> <span data-ttu-id="6071f-116">Verwenden Sie stattdessen [ICorDebugProcess2:: Abort](icordebugprocess2-setunmanagedbreakpoint-method.md) .</span><span class="sxs-lookup"><span data-stu-id="6071f-116">Use [ICorDebugProcess2::SetUnmanagedBreakpoint](icordebugprocess2-setunmanagedbreakpoint-method.md) instead.</span></span>  
  
 <span data-ttu-id="6071f-117">Die- `WriteMemory` Methode sollte nur außerhalb von verwaltetem Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6071f-117">The `WriteMemory` method should be used only outside of managed code.</span></span> <span data-ttu-id="6071f-118">Diese Methode kann die Laufzeit beschädigt werden, wenn Sie nicht ordnungsgemäß verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6071f-118">This method can corrupt the runtime if used improperly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6071f-119">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="6071f-119">Requirements</span></span>  

 <span data-ttu-id="6071f-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6071f-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6071f-121">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6071f-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6071f-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6071f-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6071f-123">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6071f-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
