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
ms.openlocfilehash: e823911280f52e16c745c9c77fe17b49bd35dc0b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698279"
---
# <a name="iclrdatatargetgetimagebase-method"></a><span data-ttu-id="ed3ed-102">ICLRDataTarget::GetImageBase-Methode</span><span class="sxs-lookup"><span data-stu-id="ed3ed-102">ICLRDataTarget::GetImageBase Method</span></span>
<span data-ttu-id="ed3ed-103">Ruft die Basis Speicheradresse des angegebenen Bilds ab.</span><span class="sxs-lookup"><span data-stu-id="ed3ed-103">Gets the base memory address of the specified image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed3ed-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ed3ed-104">Syntax</span></span>  
  
```  
HRESULT GetImageBase (  
    [in, string] LPCWSTR    imagePath,  
    [out] CLRDATA_ADDRESS   *baseAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ed3ed-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ed3ed-105">Parameters</span></span>  
 `imagePath`  
 <span data-ttu-id="ed3ed-106">[in] Der Dateiname des Bilds, einschließlich des Pfads.</span><span class="sxs-lookup"><span data-stu-id="ed3ed-106">[in] The file name of the image, including its path.</span></span>  
  
 `baseAddress`  
 <span data-ttu-id="ed3ed-107">[out] Ein Zeiger auf eine CLRDATA_ADDRESS, die Basisadresse des Bilds speichert.</span><span class="sxs-lookup"><span data-stu-id="ed3ed-107">[out] A pointer to a CLRDATA_ADDRESS that stores the base address of the image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ed3ed-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ed3ed-108">Remarks</span></span>  
 <span data-ttu-id="ed3ed-109">Der Namen der Abbilddatei kann oder möglicherweise keinen Pfad aufweisen.</span><span class="sxs-lookup"><span data-stu-id="ed3ed-109">The image file name may or may not have a path.</span></span> <span data-ttu-id="ed3ed-110">Wenn kein Pfad angegeben ist, erfolgt für den gesamten Pfad übereinstimmenden; andernfalls Übereinstimmung nur auf den Dateinamen erfolgt.</span><span class="sxs-lookup"><span data-stu-id="ed3ed-110">If a path is specified, matching is done on the whole path; otherwise, matching is done only on the file name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed3ed-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ed3ed-111">Requirements</span></span>  
 <span data-ttu-id="ed3ed-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed3ed-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed3ed-113">**Header:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="ed3ed-113">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="ed3ed-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ed3ed-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ed3ed-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed3ed-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed3ed-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ed3ed-116">See also</span></span>

- [<span data-ttu-id="ed3ed-117">ICLRDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ed3ed-117">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
