---
title: ICorDebugProcess::IsTransitionStub-Methode
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e06dc35998a2874ed1d2f76725078874817e94d8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420094"
---
# <a name="icordebugprocessistransitionstub-method"></a><span data-ttu-id="4e084-102">ICorDebugProcess::IsTransitionStub-Methode</span><span class="sxs-lookup"><span data-stu-id="4e084-102">ICorDebugProcess::IsTransitionStub Method</span></span>
<span data-ttu-id="4e084-103">Ruft einen Wert, der angibt, ob eine Adresse innerhalb eines Stubs befindet, das einen Übergang zu verwaltetem Code bewirkt.</span><span class="sxs-lookup"><span data-stu-id="4e084-103">Gets a value that indicates whether an address is inside a stub that will cause a transition to managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e084-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4e084-104">Syntax</span></span>  
  
```  
HRESULT IsTransitionStub(  
    [in]  CORDB_ADDRESS address,  
    [out] BOOL *pbTransitionStub);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4e084-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4e084-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="4e084-106">[in] Ein `CORDB_ADDRESS` Wert, der die fragliche Adresse angibt.</span><span class="sxs-lookup"><span data-stu-id="4e084-106">[in] A `CORDB_ADDRESS` value that specifies the address in question.</span></span>  
  
 `pbTransitionStub`  
 <span data-ttu-id="4e084-107">[out] Ein Zeiger auf einen booleschen Wert, der `true` , wenn die angegebene Adresse innerhalb eines Stubs befindet, das bewirkt einen Übergang zu verwaltetem Code; andernfalls \*`pbTransitionStub` ist `false`.</span><span class="sxs-lookup"><span data-stu-id="4e084-107">[out] A pointer to a Boolean value that is `true` if the specified address is inside a stub that will cause a transition to managed code; otherwise \*`pbTransitionStub` is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4e084-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4e084-108">Remarks</span></span>  
 <span data-ttu-id="4e084-109">Die `IsTransitionStub` Methode kann von nicht verwaltetem stepping-Code verwendet werden, um zu entscheiden, wann schrittweisen Steuerung an den verwalteten zugeordnetem zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4e084-109">The `IsTransitionStub` method can be used by unmanaged stepping code to decide when to return stepping control to the managed stepper.</span></span>  
  
 <span data-ttu-id="4e084-110">Sie können auch die Identität Übergangsstubs durch einen Blick auf die Informationen in der portablen ausführbaren Datei (PE)-Datei.</span><span class="sxs-lookup"><span data-stu-id="4e084-110">You can also identity transition stubs by looking at information in the portable executable (PE) file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e084-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4e084-111">Requirements</span></span>  
 <span data-ttu-id="4e084-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e084-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e084-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4e084-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4e084-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4e084-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4e084-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e084-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
