---
title: ICorDebugNativeFrame::GetLocalMemoryRegisterValue-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugNativeFrame.GetLocalMemoryRegisterValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugNativeFrame::GetLocalMemoryRegisterValue
helpviewer_keywords:
- ICorDebugNativeFrame::GetLocalMemoryRegisterValue method [.NET Framework debugging]
- GetLocalMemoryRegisterValue method
ms.assetid: 33a19f6e-1029-4d53-af64-19591c6e58ee
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5a1a2b845b3d09fd147937e39cf4e7bec8ee7c8f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugnativeframegetlocalmemoryregistervalue-method"></a><span data-ttu-id="7ab67-102">ICorDebugNativeFrame::GetLocalMemoryRegisterValue-Methode</span><span class="sxs-lookup"><span data-stu-id="7ab67-102">ICorDebugNativeFrame::GetLocalMemoryRegisterValue Method</span></span>
<span data-ttu-id="7ab67-103">Ruft den Wert eines Arguments oder einer lokalen Variablen, von denen die niedrige Word und hohe Word in den angegebenen Register und die Speicheradresse, bzw. für diese systemeigenen Rahmen gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="7ab67-103">Gets the value of an argument or local variable, of which the low word and high word are stored in the specified register and memory location, respectively, for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ab67-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7ab67-104">Syntax</span></span>  
  
```  
HRESULT GetLocalMemoryRegisterValue (  
    [in] CORDB_ADDRESS      highWordAddress,  
    [in] CorDebugRegister   lowWordRegister,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7ab67-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7ab67-105">Parameters</span></span>  
 `highWordAddress`  
 <span data-ttu-id="7ab67-106">[in] Ein `CORDB_ADDRESS` Wert, der angibt, die Speicheradresse, die das hohe Word des Werts enthält.</span><span class="sxs-lookup"><span data-stu-id="7ab67-106">[in] A `CORDB_ADDRESS` value that specifies the memory location containing the high word of the value.</span></span>  
  
 `lowWordRegister`  
 <span data-ttu-id="7ab67-107">[in] Der Wert der "CorDebugRegister"-Enumeration, die angibt, die Registrierung, die das niedrige Word des Werts enthält.</span><span class="sxs-lookup"><span data-stu-id="7ab67-107">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the low word of the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="7ab67-108">[in] Eine ganze Zahl, die die Größe der binäre Metadatensignatur gibt an, welche die verweist die `pvSigBlob` Parameter.</span><span class="sxs-lookup"><span data-stu-id="7ab67-108">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="7ab67-109">[in] Ein `PCCOR_SIGNATURE` Wert, der auf die binäre Metadatensignatur der Typ des Werts verweist.</span><span class="sxs-lookup"><span data-stu-id="7ab67-109">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="7ab67-110">[out] Ein Zeiger auf die Adresse eines Objekts "ICorDebugValue", die den abgerufenen Wert, der in der angegebenen Register und den angegebenen Speicherort gespeichert ist darstellt.</span><span class="sxs-lookup"><span data-stu-id="7ab67-110">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified register and memory location.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ab67-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7ab67-111">Requirements</span></span>  
 <span data-ttu-id="7ab67-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ab67-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ab67-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7ab67-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7ab67-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ab67-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7ab67-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ab67-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ab67-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7ab67-116">See Also</span></span>  
 
