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
ms.openlocfilehash: 687c3bb441c2a12529c873b4fa5f9283b9326a40
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54659068"
---
# <a name="icordebugvariablehomegetoffset-method"></a><span data-ttu-id="2095e-102">ICorDebugVariableHome::GetOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="2095e-102">ICorDebugVariableHome::GetOffset Method</span></span>
<span data-ttu-id="2095e-103">Ruft den Offset aus dem Basis-Register für eine Variable ab.</span><span class="sxs-lookup"><span data-stu-id="2095e-103">Gets the offset from the base register for a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2095e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2095e-104">Syntax</span></span>  
  
```  
HRESULT GetOffset(  
    [out] LONG *pOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2095e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2095e-105">Parameters</span></span>  
 `pOffset`  
 <span data-ttu-id="2095e-106">[out] Der Offset aus dem Basis-Register.</span><span class="sxs-lookup"><span data-stu-id="2095e-106">[out] The offset from the base register.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2095e-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2095e-107">Return Value</span></span>  
 <span data-ttu-id="2095e-108">Die Methode gibt die folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="2095e-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="2095e-109">Wert</span><span class="sxs-lookup"><span data-stu-id="2095e-109">Value</span></span>|<span data-ttu-id="2095e-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2095e-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="2095e-111">Die Variable ist in einem Register bezogene-Speicherort.</span><span class="sxs-lookup"><span data-stu-id="2095e-111">The variable is in a register-relative memory location.</span></span>|  
|`E_FAIL`|<span data-ttu-id="2095e-112">Die Variable ist nicht in einem Register bezogene-Speicherort.</span><span class="sxs-lookup"><span data-stu-id="2095e-112">The variable is not in a register-relative memory location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2095e-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2095e-113">Requirements</span></span>  
 <span data-ttu-id="2095e-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2095e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2095e-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2095e-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2095e-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2095e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2095e-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2095e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2095e-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2095e-118">See also</span></span>
- [<span data-ttu-id="2095e-119">ICorDebugVariableHome-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2095e-119">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
