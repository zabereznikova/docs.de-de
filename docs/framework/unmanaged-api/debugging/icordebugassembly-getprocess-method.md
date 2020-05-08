---
title: ICorDebugAssembly::GetProcess-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly::GetProcess
helpviewer_keywords:
- ICorDebugAssembly::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: ea52be06-0a16-4f57-afca-4287d72e76c4
topic_type:
- apiref
ms.openlocfilehash: c9cb599dd27a809ed5245c9570cddb8110be8172
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894926"
---
# <a name="icordebugassemblygetprocess-method"></a><span data-ttu-id="b6289-102">ICorDebugAssembly::GetProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="b6289-102">ICorDebugAssembly::GetProcess Method</span></span>
<span data-ttu-id="b6289-103">Ruft einen Schnittstellen Zeiger auf den Prozess ab, in dem diese ICorDebugAssembly-Instanz ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b6289-103">Gets an interface pointer to the process in which this ICorDebugAssembly instance is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6289-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b6289-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess (  
    [out] ICorDebugProcess **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b6289-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b6289-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="b6289-106">vorgenommen Ein Zeiger auf eine ICorDebugProcess-Schnittstelle, die den Prozess darstellt.</span><span class="sxs-lookup"><span data-stu-id="b6289-106">[out] A pointer to an ICorDebugProcess interface that represents the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6289-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b6289-107">Requirements</span></span>  
 <span data-ttu-id="b6289-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6289-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6289-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b6289-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b6289-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b6289-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b6289-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6289-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
