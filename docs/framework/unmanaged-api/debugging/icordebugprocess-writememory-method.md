---
title: ICorDebugProcess::WriteMemory-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess.WriteMemory
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess::WriteMemory
helpviewer_keywords:
- ICorDebugProcess::WriteMemory method [.NET Framework debugging]
- WriteMemory method [.NET Framework debugging]
ms.assetid: d5c07d86-045d-4391-893b-0bcd2959f90e
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 053c6bf5f451377308f4defbeb6eff9525c4332e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugprocesswritememory-method"></a><span data-ttu-id="40e08-102">ICorDebugProcess::WriteMemory-Methode</span><span class="sxs-lookup"><span data-stu-id="40e08-102">ICorDebugProcess::WriteMemory Method</span></span>
<span data-ttu-id="40e08-103">Schreibt Daten in einem Bereich des Arbeitsspeichers in diesem Prozess.</span><span class="sxs-lookup"><span data-stu-id="40e08-103">Writes data to an area of memory in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40e08-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="40e08-104">Syntax</span></span>  
  
```  
HRESULT WriteMemory(  
    [in]  CORDB_ADDRESS address,  
    [in]  DWORD size,  
    [in, size_is(size)] BYTE buffer[],  
    [out] SIZE_T *written);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="40e08-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="40e08-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="40e08-106">[in] Ein `CORDB_ADDRESS` -Wert, der die Basisadresse des Speicherbereichs, welche Daten geschrieben.</span><span class="sxs-lookup"><span data-stu-id="40e08-106">[in] A `CORDB_ADDRESS` value that is the base address of the memory area to which data is written.</span></span> <span data-ttu-id="40e08-107">Bevor die Datenübertragung erfolgt, das System überprüft, ob der Speicherbereich, der angegebenen Größe, beginnend an der Basisadresse zum Schreiben zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="40e08-107">Before data transfer occurs, the system verifies that the memory area of the specified size, beginning at the base address, is accessible for writing.</span></span> <span data-ttu-id="40e08-108">Wenn es nicht möglich ist, schlägt die Methode fehl.</span><span class="sxs-lookup"><span data-stu-id="40e08-108">If it is not accessible, the method fails.</span></span>  
  
 `size`  
 <span data-ttu-id="40e08-109">[in] Die Anzahl der Bytes in den Speicherbereich geschrieben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="40e08-109">[in] The number of bytes to be written to the memory area.</span></span>  
  
 `buffer`  
 <span data-ttu-id="40e08-110">[in] Ein Puffer, der zu schreibenden Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="40e08-110">[in] A buffer that contains data to be written.</span></span>  
  
 `written`  
 <span data-ttu-id="40e08-111">[out] Ein Zeiger auf eine Variable, die Anzahl der Bytes, die in den Speicherbereich in diesem Prozess geschrieben empfängt.</span><span class="sxs-lookup"><span data-stu-id="40e08-111">[out] A pointer to a variable that receives the number of bytes written to the memory area in this process.</span></span> <span data-ttu-id="40e08-112">Wenn `written` NULL ist, wird dieser Parameter ignoriert.</span><span class="sxs-lookup"><span data-stu-id="40e08-112">If `written` is NULL, this parameter is ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="40e08-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="40e08-113">Remarks</span></span>  
 <span data-ttu-id="40e08-114">Daten werden automatisch hinter die Haltepunkte geschrieben.</span><span class="sxs-lookup"><span data-stu-id="40e08-114">Data is automatically written behind any breakpoints.</span></span> <span data-ttu-id="40e08-115">In .NET Framework, Version 2.0 verwenden nativen Debugger nicht diese Methode zum Einfügen von Haltepunkten in den Anweisungsstream.</span><span class="sxs-lookup"><span data-stu-id="40e08-115">In the .NET Framework version 2.0, native debuggers should not use this method to inject breakpoints into the instruction stream.</span></span> <span data-ttu-id="40e08-116">Verwendung [ICorDebugProcess2:: SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md) stattdessen.</span><span class="sxs-lookup"><span data-stu-id="40e08-116">Use [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md) instead.</span></span>  
  
 <span data-ttu-id="40e08-117">Die `WriteMemory` Methode sollte nur außerhalb von verwaltetem Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="40e08-117">The `WriteMemory` method should be used only outside of managed code.</span></span> <span data-ttu-id="40e08-118">Diese Methode kann die Common Language Runtime beschädigt werden, wenn Sie nicht ordnungsgemäß verwendet.</span><span class="sxs-lookup"><span data-stu-id="40e08-118">This method can corrupt the runtime if used improperly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40e08-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="40e08-119">Requirements</span></span>  
 <span data-ttu-id="40e08-120">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40e08-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40e08-121">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="40e08-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="40e08-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="40e08-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="40e08-123">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40e08-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
