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
ms.openlocfilehash: c071a7ddb7d8d3f0e6487ab85284c45f9a7f0372
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178841"
---
# <a name="icordebugilframeenumeratelocalvariables-method"></a><span data-ttu-id="2bb93-102">ICorDebugILFrame::EnumerateLocalVariables-Methode</span><span class="sxs-lookup"><span data-stu-id="2bb93-102">ICorDebugILFrame::EnumerateLocalVariables Method</span></span>
<span data-ttu-id="2bb93-103">Ruft einen Enumerator für die lokalen Variablen in diesem Frame ab.</span><span class="sxs-lookup"><span data-stu-id="2bb93-103">Gets an enumerator for the local variables in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bb93-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2bb93-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateLocalVariables(
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2bb93-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2bb93-105">Parameters</span></span>  
 `ppValueEnum`  
 <span data-ttu-id="2bb93-106">[out] Ein Zeiger auf die Adresse eines ICorDebugValueEnum-Objekts, das den Enumerator für die lokale Variable im Rahmen darstellt.</span><span class="sxs-lookup"><span data-stu-id="2bb93-106">[out] A pointer to the address of an ICorDebugValueEnum object that is the enumerator for the local variables in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2bb93-107">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="2bb93-107">Remarks</span></span>  
 <span data-ttu-id="2bb93-108">`EnumerateLocalVariables`ruft einen Enumerator ab, der die lokalen Variablen auflisten kann, die im Aufrufframe verfügbar sind, der durch dieses ICorDebugILFrame-Objekt dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="2bb93-108">`EnumerateLocalVariables` gets an enumerator that can list the local variables available in the call frame that is represented by this ICorDebugILFrame object.</span></span> <span data-ttu-id="2bb93-109">Die Liste enthält möglicherweise nicht alle lokalen Variablen in der laufenden Funktion, da einige von ihnen möglicherweise nicht aktiv sind.</span><span class="sxs-lookup"><span data-stu-id="2bb93-109">The list may not include all of the local variables in the running function, because some of them may not be active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2bb93-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2bb93-110">Requirements</span></span>  
 <span data-ttu-id="2bb93-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2bb93-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2bb93-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2bb93-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2bb93-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2bb93-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2bb93-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2bb93-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
