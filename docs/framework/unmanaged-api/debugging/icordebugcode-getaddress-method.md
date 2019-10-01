---
title: ICorDebugCode::GetAddress-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetAddress
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetAddress
helpviewer_keywords:
- GetAddress method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetAddress method [.NET Framework debugging]
ms.assetid: cc507cb0-df2e-49c2-b32e-0c3271a8df9a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7df668487601e4278b56e196a43d1154b643fd29
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700743"
---
# <a name="icordebugcodegetaddress-method"></a><span data-ttu-id="d29b1-102">ICorDebugCode::GetAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="d29b1-102">ICorDebugCode::GetAddress Method</span></span>
<span data-ttu-id="d29b1-103">Ruft die relative virtuelle Adresse (RVA) des Code Segments ab, das diese ICorDebugCode-Schnittstelle darstellt.</span><span class="sxs-lookup"><span data-stu-id="d29b1-103">Gets the relative virtual address (RVA) of the code segment that this "ICorDebugCode" interface represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d29b1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d29b1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS *pStart  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d29b1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d29b1-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="d29b1-106">vorgenommen Ein Zeiger auf die RVA des Code Segments.</span><span class="sxs-lookup"><span data-stu-id="d29b1-106">[out] A pointer to the RVA of the code segment.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d29b1-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d29b1-107">Requirements</span></span>  
 <span data-ttu-id="d29b1-108">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d29b1-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d29b1-109">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="d29b1-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d29b1-110">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d29b1-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d29b1-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d29b1-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
