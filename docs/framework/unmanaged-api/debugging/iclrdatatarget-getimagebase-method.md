---
title: ICLRDataTarget::GetImageBase-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataTarget.GetImageBase
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataTarget::GetImageBase
helpviewer_keywords:
- ICLRDataTarget::GetImageBase method [.NET Framework debugging]
- GetImageBase method [.NET Framework debugging]
ms.assetid: 091c5f32-c160-49e3-a75f-4692e084c8e4
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1d397995266d6063164510a4b563ba94f7f54950
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="iclrdatatargetgetimagebase-method"></a><span data-ttu-id="bb697-102">ICLRDataTarget::GetImageBase-Methode</span><span class="sxs-lookup"><span data-stu-id="bb697-102">ICLRDataTarget::GetImageBase Method</span></span>
<span data-ttu-id="bb697-103">Ruft die Basis Speicheradresse für das angegebene Bild ab.</span><span class="sxs-lookup"><span data-stu-id="bb697-103">Gets the base memory address of the specified image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb697-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bb697-104">Syntax</span></span>  
  
```  
HRESULT GetImageBase (  
    [in, string] LPCWSTR    imagePath,  
    [out] CLRDATA_ADDRESS   *baseAddress  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bb697-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bb697-105">Parameters</span></span>  
 `imagePath`  
 <span data-ttu-id="bb697-106">[in] Der Dateiname des Bilds, einschließlich ihres Pfads.</span><span class="sxs-lookup"><span data-stu-id="bb697-106">[in] The file name of the image, including its path.</span></span>  
  
 `baseAddress`  
 <span data-ttu-id="bb697-107">[out] Ein Zeiger auf eine CLRDATA_ADDRESS, die Basisadresse des Bilds speichert.</span><span class="sxs-lookup"><span data-stu-id="bb697-107">[out] A pointer to a CLRDATA_ADDRESS that stores the base address of the image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bb697-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bb697-108">Remarks</span></span>  
 <span data-ttu-id="bb697-109">Die Bilddateinamen kann oder möglicherweise keinen Pfad.</span><span class="sxs-lookup"><span data-stu-id="bb697-109">The image file name may or may not have a path.</span></span> <span data-ttu-id="bb697-110">Wenn kein Pfad angegeben wird, erfolgt für den gesamten Pfad übereinstimmenden; Abgleich ist hingegen nur auf den Dateinamen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="bb697-110">If a path is specified, matching is done on the whole path; otherwise, matching is done only on the file name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb697-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bb697-111">Requirements</span></span>  
 <span data-ttu-id="bb697-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb697-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb697-113">**Header:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="bb697-113">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="bb697-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bb697-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bb697-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb697-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb697-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bb697-116">See Also</span></span>  
 [<span data-ttu-id="bb697-117">ICLRDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bb697-117">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
