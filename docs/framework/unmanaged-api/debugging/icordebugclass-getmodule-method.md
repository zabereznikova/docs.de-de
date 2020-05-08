---
title: ICorDebugClass::GetModule-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugClass.GetModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass::GetModule
helpviewer_keywords:
- GetModule method, ICorDebugClass interface [.NET Framework debugging]
- ICorDebugClass::GetModule method [.NET Framework debugging]
ms.assetid: 87029cc4-e5e1-42d5-8b98-655bb7ece520
topic_type:
- apiref
ms.openlocfilehash: fd048b692ad05f60621a057024be22cb48b3abbe
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894199"
---
# <a name="icordebugclassgetmodule-method"></a><span data-ttu-id="432a9-102">ICorDebugClass::GetModule-Methode</span><span class="sxs-lookup"><span data-stu-id="432a9-102">ICorDebugClass::GetModule Method</span></span>
<span data-ttu-id="432a9-103">Ruft das Modul ab, das diese Klasse definiert.</span><span class="sxs-lookup"><span data-stu-id="432a9-103">Gets the module that defines this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="432a9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="432a9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModule (  
    [out] ICorDebugModule    **pModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="432a9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="432a9-105">Parameters</span></span>  
 `pModule`  
 <span data-ttu-id="432a9-106">vorgenommen Ein Zeiger auf die Adresse eines ICorDebugModule-Objekts, das das Modul darstellt, in dem diese Klasse definiert ist.</span><span class="sxs-lookup"><span data-stu-id="432a9-106">[out] A pointer to the address of an ICorDebugModule object that represents the module in which this class is defined.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="432a9-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="432a9-107">Requirements</span></span>  
 <span data-ttu-id="432a9-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="432a9-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="432a9-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="432a9-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="432a9-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="432a9-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="432a9-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="432a9-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
