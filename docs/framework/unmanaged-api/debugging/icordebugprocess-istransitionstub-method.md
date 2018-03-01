---
title: ICorDebugProcess::IsTransitionStub-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugProcess.IsTransitionStub
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::IsTransitionStub
helpviewer_keywords:
- ICorDebugProcess::IsTransitionStub method [.NET Framework debugging]
- IsTransitionStub method [.NET Framework debugging]
ms.assetid: f7653317-7e48-4163-be03-f50f1a4b0f70
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9fe38cf5f53c2514b845238c1d52fa12df526fdd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocessistransitionstub-method"></a><span data-ttu-id="0cde3-102">ICorDebugProcess::IsTransitionStub-Methode</span><span class="sxs-lookup"><span data-stu-id="0cde3-102">ICorDebugProcess::IsTransitionStub Method</span></span>
<span data-ttu-id="0cde3-103">Ruft einen Wert, der angibt, ob eine Adresse innerhalb eines Stubs befindet, das einen Übergang zu verwaltetem Code bewirkt.</span><span class="sxs-lookup"><span data-stu-id="0cde3-103">Gets a value that indicates whether an address is inside a stub that will cause a transition to managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0cde3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0cde3-104">Syntax</span></span>  
  
```  
HRESULT IsTransitionStub(  
    [in]  CORDB_ADDRESS address,  
    [out] BOOL *pbTransitionStub);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0cde3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0cde3-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="0cde3-106">[in] Ein `CORDB_ADDRESS` Wert, der die fragliche Adresse angibt.</span><span class="sxs-lookup"><span data-stu-id="0cde3-106">[in] A `CORDB_ADDRESS` value that specifies the address in question.</span></span>  
  
 `pbTransitionStub`  
 <span data-ttu-id="0cde3-107">[out] Ein Zeiger auf einen booleschen Wert, der `true` , wenn die angegebene Adresse innerhalb eines Stubs befindet, das bewirkt einen Übergang zu verwaltetem Code; andernfalls \*`pbTransitionStub` ist `false`.</span><span class="sxs-lookup"><span data-stu-id="0cde3-107">[out] A pointer to a Boolean value that is `true` if the specified address is inside a stub that will cause a transition to managed code; otherwise \*`pbTransitionStub` is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0cde3-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0cde3-108">Remarks</span></span>  
 <span data-ttu-id="0cde3-109">Die `IsTransitionStub` Methode kann von nicht verwaltetem stepping-Code verwendet werden, um zu entscheiden, wann schrittweisen Steuerung an den verwalteten zugeordnetem zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0cde3-109">The `IsTransitionStub` method can be used by unmanaged stepping code to decide when to return stepping control to the managed stepper.</span></span>  
  
 <span data-ttu-id="0cde3-110">Sie können auch die Identität Übergangsstubs durch einen Blick auf die Informationen in der portablen ausführbaren Datei (PE)-Datei.</span><span class="sxs-lookup"><span data-stu-id="0cde3-110">You can also identity transition stubs by looking at information in the portable executable (PE) file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0cde3-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0cde3-111">Requirements</span></span>  
 <span data-ttu-id="0cde3-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0cde3-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0cde3-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0cde3-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0cde3-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0cde3-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0cde3-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0cde3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
