---
title: ICorDebugVariableHome::GetOffset-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetOffset
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetOffset
helpviewer_keywords:
- ICorDebugVariableHome::GetOffset method [.NET Framework debugging]
- GetOffset method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: f025c2e5-3f6c-4be8-9ffe-c8b214617dfe
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 864cb893511bceabd61ce0064065b3866ce01dfe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986751"
---
# <a name="icordebugvariablehomegetoffset-method"></a><span data-ttu-id="8a012-102">ICorDebugVariableHome::GetOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="8a012-102">ICorDebugVariableHome::GetOffset Method</span></span>
<span data-ttu-id="8a012-103">Ruft den Offset aus dem Basis-Register für eine Variable ab.</span><span class="sxs-lookup"><span data-stu-id="8a012-103">Gets the offset from the base register for a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a012-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8a012-104">Syntax</span></span>  
  
```  
HRESULT GetOffset(  
    [out] LONG *pOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8a012-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8a012-105">Parameters</span></span>  
 `pOffset`  
 <span data-ttu-id="8a012-106">[out] Der Offset aus dem Basis-Register.</span><span class="sxs-lookup"><span data-stu-id="8a012-106">[out] The offset from the base register.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8a012-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8a012-107">Return Value</span></span>  
 <span data-ttu-id="8a012-108">Die Methode gibt die folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="8a012-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="8a012-109">Wert</span><span class="sxs-lookup"><span data-stu-id="8a012-109">Value</span></span>|<span data-ttu-id="8a012-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8a012-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="8a012-111">Die Variable ist in einem Register bezogene-Speicherort.</span><span class="sxs-lookup"><span data-stu-id="8a012-111">The variable is in a register-relative memory location.</span></span>|  
|`E_FAIL`|<span data-ttu-id="8a012-112">Die Variable ist nicht in einem Register bezogene-Speicherort.</span><span class="sxs-lookup"><span data-stu-id="8a012-112">The variable is not in a register-relative memory location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8a012-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8a012-113">Requirements</span></span>  
 <span data-ttu-id="8a012-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a012-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a012-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8a012-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8a012-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a012-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a012-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a012-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a012-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8a012-118">See also</span></span>

- [<span data-ttu-id="8a012-119">ICorDebugVariableHome-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8a012-119">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
