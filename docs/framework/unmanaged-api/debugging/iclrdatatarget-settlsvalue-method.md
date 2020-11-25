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
ms.openlocfilehash: d2eaab1f42eb04d8e9727220a08842ca75a2eadf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723687"
---
# <a name="iclrdatatargetsettlsvalue-method"></a><span data-ttu-id="0361f-102">ICLRDataTarget::SetTLSValue-Methode</span><span class="sxs-lookup"><span data-stu-id="0361f-102">ICLRDataTarget::SetTLSValue Method</span></span>

<span data-ttu-id="0361f-103">Legt einen Wert im lokalen Thread Speicher (TLS) des angegebenen Threads im Ziel Prozess fest.</span><span class="sxs-lookup"><span data-stu-id="0361f-103">Sets a value in the thread local storage (TLS) of the specified thread in the target process.</span></span> <span data-ttu-id="0361f-104">Diese Methode wird vom Common Language Runtime (CLR)-Datenzugriffs Dienst aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="0361f-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0361f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="0361f-105">Syntax</span></span>  
  
```cpp  
HRESULT SetTLSValue (  
    [in] ULONG32            threadID,  
    [in] ULONG32            index,  
    [in] CLRDATA_ADDRESS    value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0361f-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="0361f-106">Parameters</span></span>  

 `threadID`  
 <span data-ttu-id="0361f-107">in Der Betriebssystem Bezeichner eines Threads im Ziel Prozess.</span><span class="sxs-lookup"><span data-stu-id="0361f-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `index`  
 <span data-ttu-id="0361f-108">in Der Index des Speicher Orts.</span><span class="sxs-lookup"><span data-stu-id="0361f-108">[in] The index of the location.</span></span> <span data-ttu-id="0361f-109">Dieser Wert muss ein gültiger Index im lokalen Speicher des angegebenen Threads sein.</span><span class="sxs-lookup"><span data-stu-id="0361f-109">This value must be a valid index in the local store of the specified thread.</span></span>  
  
 `value`  
 <span data-ttu-id="0361f-110">in Ein- `CLRDATA_ADDRESS` Wert, der den Wert angibt, der im angegebenen TLS-Speicherort platziert werden soll.</span><span class="sxs-lookup"><span data-stu-id="0361f-110">[in] A `CLRDATA_ADDRESS` value that specifies the value to place in the given TLS location.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0361f-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0361f-111">Remarks</span></span>  

 <span data-ttu-id="0361f-112">Diese Methode wird vom Writer der Debuganwendung implementiert.</span><span class="sxs-lookup"><span data-stu-id="0361f-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0361f-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="0361f-113">Requirements</span></span>  

 <span data-ttu-id="0361f-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0361f-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0361f-115">**Header:** Clrdata. idl, Clrdata. h</span><span class="sxs-lookup"><span data-stu-id="0361f-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="0361f-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0361f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0361f-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0361f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0361f-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0361f-118">See also</span></span>

- [<span data-ttu-id="0361f-119">ICLRDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0361f-119">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
