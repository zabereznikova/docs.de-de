---
title: ICorDebugNativeFrame::GetLocalDoubleRegisterValue-Methode
ms.date: 03/30/2017
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
ms.openlocfilehash: 10f06fb04099ef947711bc7c5641e5a7f1fa36b7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695698"
---
# <a name="icordebugnativeframegetlocaldoubleregistervalue-method"></a><span data-ttu-id="ff7cf-102">ICorDebugNativeFrame::GetLocalDoubleRegisterValue-Methode</span><span class="sxs-lookup"><span data-stu-id="ff7cf-102">ICorDebugNativeFrame::GetLocalDoubleRegisterValue Method</span></span>

<span data-ttu-id="ff7cf-103">Ruft den Wert eines Arguments oder einer lokalen Variablen ab, das in den beiden angegebenen Registern für diesen systemeigenen Frame gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="ff7cf-103">Gets the value of an argument or local variable that is stored in the two specified registers for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff7cf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ff7cf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalDoubleRegisterValue (  
    [in] CorDebugRegister   highWordReg,  
    [in] CorDebugRegister   lowWordReg,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ff7cf-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ff7cf-105">Parameters</span></span>  

 `highWordReg`  
 <span data-ttu-id="ff7cf-106">in Ein Wert der CorDebugRegister-Enumeration, der das Register angibt, das das höchst Wort des Werts enthält.</span><span class="sxs-lookup"><span data-stu-id="ff7cf-106">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the high word of the value.</span></span>  
  
 `lowWordReg`  
 <span data-ttu-id="ff7cf-107">in Ein Wert der- `CorDebugRegister` Enumeration, der das Register mit dem unteren Wort des Werts angibt.</span><span class="sxs-lookup"><span data-stu-id="ff7cf-107">[in] A value of the `CorDebugRegister` enumeration that specifies the register containing the low word of the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="ff7cf-108">in Eine ganze Zahl, die die Größe der binären Metadatensignatur angibt, auf die vom-Parameter verwiesen wird `pvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="ff7cf-108">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="ff7cf-109">in Ein- `PCCOR_SIGNATURE` Wert, der auf die binäre Metadatensignatur des Werttyps zeigt.</span><span class="sxs-lookup"><span data-stu-id="ff7cf-109">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="ff7cf-110">vorgenommen Ein Zeiger auf die Adresse eines icorentbugvalue-Objekts, das den abgerufenen Wert darstellt, der in den angegebenen Registern gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="ff7cf-110">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified registers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ff7cf-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ff7cf-111">Remarks</span></span>  

 <span data-ttu-id="ff7cf-112">Die `GetLocalDoubleRegisterValue` -Methode kann entweder in einem nativen Frame oder einem JIT-kompilierten Frame (Just-in-Time) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ff7cf-112">The `GetLocalDoubleRegisterValue` method can be used either in a native frame or a just-in-time (JIT)-compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff7cf-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ff7cf-113">Requirements</span></span>  

 <span data-ttu-id="ff7cf-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff7cf-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff7cf-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ff7cf-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ff7cf-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ff7cf-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ff7cf-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff7cf-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff7cf-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ff7cf-118">See also</span></span>
