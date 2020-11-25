---
title: ICorDebugNativeFrame::GetLocalMemoryValue-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetLocalMemoryValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalMemoryValue
helpviewer_keywords:
- GetLocalMemoryValue method [.NET Framework debugging]
- ICorDebugNativeFrame::GetLocalMemoryValue method [.NET Framework debugging]
ms.assetid: b600b3a2-9908-42d8-8093-ab6f39e9a2c9
topic_type:
- apiref
ms.openlocfilehash: 92a4ee2007760024b5802208d77ca3abc81e3cf3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695672"
---
# <a name="icordebugnativeframegetlocalmemoryvalue-method"></a><span data-ttu-id="de401-102">ICorDebugNativeFrame::GetLocalMemoryValue-Methode</span><span class="sxs-lookup"><span data-stu-id="de401-102">ICorDebugNativeFrame::GetLocalMemoryValue Method</span></span>

<span data-ttu-id="de401-103">Ruft den Wert eines Arguments oder einer lokalen Variablen ab, das an der angegebenen Speicheradresse für diesen systemeigenen Frame gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="de401-103">Gets the value of an argument or local variable that is stored in the specified memory location for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de401-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="de401-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalMemoryValue (  
    [in]  CORDB_ADDRESS      address,  
    [in]  ULONG              cbSigBlob,  
    [in]  PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="de401-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="de401-105">Parameters</span></span>  

 `address`  
 <span data-ttu-id="de401-106">in Ein- `CORDB_ADDRESS` Wert, der den Speicherort angibt, der den Wert enthält.</span><span class="sxs-lookup"><span data-stu-id="de401-106">[in] A `CORDB_ADDRESS` value that specifies the memory location containing the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="de401-107">in Eine ganze Zahl, die die Größe der binären Metadatensignatur angibt, auf die vom-Parameter verwiesen wird `pvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="de401-107">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="de401-108">in Ein- `PCCOR_SIGNATURE` Wert, der auf die binäre Metadatensignatur des Werttyps zeigt.</span><span class="sxs-lookup"><span data-stu-id="de401-108">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="de401-109">vorgenommen Ein Zeiger auf die Adresse eines ICorDebugValue-Objekts, das den abgerufenen Wert darstellt, der an der angegebenen Speicheradresse gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="de401-109">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified memory location.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de401-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="de401-110">Requirements</span></span>  

 <span data-ttu-id="de401-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de401-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de401-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="de401-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="de401-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="de401-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="de401-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de401-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de401-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="de401-115">See also</span></span>
