---
title: ICLRDataTarget::GetImageBase-Methode
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetImageBase
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetImageBase
helpviewer_keywords:
- ICLRDataTarget::GetImageBase method [.NET Framework debugging]
- GetImageBase method [.NET Framework debugging]
ms.assetid: 091c5f32-c160-49e3-a75f-4692e084c8e4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 91d893c0df13fbcb44c66df7f268cffdffb5fff6
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57488416"
---
# <a name="iclrdatatargetgetimagebase-method"></a><span data-ttu-id="71ead-102">ICLRDataTarget::GetImageBase-Methode</span><span class="sxs-lookup"><span data-stu-id="71ead-102">ICLRDataTarget::GetImageBase Method</span></span>
<span data-ttu-id="71ead-103">Ruft die Basis Speicheradresse des angegebenen Bilds ab.</span><span class="sxs-lookup"><span data-stu-id="71ead-103">Gets the base memory address of the specified image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71ead-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="71ead-104">Syntax</span></span>  
  
```  
HRESULT GetImageBase (  
    [in, string] LPCWSTR    imagePath,  
    [out] CLRDATA_ADDRESS   *baseAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="71ead-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="71ead-105">Parameters</span></span>  
 `imagePath`  
 <span data-ttu-id="71ead-106">[in] Der Dateiname des Bilds, einschließlich des Pfads.</span><span class="sxs-lookup"><span data-stu-id="71ead-106">[in] The file name of the image, including its path.</span></span>  
  
 `baseAddress`  
 <span data-ttu-id="71ead-107">[out] Ein Zeiger auf eine CLRDATA_ADDRESS, die Basisadresse des Bilds speichert.</span><span class="sxs-lookup"><span data-stu-id="71ead-107">[out] A pointer to a CLRDATA_ADDRESS that stores the base address of the image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="71ead-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="71ead-108">Remarks</span></span>  
 <span data-ttu-id="71ead-109">Der Namen der Abbilddatei kann oder möglicherweise keinen Pfad aufweisen.</span><span class="sxs-lookup"><span data-stu-id="71ead-109">The image file name may or may not have a path.</span></span> <span data-ttu-id="71ead-110">Wenn kein Pfad angegeben ist, erfolgt für den gesamten Pfad übereinstimmenden; andernfalls Übereinstimmung nur auf den Dateinamen erfolgt.</span><span class="sxs-lookup"><span data-stu-id="71ead-110">If a path is specified, matching is done on the whole path; otherwise, matching is done only on the file name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71ead-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="71ead-111">Requirements</span></span>  
 <span data-ttu-id="71ead-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71ead-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71ead-113">**Header:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="71ead-113">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="71ead-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="71ead-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="71ead-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71ead-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71ead-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="71ead-116">See also</span></span>
- [<span data-ttu-id="71ead-117">ICLRDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="71ead-117">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
