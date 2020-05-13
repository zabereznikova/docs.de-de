---
title: ICorDebugFunction::GetModule-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetModule
helpviewer_keywords:
- ICorDebugFunction::GetModule method [.NET Framework debugging]
- GetModule method, ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: 5031a5d3-2564-412a-9007-e36d4631308a
topic_type:
- apiref
ms.openlocfilehash: 41ad10fecca2ba1831d9e0d1120d3d1be0be92ad
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212957"
---
# <a name="icordebugfunctiongetmodule-method"></a><span data-ttu-id="d1cfb-102">ICorDebugFunction::GetModule-Methode</span><span class="sxs-lookup"><span data-stu-id="d1cfb-102">ICorDebugFunction::GetModule Method</span></span>
<span data-ttu-id="d1cfb-103">Ruft das Modul ab, in dem diese Funktion definiert ist.</span><span class="sxs-lookup"><span data-stu-id="d1cfb-103">Gets the module in which this function is defined.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1cfb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d1cfb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModule (  
    [out] ICorDebugModule **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d1cfb-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d1cfb-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="d1cfb-106">vorgenommen Ein Zeiger auf die Adresse eines ICorDebug Module-Objekts, das das Modul darstellt, in dem diese Funktion definiert ist.</span><span class="sxs-lookup"><span data-stu-id="d1cfb-106">[out] A pointer to the address of an ICorDebugModule object that represents the module in which this function is defined.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1cfb-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d1cfb-107">Requirements</span></span>  
 <span data-ttu-id="d1cfb-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d1cfb-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1cfb-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d1cfb-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d1cfb-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d1cfb-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d1cfb-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1cfb-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
