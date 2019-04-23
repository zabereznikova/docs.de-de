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
ms.openlocfilehash: 73645265821d5854776e412f8eb0f33b36db00d1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59130493"
---
# <a name="iclrdatatargetgetpointersize-method"></a><span data-ttu-id="bacea-102">ICLRDataTarget::GetPointerSize-Methode</span><span class="sxs-lookup"><span data-stu-id="bacea-102">ICLRDataTarget::GetPointerSize Method</span></span>
<span data-ttu-id="bacea-103">Ruft die Größe des Zeigertyps, mit denen das Ziel wird in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="bacea-103">Gets the size, in bytes, of the pointer type that the target process uses.</span></span> <span data-ttu-id="bacea-104">Diese Methode wird von den Datenzugriffsdiensten der common Language Runtime aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="bacea-104">This method is called by the common language runtime data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bacea-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="bacea-105">Syntax</span></span>  
  
```  
HRESULT GetPointerSize (  
    [out] ULONG32     *pointerSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bacea-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="bacea-106">Parameters</span></span>  
 `pointerSize`  
 <span data-ttu-id="bacea-107">[out] Ein Zeiger auf einen ganzzahligen Wert, der angibt, die Größe in Bytes, der einen Zeiger auf den Zielprozess.</span><span class="sxs-lookup"><span data-stu-id="bacea-107">[out] A pointer to an integer value that specifies the size, in bytes, of a pointer on the target process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bacea-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bacea-108">Remarks</span></span>  
 <span data-ttu-id="bacea-109">Diese Methode wird vom Writer der Debuganwendung implementiert.</span><span class="sxs-lookup"><span data-stu-id="bacea-109">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bacea-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bacea-110">Requirements</span></span>  
 <span data-ttu-id="bacea-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bacea-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bacea-112">**Header:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="bacea-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="bacea-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bacea-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bacea-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bacea-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bacea-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bacea-115">See also</span></span>

- [<span data-ttu-id="bacea-116">ICLRDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bacea-116">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
