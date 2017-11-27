---
title: ICorDebugClass::GetModule-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugClass.GetModule
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugClass::GetModule
helpviewer_keywords:
- GetModule method, ICorDebugClass interface [.NET Framework debugging]
- ICorDebugClass::GetModule method [.NET Framework debugging]
ms.assetid: 87029cc4-e5e1-42d5-8b98-655bb7ece520
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8021eb63b33f653e5b8c8a16d2e181223d5ee2b0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugclassgetmodule-method"></a><span data-ttu-id="6d2f0-102">ICorDebugClass::GetModule-Methode</span><span class="sxs-lookup"><span data-stu-id="6d2f0-102">ICorDebugClass::GetModule Method</span></span>
<span data-ttu-id="6d2f0-103">Ruft das Modul, das diese Klasse definiert.</span><span class="sxs-lookup"><span data-stu-id="6d2f0-103">Gets the module that defines this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d2f0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6d2f0-104">Syntax</span></span>  
  
```  
HRESULT GetModule (  
    [out] ICorDebugModule    **pModule  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6d2f0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6d2f0-105">Parameters</span></span>  
 `pModule`  
 <span data-ttu-id="6d2f0-106">[out] Ein Zeiger auf die Adresse eines ICorDebugModule-Objekts, das das Modul darstellt, in dem diese Klasse definiert ist.</span><span class="sxs-lookup"><span data-stu-id="6d2f0-106">[out] A pointer to the address of an ICorDebugModule object that represents the module in which this class is defined.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d2f0-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6d2f0-107">Requirements</span></span>  
 <span data-ttu-id="6d2f0-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d2f0-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d2f0-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6d2f0-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6d2f0-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6d2f0-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6d2f0-111">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d2f0-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
