---
title: ICorDebugClass::GetModule-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugClass.GetModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass::GetModule
helpviewer_keywords:
- GetModule method, ICorDebugClass interface [.NET Framework debugging]
- ICorDebugClass::GetModule method [.NET Framework debugging]
ms.assetid: 87029cc4-e5e1-42d5-8b98-655bb7ece520
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9e96d0d82b08449b4675ec7fd1517317006011ae
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61989221"
---
# <a name="icordebugclassgetmodule-method"></a><span data-ttu-id="34f91-102">ICorDebugClass::GetModule-Methode</span><span class="sxs-lookup"><span data-stu-id="34f91-102">ICorDebugClass::GetModule Method</span></span>
<span data-ttu-id="34f91-103">Ruft das Modul, das diese Klasse definiert.</span><span class="sxs-lookup"><span data-stu-id="34f91-103">Gets the module that defines this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34f91-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="34f91-104">Syntax</span></span>  
  
```  
HRESULT GetModule (  
    [out] ICorDebugModule    **pModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="34f91-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="34f91-105">Parameters</span></span>  
 `pModule`  
 <span data-ttu-id="34f91-106">[out] Ein Zeiger auf die Adresse eines ICorDebugModule-Objekts, das das Modul darstellt, in dem diese Klasse definiert ist.</span><span class="sxs-lookup"><span data-stu-id="34f91-106">[out] A pointer to the address of an ICorDebugModule object that represents the module in which this class is defined.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34f91-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="34f91-107">Requirements</span></span>  
 <span data-ttu-id="34f91-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34f91-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34f91-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="34f91-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="34f91-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="34f91-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="34f91-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34f91-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
