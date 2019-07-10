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
ms.openlocfilehash: ff7c77a27e9be58e9702c3a5e3f990863dc83901
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763624"
---
# <a name="icordebugmodulegetprocess-method"></a><span data-ttu-id="dbd1c-102">ICorDebugModule::GetProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="dbd1c-102">ICorDebugModule::GetProcess Method</span></span>
<span data-ttu-id="dbd1c-103">Ruft die enthaltende Prozess dieses Moduls ab.</span><span class="sxs-lookup"><span data-stu-id="dbd1c-103">Gets the containing process of this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbd1c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dbd1c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess (  
    [out] ICorDebugProcess **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dbd1c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="dbd1c-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="dbd1c-106">[out] Ein Zeiger auf die Adresse des ein ICorDebugProcess-Objekt, das den Prozess, der mit diesem Modul darstellt.</span><span class="sxs-lookup"><span data-stu-id="dbd1c-106">[out] A pointer to the address of an ICorDebugProcess object that represents the process containing this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dbd1c-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dbd1c-107">Requirements</span></span>  
 <span data-ttu-id="dbd1c-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dbd1c-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dbd1c-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dbd1c-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dbd1c-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dbd1c-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dbd1c-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dbd1c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
