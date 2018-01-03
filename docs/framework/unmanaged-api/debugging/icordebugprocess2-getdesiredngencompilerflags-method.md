---
title: ICorDebugProcess2::GetDesiredNGENCompilerFlags-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess2.GetDesiredNGENCompilerFlags
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess2::GetDesiredNGENCompilerFlags
helpviewer_keywords:
- ICorDebugProcess2::GetDesiredNGENCompilerFlags method [.NET Framework debugging]
- GetDesiredNGENCompilerFlags method [.NET Framework debugging]
ms.assetid: fc834580-3a90-4315-95d2-349b6bb7d059
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7306174f6c60d814474d7f142da49a2a4013f19b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess2getdesiredngencompilerflags-method"></a><span data-ttu-id="bfa14-102">ICorDebugProcess2::GetDesiredNGENCompilerFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="bfa14-102">ICorDebugProcess2::GetDesiredNGENCompilerFlags Method</span></span>
<span data-ttu-id="bfa14-103">Ruft den aktuellen Compiler Flageinstellungen, die die common Language Runtime (CLR) verwendet, um den richtigen vorkompilierte auszuwählen (d. h. systemeigene) Image in diesen Prozess geladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="bfa14-103">Gets the current compiler flag settings that the common language runtime (CLR) uses to select the correct precompiled (that is, native) image to be loaded into this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfa14-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bfa14-104">Syntax</span></span>  
  
```  
HRESULT GetDesiredNGENCompilerFlags (  
    [out] DWORD   *pdwFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bfa14-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bfa14-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="bfa14-106">[out] Ein Zeiger auf eine bitweise Kombination der [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) Enumerationswerte, die verwendet werden, wählen Sie das richtige vorkompilierte Bild geladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="bfa14-106">[out] A pointer to a bitwise combination of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration values that are used to select the correct precompiled image to be loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bfa14-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bfa14-107">Remarks</span></span>  
 <span data-ttu-id="bfa14-108">Verwenden Sie die [ICorDebugProcess2:: SetDesiredNGENCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setdesiredngencompilerflags-method.md) Methode, um die Flags festgelegt, die die CLR verwendet, um die richtige vorkompiliert das zu ladende Bild auswählen.</span><span class="sxs-lookup"><span data-stu-id="bfa14-108">Use the [ICorDebugProcess2::SetDesiredNGENCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setdesiredngencompilerflags-method.md) method to set the flags that the CLR will use to select the correct pre-compiled image to load.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bfa14-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bfa14-109">Requirements</span></span>  
 <span data-ttu-id="bfa14-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bfa14-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bfa14-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bfa14-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bfa14-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bfa14-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bfa14-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bfa14-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
