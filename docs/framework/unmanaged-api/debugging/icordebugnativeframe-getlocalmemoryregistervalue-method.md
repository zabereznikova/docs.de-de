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
ms.openlocfilehash: 9b2244ec1be6fc0e5e19fac5adc7ecb38d68a0af
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59081136"
---
# <a name="icordebugnativeframegetlocalmemoryregistervalue-method"></a><span data-ttu-id="1cc49-102">ICorDebugNativeFrame::GetLocalMemoryRegisterValue-Methode</span><span class="sxs-lookup"><span data-stu-id="1cc49-102">ICorDebugNativeFrame::GetLocalMemoryRegisterValue Method</span></span>
<span data-ttu-id="1cc49-103">Ruft den Wert eines Arguments oder lokale Variable, von denen das niedrige Word und das hohe Word in der angegebenen Register und den Speicherort, für diesen Frame native gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="1cc49-103">Gets the value of an argument or local variable, of which the low word and high word are stored in the specified register and memory location, respectively, for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1cc49-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1cc49-104">Syntax</span></span>  
  
```  
HRESULT GetLocalMemoryRegisterValue (  
    [in] CORDB_ADDRESS      highWordAddress,  
    [in] CorDebugRegister   lowWordRegister,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1cc49-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1cc49-105">Parameters</span></span>  
 `highWordAddress`  
 <span data-ttu-id="1cc49-106">[in] Ein `CORDB_ADDRESS` -Wert, die Speicheradresse aus, das hohe Word des Werts angibt.</span><span class="sxs-lookup"><span data-stu-id="1cc49-106">[in] A `CORDB_ADDRESS` value that specifies the memory location containing the high word of the value.</span></span>  
  
 `lowWordRegister`  
 <span data-ttu-id="1cc49-107">[in] Der Wert der "CorDebugRegister"-Enumeration, die angibt, die Registrierung, die das niedrige Word des Werts enthält.</span><span class="sxs-lookup"><span data-stu-id="1cc49-107">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the low word of the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="1cc49-108">[in] Eine ganze Zahl, die die Größe der die binäre Metadatensignatur gibt an, welche die verweist die `pvSigBlob` Parameter.</span><span class="sxs-lookup"><span data-stu-id="1cc49-108">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="1cc49-109">[in] Ein `PCCOR_SIGNATURE` Wert, der auf die binäre Metadatensignatur der der Typ des Werts verweist.</span><span class="sxs-lookup"><span data-stu-id="1cc49-109">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="1cc49-110">[out] Ein Zeiger auf die Adresse eines "ICorDebugValue"-Objekts, die den abgerufenen Wert, der in der angegebenen registrieren und den angegebenen Speicherort gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="1cc49-110">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified register and memory location.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1cc49-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1cc49-111">Requirements</span></span>  
 <span data-ttu-id="1cc49-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1cc49-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1cc49-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1cc49-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1cc49-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1cc49-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="1cc49-115">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="1cc49-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1cc49-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1cc49-116">See also</span></span>
