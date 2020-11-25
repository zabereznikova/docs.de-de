---
title: ICorDebugModule::GetSize-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetSize method [.NET Framework debugging]
ms.assetid: 5c68375d-145d-46ef-a7c8-2dc4257472de
topic_type:
- apiref
ms.openlocfilehash: 0cfc31839b263c2e8cf44d15439b44ffacccf5bf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709894"
---
# <a name="icordebugmodulegetsize-method"></a><span data-ttu-id="d6493-102">ICorDebugModule::GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="d6493-102">ICorDebugModule::GetSize Method</span></span>

<span data-ttu-id="d6493-103">Ruft die Größe des Moduls in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="d6493-103">Gets the size, in bytes, of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6493-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d6493-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
    [out] ULONG32 *pcBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d6493-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d6493-105">Parameters</span></span>  

 `pcBytes`  
 <span data-ttu-id="d6493-106">vorgenommen Die Größe des Moduls in Bytes.</span><span class="sxs-lookup"><span data-stu-id="d6493-106">[out] The size of the module in bytes.</span></span>  
  
 <span data-ttu-id="d6493-107">Wenn das Modul aus dem nativen Image Generator (NGen.exe) erstellt wurde, ist die Größe des Moduls 0 (null).</span><span class="sxs-lookup"><span data-stu-id="d6493-107">If the module was produced from the native image generator (NGen.exe), the size of the module will be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6493-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d6493-108">Requirements</span></span>  

 <span data-ttu-id="d6493-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6493-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6493-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d6493-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d6493-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d6493-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d6493-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6493-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
