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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6fd7694901534ad6897bbf78239081af6314e4bd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33415467"
---
# <a name="icordebugilframeenumeratelocalvariables-method"></a><span data-ttu-id="fa2b8-102">ICorDebugILFrame::EnumerateLocalVariables-Methode</span><span class="sxs-lookup"><span data-stu-id="fa2b8-102">ICorDebugILFrame::EnumerateLocalVariables Method</span></span>
<span data-ttu-id="fa2b8-103">Ruft einen Enumerator für die lokalen Variablen in diesem Frame ab.</span><span class="sxs-lookup"><span data-stu-id="fa2b8-103">Gets an enumerator for the local variables in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa2b8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fa2b8-104">Syntax</span></span>  
  
```  
HRESULT EnumerateLocalVariables(   
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fa2b8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fa2b8-105">Parameters</span></span>  
 `ppValueEnum`  
 <span data-ttu-id="fa2b8-106">[out] Ein Zeiger auf die Adresse eines ICorDebugValueEnum-Objekts, das den Enumerator für die lokalen Variablen in diesem Frame darstellt.</span><span class="sxs-lookup"><span data-stu-id="fa2b8-106">[out] A pointer to the address of an ICorDebugValueEnum object that is the enumerator for the local variables in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa2b8-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fa2b8-107">Remarks</span></span>  
 <span data-ttu-id="fa2b8-108">`EnumerateLocalVariables` Gibt einen Enumerator zurück, der die lokalen Variablen in den Aufrufframe verfügbar auflisten kann, die von diesem ICorDebugILFrame-Objekt dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="fa2b8-108">`EnumerateLocalVariables` gets an enumerator that can list the local variables available in the call frame that is represented by this ICorDebugILFrame object.</span></span> <span data-ttu-id="fa2b8-109">Die Liste kann alle lokalen Variablen in die ausgeführte Funktion nicht enthalten, da einige von ihnen möglicherweise nicht aktiv sind.</span><span class="sxs-lookup"><span data-stu-id="fa2b8-109">The list may not include all of the local variables in the running function, because some of them may not be active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa2b8-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fa2b8-110">Requirements</span></span>  
 <span data-ttu-id="fa2b8-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa2b8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa2b8-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fa2b8-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fa2b8-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fa2b8-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fa2b8-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa2b8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
