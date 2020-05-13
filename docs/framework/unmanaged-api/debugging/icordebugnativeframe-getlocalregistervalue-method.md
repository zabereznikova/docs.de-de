---
title: ICorDebugNativeFrame::GetLocalRegisterValue-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalRegisterValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalRegisterValue
helpviewer_keywords:
- GetLocalRegisterValue method [.NET Framework debugging]
- ICorDebugNativeFrame::GetLocalRegisterValue method [.NET Framework debugging]
ms.assetid: 5ccb74f3-f891-430c-b70a-e370624edde2
topic_type:
- apiref
ms.openlocfilehash: 97d79f70097bef7768316907887cea2c38dd81e1
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212827"
---
# <a name="icordebugnativeframegetlocalregistervalue-method"></a><span data-ttu-id="e9c33-102">ICorDebugNativeFrame::GetLocalRegisterValue-Methode</span><span class="sxs-lookup"><span data-stu-id="e9c33-102">ICorDebugNativeFrame::GetLocalRegisterValue Method</span></span>
<span data-ttu-id="e9c33-103">Ruft den Wert eines Arguments oder einer lokalen Variablen ab, das im angegebenen Register für diesen systemeigenen Frame gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="e9c33-103">Gets the value of an argument or local variable that is stored in the specified register for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9c33-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e9c33-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalRegisterValue (  
    [in]  CorDebugRegister   reg,  
    [in]  ULONG              cbSigBlob,  
    [in]  PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9c33-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e9c33-105">Parameters</span></span>  
 `reg`  
 <span data-ttu-id="e9c33-106">in Ein Wert der CorDebugRegister-Enumeration, der das Register angibt, das den Wert enthält.</span><span class="sxs-lookup"><span data-stu-id="e9c33-106">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="e9c33-107">in Eine ganze Zahl, die die Größe der binären Metadatensignatur angibt, auf die vom-Parameter verwiesen wird `pvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="e9c33-107">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="e9c33-108">in Ein- `PCCOR_SIGNATURE` Wert, der auf die binäre Metadatensignatur des Werttyps zeigt.</span><span class="sxs-lookup"><span data-stu-id="e9c33-108">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="e9c33-109">vorgenommen Ein Zeiger auf die Adresse eines ICorDebugValue-Objekts, das den abgerufenen Wert darstellt, der im angegebenen Register gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="e9c33-109">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9c33-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e9c33-110">Remarks</span></span>  
 <span data-ttu-id="e9c33-111">Die `GetLocalRegisterValue` -Methode kann entweder in einem nativen Frame oder einem JIT-kompilierten Frame (Just-in-Time) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e9c33-111">The `GetLocalRegisterValue` method can be used either in a native frame or a just-in-time (JIT)-compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9c33-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e9c33-112">Requirements</span></span>  
 <span data-ttu-id="e9c33-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9c33-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9c33-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e9c33-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e9c33-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e9c33-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e9c33-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9c33-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9c33-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e9c33-117">See also</span></span>
