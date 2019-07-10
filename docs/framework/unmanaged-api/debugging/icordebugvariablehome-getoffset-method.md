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
ms.openlocfilehash: 0fdab81d499fe1508493cb0bf05a1787974a9d01
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67774537"
---
# <a name="icordebugvariablehomegetoffset-method"></a><span data-ttu-id="63076-102">ICorDebugVariableHome::GetOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="63076-102">ICorDebugVariableHome::GetOffset Method</span></span>
<span data-ttu-id="63076-103">Ruft den Offset aus dem Basis-Register für eine Variable ab.</span><span class="sxs-lookup"><span data-stu-id="63076-103">Gets the offset from the base register for a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63076-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="63076-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset(  
    [out] LONG *pOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="63076-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="63076-105">Parameters</span></span>  
 `pOffset`  
 <span data-ttu-id="63076-106">[out] Der Offset aus dem Basis-Register.</span><span class="sxs-lookup"><span data-stu-id="63076-106">[out] The offset from the base register.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="63076-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="63076-107">Return Value</span></span>  
 <span data-ttu-id="63076-108">Die Methode gibt die folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="63076-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="63076-109">Wert</span><span class="sxs-lookup"><span data-stu-id="63076-109">Value</span></span>|<span data-ttu-id="63076-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="63076-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="63076-111">Die Variable ist in einem Register bezogene-Speicherort.</span><span class="sxs-lookup"><span data-stu-id="63076-111">The variable is in a register-relative memory location.</span></span>|  
|`E_FAIL`|<span data-ttu-id="63076-112">Die Variable ist nicht in einem Register bezogene-Speicherort.</span><span class="sxs-lookup"><span data-stu-id="63076-112">The variable is not in a register-relative memory location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="63076-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="63076-113">Requirements</span></span>  
 <span data-ttu-id="63076-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63076-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63076-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="63076-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="63076-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="63076-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="63076-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63076-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63076-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="63076-118">See also</span></span>

- [<span data-ttu-id="63076-119">ICorDebugVariableHome-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="63076-119">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
