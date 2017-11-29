---
title: ICLRDataTarget::GetTLSValue-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataTarget.GetTLSValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataTarget::GetTLSValue
helpviewer_keywords:
- GetTLSValue method [.NET Framework debugging]
- ICLRDataTarget::GetTLSValue method [.NET Framework debugging]
ms.assetid: 0d8a7730-edc9-4728-898f-41b219cf5a28
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a820ec7c0a00306266be432a8aceacb3d30d1b4f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="iclrdatatargetgettlsvalue-method"></a><span data-ttu-id="e3c79-102">ICLRDataTarget::GetTLSValue-Methode</span><span class="sxs-lookup"><span data-stu-id="e3c79-102">ICLRDataTarget::GetTLSValue Method</span></span>
<span data-ttu-id="e3c79-103">Ruft einen Wert aus dem lokalen Threadspeicher (TLS) des angegebenen Threads im Zielprozess.</span><span class="sxs-lookup"><span data-stu-id="e3c79-103">Gets a value from the thread local storage (TLS) of the specified thread in the target process.</span></span> <span data-ttu-id="e3c79-104">Diese Methode wird von den Datenzugriffsdiensten der common Language Runtime (CLR) aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="e3c79-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3c79-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e3c79-105">Syntax</span></span>  
  
```  
HRESULT GetTLSValue (  
    [in] ULONG32            threadID,  
    [in] ULONG32            index,  
    [out] CLRDATA_ADDRESS   *value  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e3c79-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="e3c79-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="e3c79-107">[in] Der Betriebssystem-Bezeichner eines Threads im Zielprozess.</span><span class="sxs-lookup"><span data-stu-id="e3c79-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `index`  
 <span data-ttu-id="e3c79-108">[in] Der Index der Position.</span><span class="sxs-lookup"><span data-stu-id="e3c79-108">[in] The index of the location.</span></span> <span data-ttu-id="e3c79-109">Dieser Wert muss ein gültiger Index in den lokalen Speicher des angegebenen Threads.</span><span class="sxs-lookup"><span data-stu-id="e3c79-109">This value must be a valid index in the local store of the specified thread.</span></span>  
  
 `value`  
 <span data-ttu-id="e3c79-110">[out] Ein Zeiger auf eine `CLRDATA_ADDRESS` -Wert, der den Wert angibt, aus dem angegebenen TLS-Speicherort zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e3c79-110">[out] A pointer to a `CLRDATA_ADDRESS` value that specifies the value returned from the given TLS location.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e3c79-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e3c79-111">Remarks</span></span>  
 <span data-ttu-id="e3c79-112">Diese Methode wird vom Writer der Debuganwendung implementiert.</span><span class="sxs-lookup"><span data-stu-id="e3c79-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3c79-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e3c79-113">Requirements</span></span>  
 <span data-ttu-id="e3c79-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e3c79-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3c79-115">**Header:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="e3c79-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="e3c79-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e3c79-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e3c79-117">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3c79-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3c79-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e3c79-118">See Also</span></span>  
 [<span data-ttu-id="e3c79-119">ICLRDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e3c79-119">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
