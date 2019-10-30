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
ms.openlocfilehash: 132e0868426670ba61d8ee12ba7007be1a8a52de
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139399"
---
# <a name="icordebugnativeframegetlocalregistervalue-method"></a><span data-ttu-id="987d0-102">ICorDebugNativeFrame::GetLocalRegisterValue-Methode</span><span class="sxs-lookup"><span data-stu-id="987d0-102">ICorDebugNativeFrame::GetLocalRegisterValue Method</span></span>
<span data-ttu-id="987d0-103">Ruft den Wert eines Arguments oder einer lokalen Variablen ab, das im angegebenen Register für diesen systemeigenen Frame gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="987d0-103">Gets the value of an argument or local variable that is stored in the specified register for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="987d0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="987d0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalRegisterValue (  
    [in]  CorDebugRegister   reg,  
    [in]  ULONG              cbSigBlob,  
    [in]  PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="987d0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="987d0-105">Parameters</span></span>  
 `reg`  
 <span data-ttu-id="987d0-106">in Ein Wert der CorDebugRegister-Enumeration, der das Register angibt, das den Wert enthält.</span><span class="sxs-lookup"><span data-stu-id="987d0-106">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="987d0-107">in Eine ganze Zahl, die die Größe der binären Metadatensignatur angibt, auf die vom `pvSigBlob`-Parameter verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="987d0-107">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="987d0-108">in Ein `PCCOR_SIGNATURE` Wert, der auf die binäre Metadatensignatur des Werttyps zeigt.</span><span class="sxs-lookup"><span data-stu-id="987d0-108">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="987d0-109">vorgenommen Ein Zeiger auf die Adresse eines ICorDebugValue-Objekts, das den abgerufenen Wert darstellt, der im angegebenen Register gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="987d0-109">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="987d0-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="987d0-110">Remarks</span></span>  
 <span data-ttu-id="987d0-111">Die `GetLocalRegisterValue`-Methode kann entweder in einem nativen Frame oder einem JIT-kompilierten Frame (Just-in-Time) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="987d0-111">The `GetLocalRegisterValue` method can be used either in a native frame or a just-in-time (JIT)-compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="987d0-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="987d0-112">Requirements</span></span>  
 <span data-ttu-id="987d0-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="987d0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="987d0-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="987d0-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="987d0-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="987d0-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="987d0-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="987d0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="987d0-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="987d0-117">See also</span></span>
