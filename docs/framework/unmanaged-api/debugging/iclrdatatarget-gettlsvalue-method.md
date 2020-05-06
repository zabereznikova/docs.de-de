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
ms.openlocfilehash: 141dc8632812ab4a2ce82864cde56337025baa28
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860584"
---
# <a name="iclrdatatargetgettlsvalue-method"></a><span data-ttu-id="d5440-102">ICLRDataTarget::GetTLSValue-Methode</span><span class="sxs-lookup"><span data-stu-id="d5440-102">ICLRDataTarget::GetTLSValue Method</span></span>
<span data-ttu-id="d5440-103">Ruft einen Wert aus dem lokalen Thread Speicher (TLS) des angegebenen Threads im Ziel Prozess ab.</span><span class="sxs-lookup"><span data-stu-id="d5440-103">Gets a value from the thread local storage (TLS) of the specified thread in the target process.</span></span> <span data-ttu-id="d5440-104">Diese Methode wird vom Common Language Runtime (CLR)-Datenzugriffs Dienst aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="d5440-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5440-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="d5440-105">Syntax</span></span>  
  
```cpp  
HRESULT GetTLSValue (  
    [in] ULONG32            threadID,  
    [in] ULONG32            index,  
    [out] CLRDATA_ADDRESS   *value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d5440-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="d5440-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="d5440-107">in Der Betriebssystem Bezeichner eines Threads im Ziel Prozess.</span><span class="sxs-lookup"><span data-stu-id="d5440-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `index`  
 <span data-ttu-id="d5440-108">in Der Index des Speicher Orts.</span><span class="sxs-lookup"><span data-stu-id="d5440-108">[in] The index of the location.</span></span> <span data-ttu-id="d5440-109">Dieser Wert muss ein gültiger Index im lokalen Speicher des angegebenen Threads sein.</span><span class="sxs-lookup"><span data-stu-id="d5440-109">This value must be a valid index in the local store of the specified thread.</span></span>  
  
 `value`  
 <span data-ttu-id="d5440-110">vorgenommen Ein Zeiger auf einen `CLRDATA_ADDRESS` -Wert, der den Wert angibt, der vom angegebenen TLS-Speicherort zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="d5440-110">[out] A pointer to a `CLRDATA_ADDRESS` value that specifies the value returned from the given TLS location.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d5440-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d5440-111">Remarks</span></span>  
 <span data-ttu-id="d5440-112">Diese Methode wird vom Writer der Debuganwendung implementiert.</span><span class="sxs-lookup"><span data-stu-id="d5440-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5440-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d5440-113">Requirements</span></span>  
 <span data-ttu-id="d5440-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5440-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5440-115">**Header:** Clrdata. idl, Clrdata. h</span><span class="sxs-lookup"><span data-stu-id="d5440-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="d5440-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d5440-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d5440-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5440-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5440-118">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="d5440-118">See also</span></span>

- [<span data-ttu-id="d5440-119">ICLRDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d5440-119">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
