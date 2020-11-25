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
ms.openlocfilehash: f6066774961b3fba2c466e156296907efc2e53df
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703407"
---
# <a name="iclrdatatargetgettlsvalue-method"></a><span data-ttu-id="230aa-102">ICLRDataTarget::GetTLSValue-Methode</span><span class="sxs-lookup"><span data-stu-id="230aa-102">ICLRDataTarget::GetTLSValue Method</span></span>

<span data-ttu-id="230aa-103">Ruft einen Wert aus dem lokalen Thread Speicher (TLS) des angegebenen Threads im Ziel Prozess ab.</span><span class="sxs-lookup"><span data-stu-id="230aa-103">Gets a value from the thread local storage (TLS) of the specified thread in the target process.</span></span> <span data-ttu-id="230aa-104">Diese Methode wird vom Common Language Runtime (CLR)-Datenzugriffs Dienst aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="230aa-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="230aa-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="230aa-105">Syntax</span></span>  
  
```cpp  
HRESULT GetTLSValue (  
    [in] ULONG32            threadID,  
    [in] ULONG32            index,  
    [out] CLRDATA_ADDRESS   *value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="230aa-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="230aa-106">Parameters</span></span>  

 `threadID`  
 <span data-ttu-id="230aa-107">in Der Betriebssystem Bezeichner eines Threads im Ziel Prozess.</span><span class="sxs-lookup"><span data-stu-id="230aa-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `index`  
 <span data-ttu-id="230aa-108">in Der Index des Speicher Orts.</span><span class="sxs-lookup"><span data-stu-id="230aa-108">[in] The index of the location.</span></span> <span data-ttu-id="230aa-109">Dieser Wert muss ein gültiger Index im lokalen Speicher des angegebenen Threads sein.</span><span class="sxs-lookup"><span data-stu-id="230aa-109">This value must be a valid index in the local store of the specified thread.</span></span>  
  
 `value`  
 <span data-ttu-id="230aa-110">vorgenommen Ein Zeiger auf einen- `CLRDATA_ADDRESS` Wert, der den Wert angibt, der vom angegebenen TLS-Speicherort zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="230aa-110">[out] A pointer to a `CLRDATA_ADDRESS` value that specifies the value returned from the given TLS location.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="230aa-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="230aa-111">Remarks</span></span>  

 <span data-ttu-id="230aa-112">Diese Methode wird vom Writer der Debuganwendung implementiert.</span><span class="sxs-lookup"><span data-stu-id="230aa-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="230aa-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="230aa-113">Requirements</span></span>  

 <span data-ttu-id="230aa-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="230aa-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="230aa-115">**Header:** Clrdata. idl, Clrdata. h</span><span class="sxs-lookup"><span data-stu-id="230aa-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="230aa-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="230aa-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="230aa-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="230aa-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="230aa-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="230aa-118">See also</span></span>

- [<span data-ttu-id="230aa-119">ICLRDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="230aa-119">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
