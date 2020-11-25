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
ms.openlocfilehash: 46c2b444984c5a0062f1cfbc0cd29dbe409b16fa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723440"
---
# <a name="icordebuggetprocess-method"></a><span data-ttu-id="f5a2c-102">ICorDebug::GetProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="f5a2c-102">ICorDebug::GetProcess Method</span></span>

<span data-ttu-id="f5a2c-103">Ruft einen Zeiger auf die ICorDebugProcess-Instanz für den angegebenen Prozess ab.</span><span class="sxs-lookup"><span data-stu-id="f5a2c-103">Gets a pointer to the "ICorDebugProcess" instance for the specified process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5a2c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f5a2c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess (  
    [in] DWORD               dwProcessId,  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5a2c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f5a2c-105">Parameters</span></span>  

 `dwProcessId`  
 <span data-ttu-id="f5a2c-106">in Die ID des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="f5a2c-106">[in] The ID of the process.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="f5a2c-107">vorgenommen Ein Zeiger auf die Adresse einer- `ICorDebugProcess` Instanz für den angegebenen Prozess.</span><span class="sxs-lookup"><span data-stu-id="f5a2c-107">[out] A pointer to the address of a `ICorDebugProcess` instance for the specified process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5a2c-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f5a2c-108">Requirements</span></span>  

 <span data-ttu-id="f5a2c-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5a2c-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5a2c-110">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f5a2c-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f5a2c-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f5a2c-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f5a2c-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5a2c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5a2c-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f5a2c-113">See also</span></span>

- [<span data-ttu-id="f5a2c-114">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f5a2c-114">ICorDebug Interface</span></span>](icordebug-interface.md)
