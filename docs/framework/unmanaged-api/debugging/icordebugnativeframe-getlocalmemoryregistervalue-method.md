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
ms.openlocfilehash: 15485ac94ed9074baacc4fd2662a04bdcefcf1e7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709322"
---
# <a name="icordebugnativeframegetlocalmemoryregistervalue-method"></a><span data-ttu-id="13e23-102">ICorDebugNativeFrame::GetLocalMemoryRegisterValue-Methode</span><span class="sxs-lookup"><span data-stu-id="13e23-102">ICorDebugNativeFrame::GetLocalMemoryRegisterValue Method</span></span>

<span data-ttu-id="13e23-103">Ruft den Wert eines Arguments oder einer lokalen Variablen ab, von dem das niedrige Wort und das große Wort für diesen systemeigenen Frame im angegebenen Registrierungs-bzw. Speicher Speicherort gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="13e23-103">Gets the value of an argument or local variable, of which the low word and high word are stored in the specified register and memory location, respectively, for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13e23-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="13e23-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalMemoryRegisterValue (  
    [in] CORDB_ADDRESS      highWordAddress,  
    [in] CorDebugRegister   lowWordRegister,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="13e23-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="13e23-105">Parameters</span></span>  

 `highWordAddress`  
 <span data-ttu-id="13e23-106">in Ein- `CORDB_ADDRESS` Wert, der den Speicherort angibt, der das hohe Wort des Werts enthält.</span><span class="sxs-lookup"><span data-stu-id="13e23-106">[in] A `CORDB_ADDRESS` value that specifies the memory location containing the high word of the value.</span></span>  
  
 `lowWordRegister`  
 <span data-ttu-id="13e23-107">in Ein Wert der CorDebugRegister-Enumeration, der das Register angibt, das das niedrige Wort des Werts enthält.</span><span class="sxs-lookup"><span data-stu-id="13e23-107">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the low word of the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="13e23-108">in Eine ganze Zahl, die die Größe der binären Metadatensignatur angibt, auf die vom-Parameter verwiesen wird `pvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="13e23-108">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="13e23-109">in Ein- `PCCOR_SIGNATURE` Wert, der auf die binäre Metadatensignatur des Werttyps zeigt.</span><span class="sxs-lookup"><span data-stu-id="13e23-109">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="13e23-110">vorgenommen Ein Zeiger auf die Adresse eines ICorDebugValue-Objekts, das den abgerufenen Wert darstellt, der im angegebenen Registrierungs-und Speicher Speicherort gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="13e23-110">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified register and memory location.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13e23-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="13e23-111">Requirements</span></span>  

 <span data-ttu-id="13e23-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13e23-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13e23-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="13e23-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="13e23-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="13e23-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="13e23-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13e23-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13e23-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="13e23-116">See also</span></span>
