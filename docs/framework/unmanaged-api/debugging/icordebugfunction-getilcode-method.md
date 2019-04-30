---
title: ICorDebugFunction::GetILCode-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetILCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetILCode
helpviewer_keywords:
- ICorDebugFunction::GetILCode method [.NET Framework debugging]
- GetILCode method [.NET Framework debugging]
ms.assetid: f794dd47-a7cd-47f6-96e9-a41a4dae8e72
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f34a2fe2bb1f92e75f77c086b03776ec59495600
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995747"
---
# <a name="icordebugfunctiongetilcode-method"></a><span data-ttu-id="a3f67-102">ICorDebugFunction::GetILCode-Methode</span><span class="sxs-lookup"><span data-stu-id="a3f67-102">ICorDebugFunction::GetILCode Method</span></span>
<span data-ttu-id="a3f67-103">Ruft die ICorDebugCode-Instanz, die diesem ICorDebugFunction-Objekt zugeordneten Codes Microsoft intermediate Language (MSIL) darstellt.</span><span class="sxs-lookup"><span data-stu-id="a3f67-103">Gets the ICorDebugCode instance that represents the Microsoft intermediate language (MSIL) code associated with this ICorDebugFunction object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3f67-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a3f67-104">Syntax</span></span>  
  
```  
HRESULT GetILCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a3f67-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a3f67-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="a3f67-106">[out] Ein Zeiger auf die `ICorDebugCode` -Instanz oder null, wenn die Funktion nicht in MSIL kompiliert wurde.</span><span class="sxs-lookup"><span data-stu-id="a3f67-106">[out] A pointer to the `ICorDebugCode` instance, or null, if the function was not compiled into MSIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a3f67-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a3f67-107">Remarks</span></span>  
 <span data-ttu-id="a3f67-108">Wenn Bearbeiten und Fortfahren wurde zugelassen. auf diese Funktion, die `GetILCode` Methode den MSIL-Code für diese Funktion die bearbeitete Version des Codes in der common Language Runtime (CLR) erhalten.</span><span class="sxs-lookup"><span data-stu-id="a3f67-108">If Edit and Continue has been allowed on this function, the `GetILCode` method will get the MSIL code corresponding to this function's edited version of the code in the common language runtime (CLR).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3f67-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a3f67-109">Requirements</span></span>  
 <span data-ttu-id="a3f67-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3f67-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3f67-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a3f67-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a3f67-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a3f67-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a3f67-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3f67-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
