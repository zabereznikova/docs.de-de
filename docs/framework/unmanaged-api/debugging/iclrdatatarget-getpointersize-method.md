---
title: ICLRDataTarget::GetPointerSize-Methode
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetPointerSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetPointerSize
helpviewer_keywords:
- GetPointerSize method [.NET Framework debugging]
- ICLRDataTarget::GetPointerSize method [.NET Framework debugging]
ms.assetid: 51d9f4a4-81a7-4527-8537-5212bdb05c70
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7b85739f0f9b6771b204f0e0297ab025cd112a12
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57476704"
---
# <a name="iclrdatatargetgetpointersize-method"></a><span data-ttu-id="4bd1b-102">ICLRDataTarget::GetPointerSize-Methode</span><span class="sxs-lookup"><span data-stu-id="4bd1b-102">ICLRDataTarget::GetPointerSize Method</span></span>
<span data-ttu-id="4bd1b-103">Ruft die Größe des Zeigertyps, mit denen das Ziel wird in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="4bd1b-103">Gets the size, in bytes, of the pointer type that the target process uses.</span></span> <span data-ttu-id="4bd1b-104">Diese Methode wird von den Datenzugriffsdiensten der common Language Runtime aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="4bd1b-104">This method is called by the common language runtime data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bd1b-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="4bd1b-105">Syntax</span></span>  
  
```  
HRESULT GetPointerSize (  
    [out] ULONG32     *pointerSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4bd1b-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="4bd1b-106">Parameters</span></span>  
 `pointerSize`  
 <span data-ttu-id="4bd1b-107">[out] Ein Zeiger auf einen ganzzahligen Wert, der angibt, die Größe in Bytes, der einen Zeiger auf den Zielprozess.</span><span class="sxs-lookup"><span data-stu-id="4bd1b-107">[out] A pointer to an integer value that specifies the size, in bytes, of a pointer on the target process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4bd1b-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4bd1b-108">Remarks</span></span>  
 <span data-ttu-id="4bd1b-109">Diese Methode wird vom Writer der Debuganwendung implementiert.</span><span class="sxs-lookup"><span data-stu-id="4bd1b-109">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4bd1b-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4bd1b-110">Requirements</span></span>  
 <span data-ttu-id="4bd1b-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4bd1b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4bd1b-112">**Header:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="4bd1b-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="4bd1b-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4bd1b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4bd1b-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4bd1b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bd1b-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4bd1b-115">See also</span></span>
- [<span data-ttu-id="4bd1b-116">ICLRDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4bd1b-116">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
