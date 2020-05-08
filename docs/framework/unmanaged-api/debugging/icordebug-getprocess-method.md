---
title: ICorDebug::GetProcess-Methode
ms.date: 03/30/2017
api_name:
- ICorDebug.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::GetProcess
helpviewer_keywords:
- GetProcess method, ICorDebug interface [.NET Framework debugging]
- ICorDebug::GetProcess method [.NET Framework debugging]
ms.assetid: 10a40ba0-1b65-4721-bd11-cf12d57b280d
topic_type:
- apiref
ms.openlocfilehash: 59afc8ae7d66e81e4dca3923f9c6f7ff3a3a6605
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895385"
---
# <a name="icordebuggetprocess-method"></a><span data-ttu-id="be483-102">ICorDebug::GetProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="be483-102">ICorDebug::GetProcess Method</span></span>
<span data-ttu-id="be483-103">Ruft einen Zeiger auf die ICorDebugProcess-Instanz für den angegebenen Prozess ab.</span><span class="sxs-lookup"><span data-stu-id="be483-103">Gets a pointer to the "ICorDebugProcess" instance for the specified process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be483-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="be483-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess (  
    [in] DWORD               dwProcessId,  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="be483-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="be483-105">Parameters</span></span>  
 `dwProcessId`  
 <span data-ttu-id="be483-106">in Die ID des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="be483-106">[in] The ID of the process.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="be483-107">vorgenommen Ein Zeiger auf die Adresse einer `ICorDebugProcess` -Instanz für den angegebenen Prozess.</span><span class="sxs-lookup"><span data-stu-id="be483-107">[out] A pointer to the address of a `ICorDebugProcess` instance for the specified process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be483-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="be483-108">Requirements</span></span>  
 <span data-ttu-id="be483-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be483-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be483-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="be483-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="be483-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="be483-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="be483-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be483-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be483-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="be483-113">See also</span></span>

- [<span data-ttu-id="be483-114">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="be483-114">ICorDebug Interface</span></span>](icordebug-interface.md)
