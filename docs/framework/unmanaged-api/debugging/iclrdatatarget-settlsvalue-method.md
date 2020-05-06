---
title: ICLRDataTarget::SetTLSValue-Methode
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.SetTLSValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::SetTLSValue
helpviewer_keywords:
- ICLRDataTarget::SetTLSValue method [.NET Framework debugging]
- SetTLSValue method [.NET Framework debugging]
ms.assetid: 4a2d6a24-749a-47ad-9f01-4517203d3f35
topic_type:
- apiref
ms.openlocfilehash: 6c98fc93fd659ccfc0ccd42eec7d95382cf342f8
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860510"
---
# <a name="iclrdatatargetsettlsvalue-method"></a><span data-ttu-id="6860e-102">ICLRDataTarget::SetTLSValue-Methode</span><span class="sxs-lookup"><span data-stu-id="6860e-102">ICLRDataTarget::SetTLSValue Method</span></span>
<span data-ttu-id="6860e-103">Legt einen Wert im lokalen Thread Speicher (TLS) des angegebenen Threads im Ziel Prozess fest.</span><span class="sxs-lookup"><span data-stu-id="6860e-103">Sets a value in the thread local storage (TLS) of the specified thread in the target process.</span></span> <span data-ttu-id="6860e-104">Diese Methode wird vom Common Language Runtime (CLR)-Datenzugriffs Dienst aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="6860e-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6860e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="6860e-105">Syntax</span></span>  
  
```cpp  
HRESULT SetTLSValue (  
    [in] ULONG32            threadID,  
    [in] ULONG32            index,  
    [in] CLRDATA_ADDRESS    value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6860e-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="6860e-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="6860e-107">in Der Betriebssystem Bezeichner eines Threads im Ziel Prozess.</span><span class="sxs-lookup"><span data-stu-id="6860e-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `index`  
 <span data-ttu-id="6860e-108">in Der Index des Speicher Orts.</span><span class="sxs-lookup"><span data-stu-id="6860e-108">[in] The index of the location.</span></span> <span data-ttu-id="6860e-109">Dieser Wert muss ein gültiger Index im lokalen Speicher des angegebenen Threads sein.</span><span class="sxs-lookup"><span data-stu-id="6860e-109">This value must be a valid index in the local store of the specified thread.</span></span>  
  
 `value`  
 <span data-ttu-id="6860e-110">in Ein `CLRDATA_ADDRESS` -Wert, der den Wert angibt, der im angegebenen TLS-Speicherort platziert werden soll.</span><span class="sxs-lookup"><span data-stu-id="6860e-110">[in] A `CLRDATA_ADDRESS` value that specifies the value to place in the given TLS location.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6860e-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6860e-111">Remarks</span></span>  
 <span data-ttu-id="6860e-112">Diese Methode wird vom Writer der Debuganwendung implementiert.</span><span class="sxs-lookup"><span data-stu-id="6860e-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6860e-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6860e-113">Requirements</span></span>  
 <span data-ttu-id="6860e-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6860e-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6860e-115">**Header:** Clrdata. idl, Clrdata. h</span><span class="sxs-lookup"><span data-stu-id="6860e-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="6860e-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6860e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6860e-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6860e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6860e-118">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="6860e-118">See also</span></span>

- [<span data-ttu-id="6860e-119">ICLRDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6860e-119">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
