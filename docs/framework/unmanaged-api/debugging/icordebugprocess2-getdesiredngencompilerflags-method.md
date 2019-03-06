---
title: ICorDebugProcess2::GetDesiredNGENCompilerFlags-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetDesiredNGENCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetDesiredNGENCompilerFlags
helpviewer_keywords:
- ICorDebugProcess2::GetDesiredNGENCompilerFlags method [.NET Framework debugging]
- GetDesiredNGENCompilerFlags method [.NET Framework debugging]
ms.assetid: fc834580-3a90-4315-95d2-349b6bb7d059
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a59067f72005e87152680e4f990fc74e4acdaa9b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57472667"
---
# <a name="icordebugprocess2getdesiredngencompilerflags-method"></a><span data-ttu-id="dca98-102">ICorDebugProcess2::GetDesiredNGENCompilerFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="dca98-102">ICorDebugProcess2::GetDesiredNGENCompilerFlags Method</span></span>
<span data-ttu-id="dca98-103">Ruft den aktuellen Compiler Einstellungen, die die common Language Runtime (CLR) verwendet, um den richtigen vorkompilierte auszuwählen (d.h. native) Image in dieser Prozess geladen werden.</span><span class="sxs-lookup"><span data-stu-id="dca98-103">Gets the current compiler flag settings that the common language runtime (CLR) uses to select the correct precompiled (that is, native) image to be loaded into this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dca98-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dca98-104">Syntax</span></span>  
  
```  
HRESULT GetDesiredNGENCompilerFlags (  
    [out] DWORD   *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dca98-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="dca98-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="dca98-106">[out] Ein Zeiger auf eine bitweise Kombination der [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) Enumerationswerte, die verwendet werden, wählen Sie das richtige vorkompilierte Abbild geladen werden.</span><span class="sxs-lookup"><span data-stu-id="dca98-106">[out] A pointer to a bitwise combination of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration values that are used to select the correct precompiled image to be loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dca98-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dca98-107">Remarks</span></span>  
 <span data-ttu-id="dca98-108">Verwenden Sie die [ICorDebugProcess2:: SetDesiredNGENCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setdesiredngencompilerflags-method.md) Methode, um die Flags festlegen, die die CLR verwendet, um das Auswählen des richtigen vorkompilierte Abbilds laden.</span><span class="sxs-lookup"><span data-stu-id="dca98-108">Use the [ICorDebugProcess2::SetDesiredNGENCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setdesiredngencompilerflags-method.md) method to set the flags that the CLR will use to select the correct pre-compiled image to load.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dca98-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dca98-109">Requirements</span></span>  
 <span data-ttu-id="dca98-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dca98-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dca98-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dca98-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dca98-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dca98-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dca98-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dca98-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
