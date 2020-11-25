---
title: ICorDebugILFrame::EnumerateLocalVariables-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.EnumerateLocalVariables
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::EnumerateLocalVariables
helpviewer_keywords:
- EnumerateLocalVariables method [.NET Framework debugging]
- ICorDebugILFrame::EnumerateLocalVariables method [.NET Framework debugging]
ms.assetid: 1a67fa1b-2419-4cd0-aad4-6f46a0719b4b
topic_type:
- apiref
ms.openlocfilehash: 968ceec53aade3d04c500c8247d397ffb71382c1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703186"
---
# <a name="icordebugilframeenumeratelocalvariables-method"></a><span data-ttu-id="05000-102">ICorDebugILFrame::EnumerateLocalVariables-Methode</span><span class="sxs-lookup"><span data-stu-id="05000-102">ICorDebugILFrame::EnumerateLocalVariables Method</span></span>

<span data-ttu-id="05000-103">Ruft einen Enumerator für die lokalen Variablen in diesem Frame ab.</span><span class="sxs-lookup"><span data-stu-id="05000-103">Gets an enumerator for the local variables in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05000-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="05000-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateLocalVariables(
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="05000-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="05000-105">Parameters</span></span>  

 `ppValueEnum`  
 <span data-ttu-id="05000-106">[out] Ein Zeiger auf die Adresse eines ICorDebugValueEnum-Objekts, das den Enumerator für die lokale Variable im Rahmen darstellt.</span><span class="sxs-lookup"><span data-stu-id="05000-106">[out] A pointer to the address of an ICorDebugValueEnum object that is the enumerator for the local variables in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="05000-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="05000-107">Remarks</span></span>  

 <span data-ttu-id="05000-108">`EnumerateLocalVariables` Ruft einen Enumerator ab, der die lokalen Variablen auflisten kann, die in dem von diesem ICorDebugILFrame-Objekt dargestellten Aufrufframe verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="05000-108">`EnumerateLocalVariables` gets an enumerator that can list the local variables available in the call frame that is represented by this ICorDebugILFrame object.</span></span> <span data-ttu-id="05000-109">Die Liste enthält möglicherweise nicht alle lokalen Variablen in der Funktion "wird ausgeführt", da einige von Ihnen möglicherweise nicht aktiv sind.</span><span class="sxs-lookup"><span data-stu-id="05000-109">The list may not include all of the local variables in the running function, because some of them may not be active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05000-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="05000-110">Requirements</span></span>  

 <span data-ttu-id="05000-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05000-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05000-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="05000-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="05000-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="05000-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="05000-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05000-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
