---
title: ICorDebugNativeFrame::GetLocalMemoryRegisterValue-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalMemoryRegisterValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalMemoryRegisterValue
helpviewer_keywords:
- ICorDebugNativeFrame::GetLocalMemoryRegisterValue method [.NET Framework debugging]
- GetLocalMemoryRegisterValue method
ms.assetid: 33a19f6e-1029-4d53-af64-19591c6e58ee
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 44f220f12f72ca8d0be6a9fc50b363c9bccb85fd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugnativeframegetlocalmemoryregistervalue-method"></a><span data-ttu-id="22be9-102">ICorDebugNativeFrame::GetLocalMemoryRegisterValue-Methode</span><span class="sxs-lookup"><span data-stu-id="22be9-102">ICorDebugNativeFrame::GetLocalMemoryRegisterValue Method</span></span>
<span data-ttu-id="22be9-103">Ruft den Wert eines Arguments oder einer lokalen Variablen, von denen die niedrige Word und hohe Word in den angegebenen Register und die Speicheradresse, bzw. für diese systemeigenen Rahmen gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="22be9-103">Gets the value of an argument or local variable, of which the low word and high word are stored in the specified register and memory location, respectively, for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22be9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="22be9-104">Syntax</span></span>  
  
```  
HRESULT GetLocalMemoryRegisterValue (  
    [in] CORDB_ADDRESS      highWordAddress,  
    [in] CorDebugRegister   lowWordRegister,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="22be9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="22be9-105">Parameters</span></span>  
 `highWordAddress`  
 <span data-ttu-id="22be9-106">[in] Ein `CORDB_ADDRESS` Wert, der angibt, die Speicheradresse, die das hohe Word des Werts enthält.</span><span class="sxs-lookup"><span data-stu-id="22be9-106">[in] A `CORDB_ADDRESS` value that specifies the memory location containing the high word of the value.</span></span>  
  
 `lowWordRegister`  
 <span data-ttu-id="22be9-107">[in] Der Wert der "CorDebugRegister"-Enumeration, die angibt, die Registrierung, die das niedrige Word des Werts enthält.</span><span class="sxs-lookup"><span data-stu-id="22be9-107">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the low word of the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="22be9-108">[in] Eine ganze Zahl, die die Größe der binäre Metadatensignatur gibt an, welche die verweist die `pvSigBlob` Parameter.</span><span class="sxs-lookup"><span data-stu-id="22be9-108">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="22be9-109">[in] Ein `PCCOR_SIGNATURE` Wert, der auf die binäre Metadatensignatur der Typ des Werts verweist.</span><span class="sxs-lookup"><span data-stu-id="22be9-109">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="22be9-110">[out] Ein Zeiger auf die Adresse eines Objekts "ICorDebugValue", die den abgerufenen Wert, der in der angegebenen Register und den angegebenen Speicherort gespeichert ist darstellt.</span><span class="sxs-lookup"><span data-stu-id="22be9-110">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified register and memory location.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22be9-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="22be9-111">Requirements</span></span>  
 <span data-ttu-id="22be9-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22be9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22be9-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="22be9-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="22be9-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="22be9-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="22be9-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22be9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22be9-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="22be9-116">See Also</span></span>  
 
