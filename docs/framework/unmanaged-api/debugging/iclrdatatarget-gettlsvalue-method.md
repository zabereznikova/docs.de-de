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
ms.openlocfilehash: 9fbea1350c7749f67b7e0cc62378a8a520923ae8
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57502326"
---
# <a name="iclrdatatargetgettlsvalue-method"></a><span data-ttu-id="d4bd6-102">ICLRDataTarget::GetTLSValue-Methode</span><span class="sxs-lookup"><span data-stu-id="d4bd6-102">ICLRDataTarget::GetTLSValue Method</span></span>
<span data-ttu-id="d4bd6-103">Ruft einen Wert aus dem lokalen Threadspeicher (TLS), der den angegebenen Thread im Zielprozess.</span><span class="sxs-lookup"><span data-stu-id="d4bd6-103">Gets a value from the thread local storage (TLS) of the specified thread in the target process.</span></span> <span data-ttu-id="d4bd6-104">Diese Methode wird von den Datenzugriffsdiensten der common Language Runtime (CLR) aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="d4bd6-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4bd6-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="d4bd6-105">Syntax</span></span>  
  
```  
HRESULT GetTLSValue (  
    [in] ULONG32            threadID,  
    [in] ULONG32            index,  
    [out] CLRDATA_ADDRESS   *value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4bd6-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="d4bd6-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="d4bd6-107">[in] Der Betriebssystem-Bezeichner eines Threads im Zielprozess.</span><span class="sxs-lookup"><span data-stu-id="d4bd6-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `index`  
 <span data-ttu-id="d4bd6-108">[in] Der Index der Position.</span><span class="sxs-lookup"><span data-stu-id="d4bd6-108">[in] The index of the location.</span></span> <span data-ttu-id="d4bd6-109">Dieser Wert muss ein gültiger Index im lokalen Speicher des angegebenen Threads sein.</span><span class="sxs-lookup"><span data-stu-id="d4bd6-109">This value must be a valid index in the local store of the specified thread.</span></span>  
  
 `value`  
 <span data-ttu-id="d4bd6-110">[out] Ein Zeiger auf eine `CLRDATA_ADDRESS` Wert zurückgegeben, der den Wert angibt, aus dem angegebenen TLS-Speicherort.</span><span class="sxs-lookup"><span data-stu-id="d4bd6-110">[out] A pointer to a `CLRDATA_ADDRESS` value that specifies the value returned from the given TLS location.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4bd6-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d4bd6-111">Remarks</span></span>  
 <span data-ttu-id="d4bd6-112">Diese Methode wird vom Writer der Debuganwendung implementiert.</span><span class="sxs-lookup"><span data-stu-id="d4bd6-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4bd6-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d4bd6-113">Requirements</span></span>  
 <span data-ttu-id="d4bd6-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4bd6-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4bd6-115">**Header:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="d4bd6-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="d4bd6-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d4bd6-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d4bd6-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4bd6-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4bd6-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d4bd6-118">See also</span></span>
- [<span data-ttu-id="d4bd6-119">ICLRDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d4bd6-119">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
