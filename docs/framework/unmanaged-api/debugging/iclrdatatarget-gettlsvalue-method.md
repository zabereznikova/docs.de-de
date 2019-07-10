---
title: ICLRDataTarget::GetTLSValue-Methode
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetTLSValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetTLSValue
helpviewer_keywords:
- GetTLSValue method [.NET Framework debugging]
- ICLRDataTarget::GetTLSValue method [.NET Framework debugging]
ms.assetid: 0d8a7730-edc9-4728-898f-41b219cf5a28
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7de415b998ef97e7500c289a1bca4402d203b152
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738694"
---
# <a name="iclrdatatargetgettlsvalue-method"></a><span data-ttu-id="b995d-102">ICLRDataTarget::GetTLSValue-Methode</span><span class="sxs-lookup"><span data-stu-id="b995d-102">ICLRDataTarget::GetTLSValue Method</span></span>
<span data-ttu-id="b995d-103">Ruft einen Wert aus dem lokalen Threadspeicher (TLS), der den angegebenen Thread im Zielprozess.</span><span class="sxs-lookup"><span data-stu-id="b995d-103">Gets a value from the thread local storage (TLS) of the specified thread in the target process.</span></span> <span data-ttu-id="b995d-104">Diese Methode wird von den Datenzugriffsdiensten der common Language Runtime (CLR) aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="b995d-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b995d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b995d-105">Syntax</span></span>  
  
```cpp  
HRESULT GetTLSValue (  
    [in] ULONG32            threadID,  
    [in] ULONG32            index,  
    [out] CLRDATA_ADDRESS   *value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b995d-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="b995d-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="b995d-107">[in] Der Betriebssystem-Bezeichner eines Threads im Zielprozess.</span><span class="sxs-lookup"><span data-stu-id="b995d-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `index`  
 <span data-ttu-id="b995d-108">[in] Der Index der Position.</span><span class="sxs-lookup"><span data-stu-id="b995d-108">[in] The index of the location.</span></span> <span data-ttu-id="b995d-109">Dieser Wert muss ein gültiger Index im lokalen Speicher des angegebenen Threads sein.</span><span class="sxs-lookup"><span data-stu-id="b995d-109">This value must be a valid index in the local store of the specified thread.</span></span>  
  
 `value`  
 <span data-ttu-id="b995d-110">[out] Ein Zeiger auf eine `CLRDATA_ADDRESS` Wert zurückgegeben, der den Wert angibt, aus dem angegebenen TLS-Speicherort.</span><span class="sxs-lookup"><span data-stu-id="b995d-110">[out] A pointer to a `CLRDATA_ADDRESS` value that specifies the value returned from the given TLS location.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b995d-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b995d-111">Remarks</span></span>  
 <span data-ttu-id="b995d-112">Diese Methode wird vom Writer der Debuganwendung implementiert.</span><span class="sxs-lookup"><span data-stu-id="b995d-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b995d-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b995d-113">Requirements</span></span>  
 <span data-ttu-id="b995d-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b995d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b995d-115">**Header:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="b995d-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="b995d-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b995d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b995d-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b995d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b995d-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b995d-118">See also</span></span>

- [<span data-ttu-id="b995d-119">ICLRDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b995d-119">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
