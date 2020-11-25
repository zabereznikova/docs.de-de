---
title: ICorDebugNativeFrame::GetLocalRegisterMemoryValue-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalRegisterMemoryValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalRegisterMemoryValue
helpviewer_keywords:
- ICorDebugNativeFrame::GetLocalRegisterMemoryValue method [.NET Framework debugging]
- GetLocalRegisterMemoryValue method [.NET Framework debugging]
ms.assetid: d350f69d-9aff-4f5a-8301-daea22dee2da
topic_type:
- apiref
ms.openlocfilehash: 4b77ad2f31f10bd14ce7d8242a584da737428344
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709302"
---
# <a name="icordebugnativeframegetlocalregistermemoryvalue-method"></a><span data-ttu-id="b0bf0-102">ICorDebugNativeFrame::GetLocalRegisterMemoryValue-Methode</span><span class="sxs-lookup"><span data-stu-id="b0bf0-102">ICorDebugNativeFrame::GetLocalRegisterMemoryValue Method</span></span>

<span data-ttu-id="b0bf0-103">Ruft den Wert eines Arguments oder einer lokalen Variablen ab, von dem das niedrige Wort und das große Wort im Speicher Speicherort gespeichert sind, bzw. das angegebene Register für diesen systemeigenen Frame.</span><span class="sxs-lookup"><span data-stu-id="b0bf0-103">Gets the value of an argument or local variable, of which the low word and high word are stored in the memory location and specified register, respectively, for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0bf0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b0bf0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalRegisterMemoryValue (  
    [in] CorDebugRegister   highWordReg,  
    [in] CORDB_ADDRESS      lowWordAddress,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b0bf0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b0bf0-105">Parameters</span></span>  

 `highWordReg`  
 <span data-ttu-id="b0bf0-106">in Ein Wert der CorDebugRegister-Enumeration, der das Register angibt, das das höchst Wort des Werts enthält.</span><span class="sxs-lookup"><span data-stu-id="b0bf0-106">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the high word of the value.</span></span>  
  
 `lowWordAddress`  
 <span data-ttu-id="b0bf0-107">in Ein- `CORDB_ADDRESS` Wert, der den Speicherort angibt, der das niedrige Wort des Werts enthält.</span><span class="sxs-lookup"><span data-stu-id="b0bf0-107">[in] A `CORDB_ADDRESS` value that specifies the memory location containing the low word of the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="b0bf0-108">in Eine ganze Zahl, die die Größe der binären Metadatensignatur angibt, auf die vom-Parameter verwiesen wird `pvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="b0bf0-108">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="b0bf0-109">in Ein- `PCCOR_SIGNATURE` Wert, der auf die binäre Metadatensignatur des Werttyps zeigt.</span><span class="sxs-lookup"><span data-stu-id="b0bf0-109">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="b0bf0-110">vorgenommen Ein Zeiger auf die Adresse eines ICorDebugValue-Objekts, das den abgerufenen Wert darstellt, der im angegebenen Registrierungs-und Speicher Speicherort gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="b0bf0-110">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified register and memory location.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0bf0-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b0bf0-111">Requirements</span></span>  

 <span data-ttu-id="b0bf0-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0bf0-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0bf0-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b0bf0-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b0bf0-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b0bf0-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b0bf0-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0bf0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0bf0-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b0bf0-116">See also</span></span>
