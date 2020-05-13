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
ms.openlocfilehash: 366a48e5f6abd92f0c6f796f40bdd263181da4a8
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213477"
---
# <a name="icordebugprocess2setdesiredngencompilerflags-method"></a><span data-ttu-id="41a65-102">ICorDebugProcess2::SetDesiredNGENCompilerFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="41a65-102">ICorDebugProcess2::SetDesiredNGENCompilerFlags Method</span></span>
<span data-ttu-id="41a65-103">Legt die Flags fest, die in ein vorkompiliertes Bild eingebettet werden müssen, damit die Common Language Runtime dieses Bild in den aktuellen Prozess lädt.</span><span class="sxs-lookup"><span data-stu-id="41a65-103">Sets the flags that must be embedded in a precompiled image in order for the runtime to load that image into the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41a65-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="41a65-104">Syntax</span></span>  
  
```cpp  
HRESULT SetDesiredNGENCompilerFlags (  
    [in] DWORD    pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="41a65-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="41a65-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="41a65-106">in Ein Wert der [corentbugjitcompilerflags](cordebugjitcompilerflags-enumeration.md) -Enumeration, der die Compilerflags angibt, die zum Auswählen des richtigen vorkompilierten Bilds verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="41a65-106">[in] A value of the [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) enumeration that specifies the compiler flags used to select the correct pre-compiled image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="41a65-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="41a65-107">Remarks</span></span>  
 <span data-ttu-id="41a65-108">Die- `SetDesiredNGENCompilerFlags` Methode gibt die Flags an, die in ein vorkompiliertes Bild eingebettet werden müssen, damit die Laufzeit dieses Bild in diesen Prozess lädt.</span><span class="sxs-lookup"><span data-stu-id="41a65-108">The `SetDesiredNGENCompilerFlags` method specifies the flags that must be embedded in a precompiled image so that the runtime will load that image into this process.</span></span> <span data-ttu-id="41a65-109">Die von dieser Methode festgelegten Flags werden nur zur Auswahl des richtigen vorkompilierten Bilds verwendet.</span><span class="sxs-lookup"><span data-stu-id="41a65-109">The flags set by this method are used only to select the correct precompiled image.</span></span> <span data-ttu-id="41a65-110">Wenn kein solches Image vorhanden ist, lädt die Runtime stattdessen das MSIL-Image (Microsoft Intermediate Language) und den JIT-Compiler (Just-in-Time).</span><span class="sxs-lookup"><span data-stu-id="41a65-110">If no such image exists, the runtime will load the Microsoft intermediate language (MSIL) image and the just-in-time (JIT) compiler instead.</span></span> <span data-ttu-id="41a65-111">In diesem Fall muss der Debugger weiterhin die [ICorDebugModule2:: SetJITCompilerFlags](icordebugmodule2-setjitcompilerflags-method.md) -Methode verwenden, um die Flags für die JIT-Kompilierung wie gewünscht festzulegen.</span><span class="sxs-lookup"><span data-stu-id="41a65-111">In that case, the debugger must still use the [ICorDebugModule2::SetJITCompilerFlags](icordebugmodule2-setjitcompilerflags-method.md) method to set the flags as desired for the JIT compilation.</span></span>  
  
 <span data-ttu-id="41a65-112">Wenn ein Bild geladen wird, aber einige JIT-Kompilierungen für dieses Bild stattfinden müssen (Dies ist der Fall, wenn das Image Generika enthält), gelten die von der-Methode angegebenen Compilerflags für `SetDesiredNGENCompilerFlags` die zusätzliche JIT-Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="41a65-112">If an image is loaded, but some JIT compiling must take place for that image (which will be the case if the image contains generics), the compiler flags specified by the `SetDesiredNGENCompilerFlags` method will apply to the extra JIT compilation.</span></span>  
  
 <span data-ttu-id="41a65-113">Die- `SetDesiredNGENCompilerFlags` Methode muss während des Rückrufs von [ICorDebugManagedCallback:: deateprocess](icordebugmanagedcallback-createprocess-method.md) aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="41a65-113">The `SetDesiredNGENCompilerFlags` method must be called during the [ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md) callback.</span></span> <span data-ttu-id="41a65-114">Versuche, die Methode anschließend aufzurufen, können `SetDesiredNGENCompilerFlags` nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="41a65-114">Attempts to call the `SetDesiredNGENCompilerFlags` method afterwards will fail.</span></span> <span data-ttu-id="41a65-115">Außerdem schlagen Versuche, Flags festzulegen, die entweder nicht in der- `CorDebugJITCompilerFlags` Enumeration definiert sind oder für den angegebenen Prozess nicht zulässig sind, fehl.</span><span class="sxs-lookup"><span data-stu-id="41a65-115">Also, attempts to set flags that are either not defined in the `CorDebugJITCompilerFlags` enumeration or are not legal for the given process will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41a65-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="41a65-116">Requirements</span></span>  
 <span data-ttu-id="41a65-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41a65-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41a65-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="41a65-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="41a65-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="41a65-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="41a65-120">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41a65-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41a65-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="41a65-121">See also</span></span>

- [<span data-ttu-id="41a65-122">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="41a65-122">ICorDebug Interface</span></span>](icordebug-interface.md)
- [<span data-ttu-id="41a65-123">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="41a65-123">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
