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
ms.openlocfilehash: 77ffb53e3a2b3802d3fcc1319397c8f51c5b127c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416110"
---
# <a name="icordebugprocess2getdesiredngencompilerflags-method"></a><span data-ttu-id="17d99-102">ICorDebugProcess2::GetDesiredNGENCompilerFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="17d99-102">ICorDebugProcess2::GetDesiredNGENCompilerFlags Method</span></span>
<span data-ttu-id="17d99-103">Ruft den aktuellen Compiler Flageinstellungen, die die common Language Runtime (CLR) verwendet, um den richtigen vorkompilierte auszuwählen (d. h. systemeigene) Image in diesen Prozess geladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="17d99-103">Gets the current compiler flag settings that the common language runtime (CLR) uses to select the correct precompiled (that is, native) image to be loaded into this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17d99-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="17d99-104">Syntax</span></span>  
  
```  
HRESULT GetDesiredNGENCompilerFlags (  
    [out] DWORD   *pdwFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="17d99-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="17d99-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="17d99-106">[out] Ein Zeiger auf eine bitweise Kombination der [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) Enumerationswerte, die verwendet werden, wählen Sie das richtige vorkompilierte Bild geladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="17d99-106">[out] A pointer to a bitwise combination of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration values that are used to select the correct precompiled image to be loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="17d99-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="17d99-107">Remarks</span></span>  
 <span data-ttu-id="17d99-108">Verwenden Sie die [ICorDebugProcess2:: SetDesiredNGENCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setdesiredngencompilerflags-method.md) Methode, um die Flags festgelegt, die die CLR verwendet, um die richtige vorkompiliert das zu ladende Bild auswählen.</span><span class="sxs-lookup"><span data-stu-id="17d99-108">Use the [ICorDebugProcess2::SetDesiredNGENCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setdesiredngencompilerflags-method.md) method to set the flags that the CLR will use to select the correct pre-compiled image to load.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17d99-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="17d99-109">Requirements</span></span>  
 <span data-ttu-id="17d99-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17d99-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17d99-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="17d99-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="17d99-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="17d99-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="17d99-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17d99-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
