---
title: ICorDebug::EnumerateProcesses-Methode
ms.date: 03/30/2017
api_name:
- ICorDebug.EnumerateProcesses
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- EnumerateProcesses
helpviewer_keywords:
- EnumerateProcesses method [.NET Framework debugging]
- ICorDebug::EnumerateProcesses method [.NET Framework debugging]
ms.assetid: ba25d166-1d28-4f1d-aca2-de298bbca669
topic_type:
- apiref
ms.openlocfilehash: bf672c90cdbb9e9fb66105820a264a49601b38d7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723453"
---
# <a name="icordebugenumerateprocesses-method"></a><span data-ttu-id="457ec-102">ICorDebug::EnumerateProcesses-Methode</span><span class="sxs-lookup"><span data-stu-id="457ec-102">ICorDebug::EnumerateProcesses Method</span></span>

<span data-ttu-id="457ec-103">Ruft einen Enumerator für die Prozesse ab, die gedeentschlgt werden.</span><span class="sxs-lookup"><span data-stu-id="457ec-103">Gets an enumerator for the processes that are being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="457ec-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="457ec-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateProcesses (  
    [out] ICorDebugProcessEnum      **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="457ec-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="457ec-105">Parameters</span></span>  

 `ppProcess`  
 <span data-ttu-id="457ec-106">Ein Zeiger auf die Adresse eines ICorDebugProcessEnum-Objekts, bei dem es sich um den Enumerator für die Prozesse handelt, die gedebuggt werden.</span><span class="sxs-lookup"><span data-stu-id="457ec-106">A pointer to the address of an ICorDebugProcessEnum object that is the enumerator for the processes being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="457ec-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="457ec-107">Requirements</span></span>  

 <span data-ttu-id="457ec-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="457ec-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="457ec-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="457ec-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="457ec-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="457ec-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="457ec-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="457ec-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="457ec-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="457ec-112">See also</span></span>

- [<span data-ttu-id="457ec-113">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="457ec-113">ICorDebug Interface</span></span>](icordebug-interface.md)
