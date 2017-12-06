---
title: ICorDebugReferenceValue::Dereference-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugReferenceValue.Dereference
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugReferenceValue::Dereference
helpviewer_keywords:
- ICorDebugReferenceValue::Dereference method [.NET Framework debugging]
- Dereference method [.NET Framework debugging]
ms.assetid: 5ec8cf76-3deb-4ce6-9a49-77a4c35d80b9
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4eb3287612a8301d551a1443d803e60e4d03f7db
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugreferencevaluedereference-method"></a><span data-ttu-id="13d08-102">ICorDebugReferenceValue::Dereference-Methode</span><span class="sxs-lookup"><span data-stu-id="13d08-102">ICorDebugReferenceValue::Dereference Method</span></span>
<span data-ttu-id="13d08-103">Ruft das Objekt ab, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="13d08-103">Gets the object that is referenced.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13d08-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="13d08-104">Syntax</span></span>  
  
```  
HRESULT Dereference (  
    [out] ICorDebugValue  **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="13d08-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="13d08-105">Parameters</span></span>  
 `ppValue`  
 <span data-ttu-id="13d08-106">[out] Ein Zeiger auf die Adresse des ICorDebugValue ab, der das Objekt darstellt, zu dem dieses Objekt ICorDebugReferenceValue verweist.</span><span class="sxs-lookup"><span data-stu-id="13d08-106">[out] A pointer to the address of an ICorDebugValue that represents the object to which this ICorDebugReferenceValue object points.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="13d08-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="13d08-107">Remarks</span></span>  
 <span data-ttu-id="13d08-108">Die `ICorDebugValue` Objekt gilt nur, während dessen Verweis noch nicht deaktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="13d08-108">The `ICorDebugValue` object is valid only while its reference has not yet been disabled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13d08-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="13d08-109">Requirements</span></span>  
 <span data-ttu-id="13d08-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13d08-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13d08-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="13d08-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="13d08-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="13d08-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="13d08-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13d08-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
