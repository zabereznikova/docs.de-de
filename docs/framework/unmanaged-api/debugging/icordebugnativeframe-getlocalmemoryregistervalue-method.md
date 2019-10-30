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
ms.openlocfilehash: 788ce2d47769caa72518e0357a0affdff5862699
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137283"
---
# <a name="icordebugnativeframegetlocalmemoryregistervalue-method"></a><span data-ttu-id="6273e-102">ICorDebugNativeFrame::GetLocalMemoryRegisterValue-Methode</span><span class="sxs-lookup"><span data-stu-id="6273e-102">ICorDebugNativeFrame::GetLocalMemoryRegisterValue Method</span></span>
<span data-ttu-id="6273e-103">Ruft den Wert eines Arguments oder einer lokalen Variablen ab, von dem das niedrige Wort und das große Wort für diesen systemeigenen Frame im angegebenen Registrierungs-bzw. Speicher Speicherort gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="6273e-103">Gets the value of an argument or local variable, of which the low word and high word are stored in the specified register and memory location, respectively, for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6273e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6273e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalMemoryRegisterValue (  
    [in] CORDB_ADDRESS      highWordAddress,  
    [in] CorDebugRegister   lowWordRegister,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6273e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6273e-105">Parameters</span></span>  
 `highWordAddress`  
 <span data-ttu-id="6273e-106">in Ein `CORDB_ADDRESS` Wert, der den Speicherbereich angibt, der das hohe Wort des Werts enthält.</span><span class="sxs-lookup"><span data-stu-id="6273e-106">[in] A `CORDB_ADDRESS` value that specifies the memory location containing the high word of the value.</span></span>  
  
 `lowWordRegister`  
 <span data-ttu-id="6273e-107">in Ein Wert der CorDebugRegister-Enumeration, der das Register angibt, das das niedrige Wort des Werts enthält.</span><span class="sxs-lookup"><span data-stu-id="6273e-107">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the low word of the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="6273e-108">in Eine ganze Zahl, die die Größe der binären Metadatensignatur angibt, auf die vom `pvSigBlob`-Parameter verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="6273e-108">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="6273e-109">in Ein `PCCOR_SIGNATURE` Wert, der auf die binäre Metadatensignatur des Werttyps zeigt.</span><span class="sxs-lookup"><span data-stu-id="6273e-109">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="6273e-110">vorgenommen Ein Zeiger auf die Adresse eines ICorDebugValue-Objekts, das den abgerufenen Wert darstellt, der im angegebenen Registrierungs-und Speicher Speicherort gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="6273e-110">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified register and memory location.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6273e-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6273e-111">Requirements</span></span>  
 <span data-ttu-id="6273e-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6273e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6273e-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6273e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6273e-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6273e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6273e-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6273e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6273e-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6273e-116">See also</span></span>
