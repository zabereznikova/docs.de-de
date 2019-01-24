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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6e8d0c16000c78fab0371b68c3a350bd2018aa1c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54664524"
---
# <a name="icordebugnativeframegetlocalmemoryvalue-method"></a><span data-ttu-id="f8043-102">ICorDebugNativeFrame::GetLocalMemoryValue-Methode</span><span class="sxs-lookup"><span data-stu-id="f8043-102">ICorDebugNativeFrame::GetLocalMemoryValue Method</span></span>
<span data-ttu-id="f8043-103">Ruft den Wert eines Arguments oder einer lokalen Variablen, die in der angegebenen Speicheradresse für diesen Frame native gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="f8043-103">Gets the value of an argument or local variable that is stored in the specified memory location for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8043-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f8043-104">Syntax</span></span>  
  
```  
HRESULT GetLocalMemoryValue (  
    [in]  CORDB_ADDRESS      address,  
    [in]  ULONG              cbSigBlob,  
    [in]  PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f8043-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f8043-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="f8043-106">[in] Ein `CORDB_ADDRESS` Wert, der angibt, die den Wert der Speicheradresse.</span><span class="sxs-lookup"><span data-stu-id="f8043-106">[in] A `CORDB_ADDRESS` value that specifies the memory location containing the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="f8043-107">[in] Eine ganze Zahl, die die Größe der die binäre Metadatensignatur gibt an, welche die verweist die `pvSigBlob` Parameter.</span><span class="sxs-lookup"><span data-stu-id="f8043-107">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="f8043-108">[in] Ein `PCCOR_SIGNATURE` Wert, der auf die binäre Metadatensignatur der der Typ des Werts verweist.</span><span class="sxs-lookup"><span data-stu-id="f8043-108">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="f8043-109">[out] Ein Zeiger auf die Adresse eines "ICorDebugValue"-Objekts, die den abgerufenen Wert, der in der angegebenen Speicheradresse gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="f8043-109">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified memory location.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8043-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f8043-110">Requirements</span></span>  
 <span data-ttu-id="f8043-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8043-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8043-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f8043-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f8043-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f8043-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f8043-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8043-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8043-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f8043-115">See also</span></span>

