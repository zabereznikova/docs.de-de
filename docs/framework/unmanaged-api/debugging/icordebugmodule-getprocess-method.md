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
ms.openlocfilehash: 97cecd66462cf6a88012b13dec82dbf617891dd5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61987999"
---
# <a name="icordebugmodulegetprocess-method"></a><span data-ttu-id="621a8-102">ICorDebugModule::GetProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="621a8-102">ICorDebugModule::GetProcess Method</span></span>
<span data-ttu-id="621a8-103">Ruft die enthaltende Prozess dieses Moduls ab.</span><span class="sxs-lookup"><span data-stu-id="621a8-103">Gets the containing process of this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="621a8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="621a8-104">Syntax</span></span>  
  
```  
HRESULT GetProcess (  
    [out] ICorDebugProcess **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="621a8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="621a8-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="621a8-106">[out] Ein Zeiger auf die Adresse des ein ICorDebugProcess-Objekt, das den Prozess, der mit diesem Modul darstellt.</span><span class="sxs-lookup"><span data-stu-id="621a8-106">[out] A pointer to the address of an ICorDebugProcess object that represents the process containing this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="621a8-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="621a8-107">Requirements</span></span>  
 <span data-ttu-id="621a8-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="621a8-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="621a8-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="621a8-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="621a8-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="621a8-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="621a8-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="621a8-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
