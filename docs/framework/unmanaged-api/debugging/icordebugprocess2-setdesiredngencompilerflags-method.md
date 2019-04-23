---
title: ICorDebugProcess2::SetDesiredNGENCompilerFlags-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.SetDesiredNGENCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::SetDesiredNGENCompilerFlags
helpviewer_keywords:
- ICorDebugProcess2::SetDesiredNGENCompilerFlags method [.NET Framework debugging]
- SetDesiredNGENCompilerFlags method [.NET Framework debugging]
ms.assetid: 98320175-7c5e-4dbb-8683-86fa82e2641f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e061c3f3dc95e63339d6fd5f82b3cb4d38a4b6c6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59206706"
---
# <a name="icordebugprocess2setdesiredngencompilerflags-method"></a><span data-ttu-id="111d5-102">ICorDebugProcess2::SetDesiredNGENCompilerFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="111d5-102">ICorDebugProcess2::SetDesiredNGENCompilerFlags Method</span></span>
<span data-ttu-id="111d5-103">Legt die Flags, die in einem vorkompilierten Abbild in der Reihenfolge für die Laufzeit beim Laden von Images in den aktuellen Prozess eingebettet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="111d5-103">Sets the flags that must be embedded in a precompiled image in order for the runtime to load that image into the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="111d5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="111d5-104">Syntax</span></span>  
  
```  
HRESULT SetDesiredNGENCompilerFlags (  
    [in] DWORD    pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="111d5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="111d5-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="111d5-106">[in] Der Wert der [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) Enumeration, der angibt, die Compilerflags verwendet, um das richtige vorkompilierte Abbild auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="111d5-106">[in] A value of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration that specifies the compiler flags used to select the correct pre-compiled image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="111d5-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="111d5-107">Remarks</span></span>  
 <span data-ttu-id="111d5-108">Die `SetDesiredNGENCompilerFlags` -Methode gibt die Flags, die in einem vorkompilierten Abbild eingebettet werden müssen, damit die Laufzeit dieses Abbild in diesen Prozess geladen werden.</span><span class="sxs-lookup"><span data-stu-id="111d5-108">The `SetDesiredNGENCompilerFlags` method specifies the flags that must be embedded in a precompiled image so that the runtime will load that image into this process.</span></span> <span data-ttu-id="111d5-109">Die Flags, die von dieser Methode festgelegte werden verwendet, nur für die richtige vorkompilierte Abbild auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="111d5-109">The flags set by this method are used only to select the correct precompiled image.</span></span> <span data-ttu-id="111d5-110">Wenn kein solches Image vorhanden ist, wird die Laufzeit die Microsoft intermediate Language (MSIL)-Image und der just-in-Time-Compiler (JIT) stattdessen geladen werden.</span><span class="sxs-lookup"><span data-stu-id="111d5-110">If no such image exists, the runtime will load the Microsoft intermediate language (MSIL) image and the just-in-time (JIT) compiler instead.</span></span> <span data-ttu-id="111d5-111">In diesem Fall muss der Debugger weiterhin verwenden die [ICorDebugModule2:: SetJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md) Methode, um die Flags für die JIT-Kompilierung wie gewünscht festgelegt.</span><span class="sxs-lookup"><span data-stu-id="111d5-111">In that case, the debugger must still use the [ICorDebugModule2::SetJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md) method to set the flags as desired for the JIT compilation.</span></span>  
  
 <span data-ttu-id="111d5-112">Wenn ein Image geladen wird, aber einige JIT-Kompilierung erfolgen muss für das Bild (das der Fall sein wird, wenn das Bild Generika enthält), die vom angegebenen Compilerflags der `SetDesiredNGENCompilerFlags` Methode gilt für die zusätzliche JIT-Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="111d5-112">If an image is loaded, but some JIT compiling must take place for that image (which will be the case if the image contains generics), the compiler flags specified by the `SetDesiredNGENCompilerFlags` method will apply to the extra JIT compilation.</span></span>  
  
 <span data-ttu-id="111d5-113">Die `SetDesiredNGENCompilerFlags` -Methode muss aufgerufen werden, während die [ICorDebugManagedCallback:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="111d5-113">The `SetDesiredNGENCompilerFlags` method must be called during the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback.</span></span> <span data-ttu-id="111d5-114">Versucht, rufen Sie die `SetDesiredNGENCompilerFlags` Methode danach schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="111d5-114">Attempts to call the `SetDesiredNGENCompilerFlags` method afterwards will fail.</span></span> <span data-ttu-id="111d5-115">Darüber hinaus versuchen, Flags festzulegen, die entweder nicht definiert, der `CorDebugJITCompilerFlags` Enumeration sind nicht zulässig, für den Prozess ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="111d5-115">Also, attempts to set flags that are either not defined in the `CorDebugJITCompilerFlags` enumeration or are not legal for the given process will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="111d5-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="111d5-116">Requirements</span></span>  
 <span data-ttu-id="111d5-117">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="111d5-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="111d5-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="111d5-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="111d5-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="111d5-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="111d5-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="111d5-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="111d5-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="111d5-121">See also</span></span>

- [<span data-ttu-id="111d5-122">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="111d5-122">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [<span data-ttu-id="111d5-123">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="111d5-123">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
