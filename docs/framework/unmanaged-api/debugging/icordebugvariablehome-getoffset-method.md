---
title: ICorDebugVariableHome::GetOffset-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorDebugVariableHome.GetOffset
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugVariableHome::GetOffset
helpviewer_keywords:
- ICorDebugVariableHome::GetOffset method [.NET Framework debugging]
- GetOffset method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: f025c2e5-3f6c-4be8-9ffe-c8b214617dfe
topic_type: apiref
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0ddedc83e4e51cf12a3f8a0504d90bda7f944a6d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugvariablehomegetoffset-method"></a><span data-ttu-id="5f49e-102">ICorDebugVariableHome::GetOffset-Methode</span><span class="sxs-lookup"><span data-stu-id="5f49e-102">ICorDebugVariableHome::GetOffset Method</span></span>
<span data-ttu-id="5f49e-103">Ruft den Offset von der Basisregister für eine Variable ab.</span><span class="sxs-lookup"><span data-stu-id="5f49e-103">Gets the offset from the base register for a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f49e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5f49e-104">Syntax</span></span>  
  
```  
HRESULT GetOffset(  
    [out] LONG *pOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5f49e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5f49e-105">Parameters</span></span>  
 `pOffset`  
 <span data-ttu-id="5f49e-106">[out] Der Offset aus dem Basis-Register.</span><span class="sxs-lookup"><span data-stu-id="5f49e-106">[out] The offset from the base register.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5f49e-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5f49e-107">Return Value</span></span>  
 <span data-ttu-id="5f49e-108">Die Methode gibt die folgenden Werte zurück:</span><span class="sxs-lookup"><span data-stu-id="5f49e-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="5f49e-109">Wert</span><span class="sxs-lookup"><span data-stu-id="5f49e-109">Value</span></span>|<span data-ttu-id="5f49e-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5f49e-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="5f49e-111">Die Variable ist in eine Register-Relative Speicheradresse.</span><span class="sxs-lookup"><span data-stu-id="5f49e-111">The variable is in a register-relative memory location.</span></span>|  
|`E_FAIL`|<span data-ttu-id="5f49e-112">Die Variable ist nicht in eine Register-Relative Speicheradresse.</span><span class="sxs-lookup"><span data-stu-id="5f49e-112">The variable is not in a register-relative memory location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5f49e-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5f49e-113">Requirements</span></span>  
 <span data-ttu-id="5f49e-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f49e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f49e-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5f49e-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5f49e-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5f49e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5f49e-117">**.NET Framework-Versionen:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f49e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f49e-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5f49e-118">See Also</span></span>  
 [<span data-ttu-id="5f49e-119">ICorDebugVariableHome-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5f49e-119">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
