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
ms.openlocfilehash: c10c45c4450e02d633ebeeca15da95b7c95ff0b4
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212528"
---
# <a name="icordebugmodulegetprocess-method"></a><span data-ttu-id="6f586-102">ICorDebugModule::GetProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="6f586-102">ICorDebugModule::GetProcess Method</span></span>
<span data-ttu-id="6f586-103">Ruft den enthaltenden Prozess dieses Moduls ab.</span><span class="sxs-lookup"><span data-stu-id="6f586-103">Gets the containing process of this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f586-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6f586-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess (  
    [out] ICorDebugProcess **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6f586-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6f586-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="6f586-106">vorgenommen Ein Zeiger auf die Adresse eines ICorDebugProcess-Objekts, das den Prozess darstellt, der dieses Modul enthält.</span><span class="sxs-lookup"><span data-stu-id="6f586-106">[out] A pointer to the address of an ICorDebugProcess object that represents the process containing this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f586-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="6f586-107">Requirements</span></span>  
 <span data-ttu-id="6f586-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f586-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f586-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6f586-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6f586-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6f586-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6f586-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f586-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
