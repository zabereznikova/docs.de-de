---
title: ICorDebugModule::GetProcess-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetProcess
helpviewer_keywords:
- GetProcess method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetProcess method [.NET Framework debugging]
ms.assetid: 5e13446c-0271-446c-924a-9072c0e6eeae
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: add7239feb1cf6dab0fabe12e178336921211190
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33414205"
---
# <a name="icordebugmodulegetprocess-method"></a><span data-ttu-id="f001e-102">ICorDebugModule::GetProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="f001e-102">ICorDebugModule::GetProcess Method</span></span>
<span data-ttu-id="f001e-103">Ruft den enthaltenden Prozess dieses Moduls ab.</span><span class="sxs-lookup"><span data-stu-id="f001e-103">Gets the containing process of this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f001e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f001e-104">Syntax</span></span>  
  
```  
HRESULT GetProcess (  
    [out] ICorDebugProcess **ppProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f001e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f001e-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="f001e-106">[out] Ein Zeiger auf die Adresse eines ICorDebugProcess-Objekts, das den Prozess, der dieses Modul enthält darstellt.</span><span class="sxs-lookup"><span data-stu-id="f001e-106">[out] A pointer to the address of an ICorDebugProcess object that represents the process containing this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f001e-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f001e-107">Requirements</span></span>  
 <span data-ttu-id="f001e-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f001e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f001e-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f001e-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f001e-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f001e-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f001e-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f001e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
