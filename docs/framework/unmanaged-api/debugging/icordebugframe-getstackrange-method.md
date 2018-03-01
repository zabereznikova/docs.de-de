---
title: ICorDebugFrame::GetStackRange-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugFrame.GetStackRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetStackRange
helpviewer_keywords:
- GetStackRange method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetStackRange method [.NET Framework debugging]
ms.assetid: fab037cb-fda6-40fb-9367-921e435dd5a0
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3c4c9c0a531d93ca2c7c72f50bcd2f7ee98887e9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugframegetstackrange-method"></a><span data-ttu-id="2c7b0-102">ICorDebugFrame::GetStackRange-Methode</span><span class="sxs-lookup"><span data-stu-id="2c7b0-102">ICorDebugFrame::GetStackRange Method</span></span>
<span data-ttu-id="2c7b0-103">Ruft den Bereich der absoluten Adresse dieses Stapelrahmens ab.</span><span class="sxs-lookup"><span data-stu-id="2c7b0-103">Gets the absolute address range of this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c7b0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2c7b0-104">Syntax</span></span>  
  
```  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,   
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2c7b0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2c7b0-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="2c7b0-106">[out] Ein Zeiger auf eine `CORDB_ADDRESS` , die angibt, dass der Startadresse des Stapelrahmens dargestellt, die von diesem `ICorDebugFrame` Objekt.</span><span class="sxs-lookup"><span data-stu-id="2c7b0-106">[out] A pointer to a `CORDB_ADDRESS` that specifies the starting address of the stack frame represented by this `ICorDebugFrame` object.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="2c7b0-107">[out] Ein Zeiger auf eine `CORDB_ADDRESS` , die angibt, dass der Endadresse des Stapelrahmens dargestellt, die von diesem `ICorDebugFrame` Objekt.</span><span class="sxs-lookup"><span data-stu-id="2c7b0-107">[out] A pointer to a `CORDB_ADDRESS` that specifies the ending address of the stack frame represented by this `ICorDebugFrame` object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2c7b0-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2c7b0-108">Remarks</span></span>  
 <span data-ttu-id="2c7b0-109">Der Adressbereich des Stapels eignet sich für die Zusammenführung überlappender stapelüberwachungen von mehreren Debugmodule gesammelt wurden.</span><span class="sxs-lookup"><span data-stu-id="2c7b0-109">The address range of the stack is useful for piecing together interleaved stack traces gathered from multiple debugging engines.</span></span> <span data-ttu-id="2c7b0-110">Die numerische Bereich bietet keine Informationen zum Inhalt des Stapelrahmens.</span><span class="sxs-lookup"><span data-stu-id="2c7b0-110">The numeric range provides no information about the contents of the stack frame.</span></span> <span data-ttu-id="2c7b0-111">Es ist sinnvoll, nur für den Vergleich der Stack-Frame-Standorten.</span><span class="sxs-lookup"><span data-stu-id="2c7b0-111">It is meaningful only for comparison of stack frame locations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c7b0-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2c7b0-112">Requirements</span></span>  
 <span data-ttu-id="2c7b0-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c7b0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c7b0-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2c7b0-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2c7b0-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2c7b0-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2c7b0-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c7b0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
