---
title: ICorDebugProcess::WriteMemory-Methode
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2a1a12d1393d1db69ea47833958fdf828b552064
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocesswritememory-method"></a><span data-ttu-id="9afa5-102">ICorDebugProcess::WriteMemory-Methode</span><span class="sxs-lookup"><span data-stu-id="9afa5-102">ICorDebugProcess::WriteMemory Method</span></span>
<span data-ttu-id="9afa5-103">Schreibt Daten in einem Bereich des Arbeitsspeichers in diesem Prozess.</span><span class="sxs-lookup"><span data-stu-id="9afa5-103">Writes data to an area of memory in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9afa5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9afa5-104">Syntax</span></span>  
  
```  
HRESULT WriteMemory(  
    [in]  CORDB_ADDRESS address,  
    [in]  DWORD size,  
    [in, size_is(size)] BYTE buffer[],  
    [out] SIZE_T *written);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9afa5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9afa5-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="9afa5-106">[in] Ein `CORDB_ADDRESS` -Wert, der die Basisadresse des Speicherbereichs, welche Daten geschrieben.</span><span class="sxs-lookup"><span data-stu-id="9afa5-106">[in] A `CORDB_ADDRESS` value that is the base address of the memory area to which data is written.</span></span> <span data-ttu-id="9afa5-107">Bevor die Datenübertragung erfolgt, das System überprüft, ob der Speicherbereich, der angegebenen Größe, beginnend an der Basisadresse zum Schreiben zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="9afa5-107">Before data transfer occurs, the system verifies that the memory area of the specified size, beginning at the base address, is accessible for writing.</span></span> <span data-ttu-id="9afa5-108">Wenn es nicht möglich ist, schlägt die Methode fehl.</span><span class="sxs-lookup"><span data-stu-id="9afa5-108">If it is not accessible, the method fails.</span></span>  
  
 `size`  
 <span data-ttu-id="9afa5-109">[in] Die Anzahl der Bytes in den Speicherbereich geschrieben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9afa5-109">[in] The number of bytes to be written to the memory area.</span></span>  
  
 `buffer`  
 <span data-ttu-id="9afa5-110">[in] Ein Puffer, der zu schreibenden Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="9afa5-110">[in] A buffer that contains data to be written.</span></span>  
  
 `written`  
 <span data-ttu-id="9afa5-111">[out] Ein Zeiger auf eine Variable, die Anzahl der Bytes, die in den Speicherbereich in diesem Prozess geschrieben empfängt.</span><span class="sxs-lookup"><span data-stu-id="9afa5-111">[out] A pointer to a variable that receives the number of bytes written to the memory area in this process.</span></span> <span data-ttu-id="9afa5-112">Wenn `written` NULL ist, wird dieser Parameter ignoriert.</span><span class="sxs-lookup"><span data-stu-id="9afa5-112">If `written` is NULL, this parameter is ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9afa5-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9afa5-113">Remarks</span></span>  
 <span data-ttu-id="9afa5-114">Daten werden automatisch hinter die Haltepunkte geschrieben.</span><span class="sxs-lookup"><span data-stu-id="9afa5-114">Data is automatically written behind any breakpoints.</span></span> <span data-ttu-id="9afa5-115">In .NET Framework, Version 2.0 verwenden nativen Debugger nicht diese Methode zum Einfügen von Haltepunkten in den Anweisungsstream.</span><span class="sxs-lookup"><span data-stu-id="9afa5-115">In the .NET Framework version 2.0, native debuggers should not use this method to inject breakpoints into the instruction stream.</span></span> <span data-ttu-id="9afa5-116">Verwendung [ICorDebugProcess2:: SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md) stattdessen.</span><span class="sxs-lookup"><span data-stu-id="9afa5-116">Use [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md) instead.</span></span>  
  
 <span data-ttu-id="9afa5-117">Die `WriteMemory` Methode sollte nur außerhalb von verwaltetem Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9afa5-117">The `WriteMemory` method should be used only outside of managed code.</span></span> <span data-ttu-id="9afa5-118">Diese Methode kann die Common Language Runtime beschädigt werden, wenn Sie nicht ordnungsgemäß verwendet.</span><span class="sxs-lookup"><span data-stu-id="9afa5-118">This method can corrupt the runtime if used improperly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9afa5-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9afa5-119">Requirements</span></span>  
 <span data-ttu-id="9afa5-120">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9afa5-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9afa5-121">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9afa5-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9afa5-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9afa5-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9afa5-123">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9afa5-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
