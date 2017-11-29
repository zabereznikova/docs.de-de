---
title: ICorDebugProcess2::SetDesiredNGENCompilerFlags-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess2.SetDesiredNGENCompilerFlags
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess2::SetDesiredNGENCompilerFlags
helpviewer_keywords:
- ICorDebugProcess2::SetDesiredNGENCompilerFlags method [.NET Framework debugging]
- SetDesiredNGENCompilerFlags method [.NET Framework debugging]
ms.assetid: 98320175-7c5e-4dbb-8683-86fa82e2641f
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 278f1f79fd929aa8a0c3233e68b30b1154e913ef
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess2setdesiredngencompilerflags-method"></a><span data-ttu-id="fd1c8-102">ICorDebugProcess2::SetDesiredNGENCompilerFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="fd1c8-102">ICorDebugProcess2::SetDesiredNGENCompilerFlags Method</span></span>
<span data-ttu-id="fd1c8-103">Legt die Flags, die in einem vorkompilierten Abbild in der Reihenfolge für die Laufzeit das Abbild in den aktuellen Prozess lädt eingebettet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="fd1c8-103">Sets the flags that must be embedded in a precompiled image in order for the runtime to load that image into the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd1c8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fd1c8-104">Syntax</span></span>  
  
```  
HRESULT SetDesiredNGENCompilerFlags (  
    [in] DWORD    pdwFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fd1c8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fd1c8-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="fd1c8-106">[in] Der Wert der [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) Enumeration, der angibt, die Compilerflags verwendet wird, um das richtige Bild für die vorkompilierte auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="fd1c8-106">[in] A value of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration that specifies the compiler flags used to select the correct pre-compiled image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fd1c8-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fd1c8-107">Remarks</span></span>  
 <span data-ttu-id="fd1c8-108">Die `SetDesiredNGENCompilerFlags` -Methode gibt die Flags, die in einem vorkompilierten Abbild eingebettet sein müssen, damit die Laufzeit das Abbild in diesem Prozess geladen werden.</span><span class="sxs-lookup"><span data-stu-id="fd1c8-108">The `SetDesiredNGENCompilerFlags` method specifies the flags that must be embedded in a precompiled image so that the runtime will load that image into this process.</span></span> <span data-ttu-id="fd1c8-109">Die Flags, die von dieser Methode festgelegte dienen nur, um das richtige vorkompilierte Abbild auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="fd1c8-109">The flags set by this method are used only to select the correct precompiled image.</span></span> <span data-ttu-id="fd1c8-110">Wenn kein solches Image vorhanden ist, wird die Common Language Runtime die Microsoft intermediate Language (MSIL)-Image und der Just-in-Time (JIT)-Compiler stattdessen geladen.</span><span class="sxs-lookup"><span data-stu-id="fd1c8-110">If no such image exists, the runtime will load the Microsoft intermediate language (MSIL) image and the just-in-time (JIT) compiler instead.</span></span> <span data-ttu-id="fd1c8-111">In diesem Fall muss der Debugger weiterhin verwenden die [ICorDebugModule2:: SetJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md) Methode, um die Flags für die JIT-Kompilierung wie gewünscht festgelegt.</span><span class="sxs-lookup"><span data-stu-id="fd1c8-111">In that case, the debugger must still use the [ICorDebugModule2::SetJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md) method to set the flags as desired for the JIT compilation.</span></span>  
  
 <span data-ttu-id="fd1c8-112">Wenn ein Image geladen wird, aber einige JIT-Kompilierung für erfolgen muss sich das Bild (das der Fall sein wird, wenn das Bild Generika enthält), die vom angegebenen Compilerflags die `SetDesiredNGENCompilerFlags` Methode gilt für die zusätzliche JIT-Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="fd1c8-112">If an image is loaded, but some JIT compiling must take place for that image (which will be the case if the image contains generics), the compiler flags specified by the `SetDesiredNGENCompilerFlags` method will apply to the extra JIT compilation.</span></span>  
  
 <span data-ttu-id="fd1c8-113">Die `SetDesiredNGENCompilerFlags` -Methode muss aufgerufen werden, während die [ICorDebugManagedCallback:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="fd1c8-113">The `SetDesiredNGENCompilerFlags` method must be called during the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback.</span></span> <span data-ttu-id="fd1c8-114">Versucht, rufen Sie die `SetDesiredNGENCompilerFlags` Methode danach schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="fd1c8-114">Attempts to call the `SetDesiredNGENCompilerFlags` method afterwards will fail.</span></span> <span data-ttu-id="fd1c8-115">Darüber hinaus versuchen, Flags festzulegen, die entweder nicht definiert, der `CorDebugJITCompilerFlags` fehl, Enumeration oder sind nicht zulässig für den angegebenen Prozess.</span><span class="sxs-lookup"><span data-stu-id="fd1c8-115">Also, attempts to set flags that are either not defined in the `CorDebugJITCompilerFlags` enumeration or are not legal for the given process will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd1c8-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fd1c8-116">Requirements</span></span>  
 <span data-ttu-id="fd1c8-117">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd1c8-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd1c8-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fd1c8-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fd1c8-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fd1c8-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fd1c8-120">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd1c8-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd1c8-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fd1c8-121">See Also</span></span>  
 [<span data-ttu-id="fd1c8-122">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fd1c8-122">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
 [<span data-ttu-id="fd1c8-123">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fd1c8-123">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
