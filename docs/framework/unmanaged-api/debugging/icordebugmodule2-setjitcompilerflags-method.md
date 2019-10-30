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
ms.openlocfilehash: 2358cee1b3a9aa50fb1f0e61d558f164a39aa86c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137364"
---
# <a name="icordebugmodule2setjitcompilerflags-method"></a><span data-ttu-id="e03fa-102">ICorDebugModule2::SetJITCompilerFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="e03fa-102">ICorDebugModule2::SetJITCompilerFlags Method</span></span>
<span data-ttu-id="e03fa-103">Legt die Flags fest, die die Just-in-time (JIT)-Kompilierung dieses ICorDebugModule2 steuern.</span><span class="sxs-lookup"><span data-stu-id="e03fa-103">Sets the flags that control the just-in-time (JIT) compilation of this ICorDebugModule2.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e03fa-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e03fa-104">Syntax</span></span>  
  
```cpp  
HRESULT SetJITCompilerFlags (  
    [in] DWORD dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e03fa-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e03fa-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="e03fa-106">in Eine bitweise Kombination der [cordbugjitcompilerflags-Enumerationswerte](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="e03fa-106">[in] A bitwise combination of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e03fa-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e03fa-107">Remarks</span></span>  
 <span data-ttu-id="e03fa-108">Wenn der `dwFlags` Wert ungültig ist, tritt bei der `SetJITCompilerFlags` Methode ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="e03fa-108">If the `dwFlags` value is invalid, the `SetJITCompilerFlags` method will fail.</span></span>  
  
 <span data-ttu-id="e03fa-109">Die `SetJITCompilerFlags`-Methode kann nur innerhalb des [ICorDebugManagedCallback:: LoadModule](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md) -Rückrufs für dieses Modul aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="e03fa-109">The `SetJITCompilerFlags` method can be called only from within the [ICorDebugManagedCallback::LoadModule](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md) callback for this module.</span></span> <span data-ttu-id="e03fa-110">Wenn versucht wird, Sie nach dem Übermitteln des `ICorDebugManagedCallback::LoadModule` Rückrufs aufzurufen, schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="e03fa-110">Attempts to call it after the `ICorDebugManagedCallback::LoadModule` callback has been delivered will fail.</span></span>  
  
 <span data-ttu-id="e03fa-111">"Bearbeiten und Fortfahren" wird auf den Plattformen 64-Bit oder Win9x nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e03fa-111">Edit and Continue is not supported on 64-bit or Win9x platforms.</span></span> <span data-ttu-id="e03fa-112">Wenn Sie die `SetJITCompilerFlags`-Methode auf einer dieser beiden Plattformen mit dem in `dwFlags`festgelegten CORDEBUG_JIT_ENABLE_ENC-Flag aufzurufen, schlagen die `SetJITCompilerFlags`-Methode und alle Methoden, die für "Bearbeiten und Fortfahren" spezifisch sind, z. b. " [ICorDebugModule2:: ApplyChanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md)", fehl.</span><span class="sxs-lookup"><span data-stu-id="e03fa-112">Therefore, if you call the `SetJITCompilerFlags` method on either of these two platforms with the CORDEBUG_JIT_ENABLE_ENC flag set in `dwFlags`, the `SetJITCompilerFlags` method and all methods specific to Edit and Continue, such as [ICorDebugModule2::ApplyChanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md), will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e03fa-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e03fa-113">Requirements</span></span>  
 <span data-ttu-id="e03fa-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e03fa-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e03fa-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e03fa-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e03fa-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e03fa-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e03fa-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e03fa-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
