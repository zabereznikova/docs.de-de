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
ms.openlocfilehash: f9b00d5e34300f1ed16eaddff3bf8e877219f910
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82893801"
---
# <a name="icordebugcodegetaddress-method"></a><span data-ttu-id="eac86-102">ICorDebugCode::GetAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="eac86-102">ICorDebugCode::GetAddress Method</span></span>
<span data-ttu-id="eac86-103">Ruft die relative virtuelle Adresse (RVA) des Code Segments ab, das diese ICorDebugCode-Schnittstelle darstellt.</span><span class="sxs-lookup"><span data-stu-id="eac86-103">Gets the relative virtual address (RVA) of the code segment that this "ICorDebugCode" interface represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eac86-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="eac86-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS *pStart  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eac86-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="eac86-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="eac86-106">vorgenommen Ein Zeiger auf die RVA des Code Segments.</span><span class="sxs-lookup"><span data-stu-id="eac86-106">[out] A pointer to the RVA of the code segment.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eac86-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="eac86-107">Requirements</span></span>  
 <span data-ttu-id="eac86-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eac86-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eac86-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eac86-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eac86-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eac86-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eac86-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eac86-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
