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
ms.openlocfilehash: da955f6eb8e7480fb23192e1a77341166dd40f3b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugfunctiongetilcode-method"></a><span data-ttu-id="d6daa-102">ICorDebugFunction::GetILCode-Methode</span><span class="sxs-lookup"><span data-stu-id="d6daa-102">ICorDebugFunction::GetILCode Method</span></span>
<span data-ttu-id="d6daa-103">Ruft die ICorDebugCode-Instanz, die die Microsoft intermediate Language (MSIL)-Code dieses ICorDebugFunction-Objekt zugeordnet darstellt.</span><span class="sxs-lookup"><span data-stu-id="d6daa-103">Gets the ICorDebugCode instance that represents the Microsoft intermediate language (MSIL) code associated with this ICorDebugFunction object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6daa-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d6daa-104">Syntax</span></span>  
  
```  
HRESULT GetILCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d6daa-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d6daa-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="d6daa-106">[out] Ein Zeiger auf die `ICorDebugCode` -Instanz oder null, wenn die Funktion nicht in MSIL kompiliert wurde.</span><span class="sxs-lookup"><span data-stu-id="d6daa-106">[out] A pointer to the `ICorDebugCode` instance, or null, if the function was not compiled into MSIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d6daa-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d6daa-107">Remarks</span></span>  
 <span data-ttu-id="d6daa-108">Wenn Bearbeiten und Fortfahren wurde zugelassen. für diese Funktion die `GetILCode` Methode den MSIL-Code entspricht diese Funktion bearbeitete Version des Codes in der common Language Runtime (CLR) erhalten.</span><span class="sxs-lookup"><span data-stu-id="d6daa-108">If Edit and Continue has been allowed on this function, the `GetILCode` method will get the MSIL code corresponding to this function's edited version of the code in the common language runtime (CLR).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6daa-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d6daa-109">Requirements</span></span>  
 <span data-ttu-id="d6daa-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6daa-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6daa-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d6daa-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d6daa-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d6daa-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d6daa-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6daa-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
