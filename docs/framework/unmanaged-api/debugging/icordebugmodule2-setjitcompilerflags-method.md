---
title: ICorDebugModule2::SetJITCompilerFlags-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.SetJITCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::SetJITCompilerFlags
helpviewer_keywords:
- ICorDebugModule2::SetJITCompilerFlags method [.NET Framework debugging]
- SetJITCompilerFlags method [.NET Framework debugging]
ms.assetid: ea574c84-c622-4589-9a14-b55771af5e06
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c71ccbc62ea026a55a7e84f6925a78850594a813
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61942514"
---
# <a name="icordebugmodule2setjitcompilerflags-method"></a><span data-ttu-id="6a875-102">ICorDebugModule2::SetJITCompilerFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="6a875-102">ICorDebugModule2::SetJITCompilerFlags Method</span></span>
<span data-ttu-id="6a875-103">Legt die Flags, die just-in-Time (JIT)-Kompilierung für dieses ICorDebugModule2 steuern.</span><span class="sxs-lookup"><span data-stu-id="6a875-103">Sets the flags that control the just-in-time (JIT) compilation of this ICorDebugModule2.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a875-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6a875-104">Syntax</span></span>  
  
```  
HRESULT SetJITCompilerFlags (  
    [in] DWORD dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6a875-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6a875-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="6a875-106">[in] Eine bitweise Kombination der [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) -Enumerationswerte fest.</span><span class="sxs-lookup"><span data-stu-id="6a875-106">[in] A bitwise combination of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6a875-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6a875-107">Remarks</span></span>  
 <span data-ttu-id="6a875-108">Wenn die `dwFlags` Wert ist ungültig, die `SetJITCompilerFlags` Methode fehl.</span><span class="sxs-lookup"><span data-stu-id="6a875-108">If the `dwFlags` value is invalid, the `SetJITCompilerFlags` method will fail.</span></span>  
  
 <span data-ttu-id="6a875-109">Die `SetJITCompilerFlags` Methode kann aufgerufen werden, nur von innerhalb der [ICorDebugManagedCallback:: LoadModule](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md) Rückruf für dieses Modul.</span><span class="sxs-lookup"><span data-stu-id="6a875-109">The `SetJITCompilerFlags` method can be called only from within the [ICorDebugManagedCallback::LoadModule](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md) callback for this module.</span></span> <span data-ttu-id="6a875-110">Versucht, sie aufzurufen, nachdem die `ICorDebugManagedCallback::LoadModule` Rückruf übermittelt wurde, fehl.</span><span class="sxs-lookup"><span data-stu-id="6a875-110">Attempts to call it after the `ICorDebugManagedCallback::LoadModule` callback has been delivered will fail.</span></span>  
  
 <span data-ttu-id="6a875-111">Bearbeiten und Fortfahren wird auf 64-Bit- oder Win9x-Plattformen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6a875-111">Edit and Continue is not supported on 64-bit or Win9x platforms.</span></span> <span data-ttu-id="6a875-112">Aus diesem Grund Aufrufen der `SetJITCompilerFlags` Methode entweder mit dem CORDEBUG_JIT_ENABLE_ENC-Flag festlegen, die dieser beiden Plattformen `dwFlags`, `SetJITCompilerFlags` -Methode und alle spezifischen Methoden zu bearbeiten und fortfahren, wie z. B. [ICorDebugModule2:: ApplyChanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md), schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="6a875-112">Therefore, if you call the `SetJITCompilerFlags` method on either of these two platforms with the CORDEBUG_JIT_ENABLE_ENC flag set in `dwFlags`, the `SetJITCompilerFlags` method and all methods specific to Edit and Continue, such as [ICorDebugModule2::ApplyChanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md), will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a875-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6a875-113">Requirements</span></span>  
 <span data-ttu-id="6a875-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6a875-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a875-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6a875-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6a875-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6a875-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6a875-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a875-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
