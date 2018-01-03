---
title: ICorDebugModule2::SetJITCompilerFlags-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule2.SetJITCompilerFlags
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule2::SetJITCompilerFlags
helpviewer_keywords:
- ICorDebugModule2::SetJITCompilerFlags method [.NET Framework debugging]
- SetJITCompilerFlags method [.NET Framework debugging]
ms.assetid: ea574c84-c622-4589-9a14-b55771af5e06
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cfc25e9ce15996360cd0e3c68805d3707b325f79
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmodule2setjitcompilerflags-method"></a><span data-ttu-id="4c3bd-102">ICorDebugModule2::SetJITCompilerFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="4c3bd-102">ICorDebugModule2::SetJITCompilerFlags Method</span></span>
<span data-ttu-id="4c3bd-103">Legt die Flags, die die Just-in-Time (JIT)-Kompilierung für diese ICorDebugModule2 steuern.</span><span class="sxs-lookup"><span data-stu-id="4c3bd-103">Sets the flags that control the just-in-time (JIT) compilation of this ICorDebugModule2.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c3bd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4c3bd-104">Syntax</span></span>  
  
```  
HRESULT SetJITCompilerFlags (  
    [in] DWORD dwFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4c3bd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4c3bd-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="4c3bd-106">[in] Eine bitweise Kombination der [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) Enumerationswerte.</span><span class="sxs-lookup"><span data-stu-id="4c3bd-106">[in] A bitwise combination of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4c3bd-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4c3bd-107">Remarks</span></span>  
 <span data-ttu-id="4c3bd-108">Wenn die `dwFlags` Wert ist ungültig, die `SetJITCompilerFlags` Methode fehl.</span><span class="sxs-lookup"><span data-stu-id="4c3bd-108">If the `dwFlags` value is invalid, the `SetJITCompilerFlags` method will fail.</span></span>  
  
 <span data-ttu-id="4c3bd-109">Die `SetJITCompilerFlags` Methode kann aufgerufen werden, nur von innerhalb der [ICorDebugManagedCallback:: LoadModule](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md) Rückruf für dieses Modul.</span><span class="sxs-lookup"><span data-stu-id="4c3bd-109">The `SetJITCompilerFlags` method can be called only from within the [ICorDebugManagedCallback::LoadModule](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md) callback for this module.</span></span> <span data-ttu-id="4c3bd-110">Versucht, die sie nach dem Aufrufen der `ICorDebugManagedCallback::LoadModule` Rückruf übermittelt wurde, schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="4c3bd-110">Attempts to call it after the `ICorDebugManagedCallback::LoadModule` callback has been delivered will fail.</span></span>  
  
 <span data-ttu-id="4c3bd-111">Bearbeiten und Fortfahren wird auf 64-Bit- oder Win9x-Plattformen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4c3bd-111">Edit and Continue is not supported on 64-bit or Win9x platforms.</span></span> <span data-ttu-id="4c3bd-112">Aus diesem Grund beim Aufrufen der `SetJITCompilerFlags` -Methode auf einer dieser beiden Plattformen mit dem CORDEBUG_JIT_ENABLE_ENC-Flag festgelegt `dwFlags`, die `SetJITCompilerFlags` -Methode und alle spezifischen Methoden zum Bearbeiten und fortfahren, z. B. [ICorDebugModule2:: ApplyChanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md), schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="4c3bd-112">Therefore, if you call the `SetJITCompilerFlags` method on either of these two platforms with the CORDEBUG_JIT_ENABLE_ENC flag set in `dwFlags`, the `SetJITCompilerFlags` method and all methods specific to Edit and Continue, such as [ICorDebugModule2::ApplyChanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md), will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c3bd-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4c3bd-113">Requirements</span></span>  
 <span data-ttu-id="4c3bd-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4c3bd-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c3bd-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4c3bd-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4c3bd-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4c3bd-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4c3bd-117">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c3bd-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
