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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2e9d640fb1c9dae5bb195baa504e560ba8e45821
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61930298"
---
# <a name="icordebugprocesswritememory-method"></a><span data-ttu-id="562c0-102">ICorDebugProcess::WriteMemory-Methode</span><span class="sxs-lookup"><span data-stu-id="562c0-102">ICorDebugProcess::WriteMemory Method</span></span>
<span data-ttu-id="562c0-103">Schreibt Daten in einem Bereich des Arbeitsspeichers in diesem Prozess.</span><span class="sxs-lookup"><span data-stu-id="562c0-103">Writes data to an area of memory in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="562c0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="562c0-104">Syntax</span></span>  
  
```  
HRESULT WriteMemory(  
    [in]  CORDB_ADDRESS address,  
    [in]  DWORD size,  
    [in, size_is(size)] BYTE buffer[],  
    [out] SIZE_T *written);  
```  
  
## <a name="parameters"></a><span data-ttu-id="562c0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="562c0-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="562c0-106">[in] Ein `CORDB_ADDRESS` -Wert, der die Basisadresse des Speicherbereichs, welche Daten geschrieben.</span><span class="sxs-lookup"><span data-stu-id="562c0-106">[in] A `CORDB_ADDRESS` value that is the base address of the memory area to which data is written.</span></span> <span data-ttu-id="562c0-107">Bevor die Datenübertragung erfolgt, das System überprüft, ob der Speicherbereich, der angegebenen Größe, beginnend an der Basisadresse, zum Schreiben zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="562c0-107">Before data transfer occurs, the system verifies that the memory area of the specified size, beginning at the base address, is accessible for writing.</span></span> <span data-ttu-id="562c0-108">Ist dies nicht zugegriffen werden kann, schlägt die Methode fehl.</span><span class="sxs-lookup"><span data-stu-id="562c0-108">If it is not accessible, the method fails.</span></span>  
  
 `size`  
 <span data-ttu-id="562c0-109">[in] Die Anzahl der Bytes in den Speicherbereich geschrieben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="562c0-109">[in] The number of bytes to be written to the memory area.</span></span>  
  
 `buffer`  
 <span data-ttu-id="562c0-110">[in] Ein Puffer, der zu schreibenden Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="562c0-110">[in] A buffer that contains data to be written.</span></span>  
  
 `written`  
 <span data-ttu-id="562c0-111">[out] Ein Zeiger auf eine Variable, die Anzahl der Bytes, die in den Speicherbereich in diesem Prozess geschrieben empfängt.</span><span class="sxs-lookup"><span data-stu-id="562c0-111">[out] A pointer to a variable that receives the number of bytes written to the memory area in this process.</span></span> <span data-ttu-id="562c0-112">Wenn `written` NULL ist, dieser Parameter wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="562c0-112">If `written` is NULL, this parameter is ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="562c0-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="562c0-113">Remarks</span></span>  
 <span data-ttu-id="562c0-114">Daten werden automatisch hinter die Haltepunkte geschrieben.</span><span class="sxs-lookup"><span data-stu-id="562c0-114">Data is automatically written behind any breakpoints.</span></span> <span data-ttu-id="562c0-115">In .NET Framework, Version 2.0 verwenden systemeigenen Debugger nicht diese Methode, Haltepunkte in den Anweisungsstream einzufügen.</span><span class="sxs-lookup"><span data-stu-id="562c0-115">In the .NET Framework version 2.0, native debuggers should not use this method to inject breakpoints into the instruction stream.</span></span> <span data-ttu-id="562c0-116">Verwendung [ICorDebugProcess2:: SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md) stattdessen.</span><span class="sxs-lookup"><span data-stu-id="562c0-116">Use [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md) instead.</span></span>  
  
 <span data-ttu-id="562c0-117">Die `WriteMemory` Methode sollte nur außerhalb von verwaltetem Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="562c0-117">The `WriteMemory` method should be used only outside of managed code.</span></span> <span data-ttu-id="562c0-118">Diese Methode kann die Laufzeit beschädigt werden, wenn nicht ordnungsgemäß verwendet.</span><span class="sxs-lookup"><span data-stu-id="562c0-118">This method can corrupt the runtime if used improperly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="562c0-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="562c0-119">Requirements</span></span>  
 <span data-ttu-id="562c0-120">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="562c0-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="562c0-121">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="562c0-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="562c0-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="562c0-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="562c0-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="562c0-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
