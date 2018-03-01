---
title: ICorDebugNativeFrame::GetLocalDoubleRegisterValue-Methode
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
- ICorDebugNativeFrame.GetLocalDoubleRegisterValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalDoubleRegisterValue
helpviewer_keywords:
- ICorDebugNativeFrame::GetLocalDoubleRegisterValue method [.NET Framework debugging]
- GetLocalDoubleRegisterValue method [.NET Framework debugging]
ms.assetid: 1f838215-ac8a-434f-8ce6-03021d3098d9
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ece07fcffbc0d0e6b8cf06cc04866c1b651e6a01
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugnativeframegetlocaldoubleregistervalue-method"></a><span data-ttu-id="14c36-102">ICorDebugNativeFrame::GetLocalDoubleRegisterValue-Methode</span><span class="sxs-lookup"><span data-stu-id="14c36-102">ICorDebugNativeFrame::GetLocalDoubleRegisterValue Method</span></span>
<span data-ttu-id="14c36-103">Ruft den Wert eines Arguments oder einer lokalen Variablen, die in den zwei angegebenen Registern für diese systemeigenen Rahmen gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="14c36-103">Gets the value of an argument or local variable that is stored in the two specified registers for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14c36-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="14c36-104">Syntax</span></span>  
  
```  
HRESULT GetLocalDoubleRegisterValue (  
    [in] CorDebugRegister   highWordReg,  
    [in] CorDebugRegister   lowWordReg,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="14c36-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="14c36-105">Parameters</span></span>  
 `highWordReg`  
 <span data-ttu-id="14c36-106">[in] Der Wert der "CorDebugRegister"-Enumeration, die angibt, die Registrierung, die das hohe Word des Werts enthält.</span><span class="sxs-lookup"><span data-stu-id="14c36-106">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the high word of the value.</span></span>  
  
 `lowWordReg`  
 <span data-ttu-id="14c36-107">[in] Der Wert der `CorDebugRegister` -Enumeration, die Register, enthält das niedrige Word des Werts angibt.</span><span class="sxs-lookup"><span data-stu-id="14c36-107">[in] A value of the `CorDebugRegister` enumeration that specifies the register containing the low word of the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="14c36-108">[in] Eine ganze Zahl, die die Größe der binäre Metadatensignatur gibt an, welche die verweist die `pvSigBlob` Parameter.</span><span class="sxs-lookup"><span data-stu-id="14c36-108">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="14c36-109">[in] Ein `PCCOR_SIGNATURE` Wert, der auf die binäre Metadatensignatur der Typ des Werts verweist.</span><span class="sxs-lookup"><span data-stu-id="14c36-109">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="14c36-110">[out] Ein Zeiger auf die Adresse eines Objekts "ICorDebugValue", der den abgerufenen Wert, der in der angegebenen Register gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="14c36-110">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified registers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="14c36-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="14c36-111">Remarks</span></span>  
 <span data-ttu-id="14c36-112">Die `GetLocalDoubleRegisterValue` Methode kann verwendet werden, entweder in einem systemeigenen Rahmen oder eine just-in-Time (JIT)-Frame kompiliert.</span><span class="sxs-lookup"><span data-stu-id="14c36-112">The `GetLocalDoubleRegisterValue` method can be used either in a native frame or a just-in-time (JIT)-compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14c36-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="14c36-113">Requirements</span></span>  
 <span data-ttu-id="14c36-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14c36-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14c36-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="14c36-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="14c36-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="14c36-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="14c36-117">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14c36-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14c36-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="14c36-118">See Also</span></span>  
 
