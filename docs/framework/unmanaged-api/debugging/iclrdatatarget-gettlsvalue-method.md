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
ms.openlocfilehash: 130ba2864537f017bd3037412d742d887df1ae68
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405726"
---
# <a name="iclrdatatargetgettlsvalue-method"></a><span data-ttu-id="8cabc-102">ICLRDataTarget::GetTLSValue-Methode</span><span class="sxs-lookup"><span data-stu-id="8cabc-102">ICLRDataTarget::GetTLSValue Method</span></span>
<span data-ttu-id="8cabc-103">Ruft einen Wert aus dem lokalen Threadspeicher (TLS) des angegebenen Threads im Zielprozess.</span><span class="sxs-lookup"><span data-stu-id="8cabc-103">Gets a value from the thread local storage (TLS) of the specified thread in the target process.</span></span> <span data-ttu-id="8cabc-104">Diese Methode wird von den Datenzugriffsdiensten der common Language Runtime (CLR) aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="8cabc-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8cabc-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="8cabc-105">Syntax</span></span>  
  
```  
HRESULT GetTLSValue (  
    [in] ULONG32            threadID,  
    [in] ULONG32            index,  
    [out] CLRDATA_ADDRESS   *value  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8cabc-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="8cabc-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="8cabc-107">[in] Der Betriebssystem-Bezeichner eines Threads im Zielprozess.</span><span class="sxs-lookup"><span data-stu-id="8cabc-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `index`  
 <span data-ttu-id="8cabc-108">[in] Der Index der Position.</span><span class="sxs-lookup"><span data-stu-id="8cabc-108">[in] The index of the location.</span></span> <span data-ttu-id="8cabc-109">Dieser Wert muss ein gültiger Index in den lokalen Speicher des angegebenen Threads.</span><span class="sxs-lookup"><span data-stu-id="8cabc-109">This value must be a valid index in the local store of the specified thread.</span></span>  
  
 `value`  
 <span data-ttu-id="8cabc-110">[out] Ein Zeiger auf eine `CLRDATA_ADDRESS` -Wert, der den Wert angibt, aus dem angegebenen TLS-Speicherort zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8cabc-110">[out] A pointer to a `CLRDATA_ADDRESS` value that specifies the value returned from the given TLS location.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8cabc-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8cabc-111">Remarks</span></span>  
 <span data-ttu-id="8cabc-112">Diese Methode wird vom Writer der Debuganwendung implementiert.</span><span class="sxs-lookup"><span data-stu-id="8cabc-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8cabc-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8cabc-113">Requirements</span></span>  
 <span data-ttu-id="8cabc-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8cabc-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8cabc-115">**Header:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="8cabc-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="8cabc-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8cabc-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8cabc-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8cabc-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cabc-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8cabc-118">See Also</span></span>  
 [<span data-ttu-id="8cabc-119">ICLRDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8cabc-119">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
