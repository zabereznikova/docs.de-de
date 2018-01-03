---
title: ICorDebugFunction::GetILCode-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFunction.GetILCode
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFunction::GetILCode
helpviewer_keywords:
- ICorDebugFunction::GetILCode method [.NET Framework debugging]
- GetILCode method [.NET Framework debugging]
ms.assetid: f794dd47-a7cd-47f6-96e9-a41a4dae8e72
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ba960246c5aa1057df517d776819817d777402f4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugfunctiongetilcode-method"></a><span data-ttu-id="92a9b-102">ICorDebugFunction::GetILCode-Methode</span><span class="sxs-lookup"><span data-stu-id="92a9b-102">ICorDebugFunction::GetILCode Method</span></span>
<span data-ttu-id="92a9b-103">Ruft die ICorDebugCode-Instanz, die die Microsoft intermediate Language (MSIL)-Code dieses ICorDebugFunction-Objekt zugeordnet darstellt.</span><span class="sxs-lookup"><span data-stu-id="92a9b-103">Gets the ICorDebugCode instance that represents the Microsoft intermediate language (MSIL) code associated with this ICorDebugFunction object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92a9b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="92a9b-104">Syntax</span></span>  
  
```  
HRESULT GetILCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="92a9b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="92a9b-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="92a9b-106">[out] Ein Zeiger auf die `ICorDebugCode` -Instanz oder null, wenn die Funktion nicht in MSIL kompiliert wurde.</span><span class="sxs-lookup"><span data-stu-id="92a9b-106">[out] A pointer to the `ICorDebugCode` instance, or null, if the function was not compiled into MSIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="92a9b-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="92a9b-107">Remarks</span></span>  
 <span data-ttu-id="92a9b-108">Wenn Bearbeiten und Fortfahren wurde zugelassen. für diese Funktion die `GetILCode` Methode den MSIL-Code entspricht diese Funktion bearbeitete Version des Codes in der common Language Runtime (CLR) erhalten.</span><span class="sxs-lookup"><span data-stu-id="92a9b-108">If Edit and Continue has been allowed on this function, the `GetILCode` method will get the MSIL code corresponding to this function's edited version of the code in the common language runtime (CLR).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92a9b-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="92a9b-109">Requirements</span></span>  
 <span data-ttu-id="92a9b-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="92a9b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92a9b-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="92a9b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="92a9b-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="92a9b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="92a9b-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92a9b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
