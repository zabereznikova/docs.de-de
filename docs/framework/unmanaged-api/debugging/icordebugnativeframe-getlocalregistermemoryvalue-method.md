---
title: ICorDebugNativeFrame::GetLocalRegisterMemoryValue-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugNativeFrame.GetLocalRegisterMemoryValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugNativeFrame::GetLocalRegisterMemoryValue
helpviewer_keywords:
- ICorDebugNativeFrame::GetLocalRegisterMemoryValue method [.NET Framework debugging]
- GetLocalRegisterMemoryValue method [.NET Framework debugging]
ms.assetid: d350f69d-9aff-4f5a-8301-daea22dee2da
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 47520e6ab4c8c3bba7383ddd08b7ff23be9dddc3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugnativeframegetlocalregistermemoryvalue-method"></a><span data-ttu-id="f047a-102">ICorDebugNativeFrame::GetLocalRegisterMemoryValue-Methode</span><span class="sxs-lookup"><span data-stu-id="f047a-102">ICorDebugNativeFrame::GetLocalRegisterMemoryValue Method</span></span>
<span data-ttu-id="f047a-103">Ruft den Wert eines Arguments oder einer lokalen Variablen, von denen die niedrige Word und hohe Word werden in der Speicheradresse gespeichert und Register bzw. für diese systemeigene Rahmen angegeben.</span><span class="sxs-lookup"><span data-stu-id="f047a-103">Gets the value of an argument or local variable, of which the low word and high word are stored in the memory location and specified register, respectively, for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f047a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f047a-104">Syntax</span></span>  
  
```  
HRESULT GetLocalRegisterMemoryValue (  
    [in] CorDebugRegister   highWordReg,  
    [in] CORDB_ADDRESS      lowWordAddress,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f047a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f047a-105">Parameters</span></span>  
 `highWordReg`  
 <span data-ttu-id="f047a-106">[in] Der Wert der "CorDebugRegister"-Enumeration, die angibt, die Registrierung, die das hohe Word des Werts enthält.</span><span class="sxs-lookup"><span data-stu-id="f047a-106">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the high word of the value.</span></span>  
  
 `lowWordAddress`  
 <span data-ttu-id="f047a-107">[in] Ein `CORDB_ADDRESS` Wert, der angibt, die Speicheradresse, die das niedrige Word des Werts enthält.</span><span class="sxs-lookup"><span data-stu-id="f047a-107">[in] A `CORDB_ADDRESS` value that specifies the memory location containing the low word of the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="f047a-108">[in] Eine ganze Zahl, die die Größe der binäre Metadatensignatur gibt an, welche die verweist die `pvSigBlob` Parameter.</span><span class="sxs-lookup"><span data-stu-id="f047a-108">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="f047a-109">[in] Ein `PCCOR_SIGNATURE` Wert, der auf die binäre Metadatensignatur der Typ des Werts verweist.</span><span class="sxs-lookup"><span data-stu-id="f047a-109">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="f047a-110">[out] Ein Zeiger auf die Adresse eines Objekts "ICorDebugValue", die den abgerufenen Wert, der in der angegebenen Register und den angegebenen Speicherort gespeichert ist darstellt.</span><span class="sxs-lookup"><span data-stu-id="f047a-110">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified register and memory location.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f047a-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f047a-111">Requirements</span></span>  
 <span data-ttu-id="f047a-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f047a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f047a-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f047a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f047a-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f047a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f047a-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f047a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f047a-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f047a-116">See Also</span></span>  
 
