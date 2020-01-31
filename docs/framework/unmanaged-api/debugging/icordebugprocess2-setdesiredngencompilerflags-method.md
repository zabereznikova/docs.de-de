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
ms.openlocfilehash: 9f62d94d30c8c4f23073895b8ff0f7afa2dbad6b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792496"
---
# <a name="icordebugprocess2setdesiredngencompilerflags-method"></a><span data-ttu-id="8e65f-102">ICorDebugProcess2::SetDesiredNGENCompilerFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="8e65f-102">ICorDebugProcess2::SetDesiredNGENCompilerFlags Method</span></span>
<span data-ttu-id="8e65f-103">Legt die Flags fest, die in ein vorkompiliertes Bild eingebettet werden müssen, damit die Common Language Runtime dieses Bild in den aktuellen Prozess lädt.</span><span class="sxs-lookup"><span data-stu-id="8e65f-103">Sets the flags that must be embedded in a precompiled image in order for the runtime to load that image into the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e65f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8e65f-104">Syntax</span></span>  
  
```cpp  
HRESULT SetDesiredNGENCompilerFlags (  
    [in] DWORD    pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8e65f-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="8e65f-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="8e65f-106">in Ein Wert der [corentbugjitcompilerflags](cordebugjitcompilerflags-enumeration.md) -Enumeration, der die Compilerflags angibt, die zum Auswählen des richtigen vorkompilierten Bilds verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8e65f-106">[in] A value of the [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) enumeration that specifies the compiler flags used to select the correct pre-compiled image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8e65f-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8e65f-107">Remarks</span></span>  
 <span data-ttu-id="8e65f-108">Die `SetDesiredNGENCompilerFlags`-Methode gibt die Flags an, die in ein vorkompiliertes Bild eingebettet werden müssen, damit die Laufzeit dieses Bild in diesen Prozess lädt.</span><span class="sxs-lookup"><span data-stu-id="8e65f-108">The `SetDesiredNGENCompilerFlags` method specifies the flags that must be embedded in a precompiled image so that the runtime will load that image into this process.</span></span> <span data-ttu-id="8e65f-109">Die von dieser Methode festgelegten Flags werden nur zur Auswahl des richtigen vorkompilierten Bilds verwendet.</span><span class="sxs-lookup"><span data-stu-id="8e65f-109">The flags set by this method are used only to select the correct precompiled image.</span></span> <span data-ttu-id="8e65f-110">Wenn kein solches Image vorhanden ist, lädt die Runtime stattdessen das MSIL-Image (Microsoft Intermediate Language) und den JIT-Compiler (Just-in-Time).</span><span class="sxs-lookup"><span data-stu-id="8e65f-110">If no such image exists, the runtime will load the Microsoft intermediate language (MSIL) image and the just-in-time (JIT) compiler instead.</span></span> <span data-ttu-id="8e65f-111">In diesem Fall muss der Debugger weiterhin die [ICorDebugModule2:: SetJITCompilerFlags](icordebugmodule2-setjitcompilerflags-method.md) -Methode verwenden, um die Flags für die JIT-Kompilierung wie gewünscht festzulegen.</span><span class="sxs-lookup"><span data-stu-id="8e65f-111">In that case, the debugger must still use the [ICorDebugModule2::SetJITCompilerFlags](icordebugmodule2-setjitcompilerflags-method.md) method to set the flags as desired for the JIT compilation.</span></span>  
  
 <span data-ttu-id="8e65f-112">Wenn ein Bild geladen wird, aber einige JIT-Kompilierungen für dieses Bild stattfinden müssen (Dies ist der Fall, wenn das Image Generika enthält), gelten die von der `SetDesiredNGENCompilerFlags`-Methode angegebenen Compilerflags für die zusätzliche JIT-Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="8e65f-112">If an image is loaded, but some JIT compiling must take place for that image (which will be the case if the image contains generics), the compiler flags specified by the `SetDesiredNGENCompilerFlags` method will apply to the extra JIT compilation.</span></span>  
  
 <span data-ttu-id="8e65f-113">Die `SetDesiredNGENCompilerFlags`-Methode muss während des [ICorDebugManagedCallback::](icordebugmanagedcallback-createprocess-method.md) -Rückruf aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="8e65f-113">The `SetDesiredNGENCompilerFlags` method must be called during the [ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md) callback.</span></span> <span data-ttu-id="8e65f-114">Versuche, die `SetDesiredNGENCompilerFlags`-Methode später aufzurufen, schlagen fehl.</span><span class="sxs-lookup"><span data-stu-id="8e65f-114">Attempts to call the `SetDesiredNGENCompilerFlags` method afterwards will fail.</span></span> <span data-ttu-id="8e65f-115">Außerdem schlagen Versuche, Flags festzulegen, die entweder nicht in der `CorDebugJITCompilerFlags` Enumeration definiert sind oder für den angegebenen Prozess nicht zulässig sind, fehl.</span><span class="sxs-lookup"><span data-stu-id="8e65f-115">Also, attempts to set flags that are either not defined in the `CorDebugJITCompilerFlags` enumeration or are not legal for the given process will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e65f-116">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8e65f-116">Requirements</span></span>  
 <span data-ttu-id="8e65f-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8e65f-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e65f-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8e65f-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8e65f-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8e65f-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8e65f-120">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e65f-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e65f-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8e65f-121">See also</span></span>

- [<span data-ttu-id="8e65f-122">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8e65f-122">ICorDebug Interface</span></span>](icordebug-interface.md)
- [<span data-ttu-id="8e65f-123">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8e65f-123">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
