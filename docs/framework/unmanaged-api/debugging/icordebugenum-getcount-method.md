---
title: ICorDebugEnum::GetCount-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugEnum.GetCount
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEnum::GetCount
helpviewer_keywords:
- ICorDebugEnum::GetCount method [.NET Framework debugging]
- GetCount method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: d8a74304-1cb2-4977-a21d-e1af48c563ff
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5eddad89c60f25c957a06822d54cc73501b974ee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33415628"
---
# <a name="icordebugenumgetcount-method"></a><span data-ttu-id="a4b40-102">ICorDebugEnum::GetCount-Methode</span><span class="sxs-lookup"><span data-stu-id="a4b40-102">ICorDebugEnum::GetCount Method</span></span>
<span data-ttu-id="a4b40-103">Ruft die Anzahl der Elemente in der Enumeration.</span><span class="sxs-lookup"><span data-stu-id="a4b40-103">Gets the number of items in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4b40-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a4b40-104">Syntax</span></span>  
  
```  
HRESULT GetCount (  
    [out] ULONG *pcelt  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a4b40-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a4b40-105">Parameters</span></span>  
 `pcelt`  
 <span data-ttu-id="a4b40-106">[out] Ein Zeiger auf die Anzahl der Elemente in der Enumeration.</span><span class="sxs-lookup"><span data-stu-id="a4b40-106">[out] A pointer to the number of items in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4b40-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a4b40-107">Requirements</span></span>  
 <span data-ttu-id="a4b40-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a4b40-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4b40-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a4b40-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a4b40-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a4b40-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a4b40-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4b40-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
