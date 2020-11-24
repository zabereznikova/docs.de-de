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
ms.openlocfilehash: 223f66639ae24f2a54f1bc936f4a0765573356eb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673890"
---
# <a name="icordebugprocess2getdesiredngencompilerflags-method"></a><span data-ttu-id="28eb6-102">ICorDebugProcess2::GetDesiredNGENCompilerFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="28eb6-102">ICorDebugProcess2::GetDesiredNGENCompilerFlags Method</span></span>

<span data-ttu-id="28eb6-103">Ruft die aktuellen compilerflageinstellungen ab, die von der Common Language Runtime (CLR) verwendet werden, um das richtige vorkompilierte (d. h. systemeigene) Image auszuwählen, das in diesen Prozess geladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="28eb6-103">Gets the current compiler flag settings that the common language runtime (CLR) uses to select the correct precompiled (that is, native) image to be loaded into this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28eb6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="28eb6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDesiredNGENCompilerFlags (  
    [out] DWORD   *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="28eb6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="28eb6-105">Parameters</span></span>  

 `pdwFlags`  
 <span data-ttu-id="28eb6-106">vorgenommen Ein Zeiger auf eine bitweise Kombination der [CorDebugJITCompilerFlags-Enumerationswerte](cordebugjitcompilerflags-enumeration.md) , die zum Auswählen des richtigen vorkompilierten Bilds verwendet werden, das geladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="28eb6-106">[out] A pointer to a bitwise combination of the [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) enumeration values that are used to select the correct precompiled image to be loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="28eb6-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="28eb6-107">Remarks</span></span>  

 <span data-ttu-id="28eb6-108">Verwenden Sie die [ICorDebugProcess2:: SetDesiredNGENCompilerFlags](icordebugprocess2-setdesiredngencompilerflags-method.md) -Methode, um die Flags festzulegen, die von der CLR verwendet werden, um das richtige vorkompilierte Image auszuwählen, das geladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="28eb6-108">Use the [ICorDebugProcess2::SetDesiredNGENCompilerFlags](icordebugprocess2-setdesiredngencompilerflags-method.md) method to set the flags that the CLR will use to select the correct pre-compiled image to load.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28eb6-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="28eb6-109">Requirements</span></span>  

 <span data-ttu-id="28eb6-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28eb6-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28eb6-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="28eb6-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="28eb6-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="28eb6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="28eb6-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28eb6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
