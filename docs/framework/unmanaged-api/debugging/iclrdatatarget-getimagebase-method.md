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
ms.openlocfilehash: 9dbb655d6ed0b9bd88c5eedf61a191401a805fb3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738756"
---
# <a name="iclrdatatargetgetimagebase-method"></a><span data-ttu-id="51571-102">ICLRDataTarget::GetImageBase-Methode</span><span class="sxs-lookup"><span data-stu-id="51571-102">ICLRDataTarget::GetImageBase Method</span></span>
<span data-ttu-id="51571-103">Ruft die Basis Speicheradresse des angegebenen Bilds ab.</span><span class="sxs-lookup"><span data-stu-id="51571-103">Gets the base memory address of the specified image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51571-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="51571-104">Syntax</span></span>  
  
```cpp  
HRESULT GetImageBase (  
    [in, string] LPCWSTR    imagePath,  
    [out] CLRDATA_ADDRESS   *baseAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="51571-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="51571-105">Parameters</span></span>  
 `imagePath`  
 <span data-ttu-id="51571-106">[in] Der Dateiname des Bilds, einschließlich des Pfads.</span><span class="sxs-lookup"><span data-stu-id="51571-106">[in] The file name of the image, including its path.</span></span>  
  
 `baseAddress`  
 <span data-ttu-id="51571-107">[out] Ein Zeiger auf eine CLRDATA_ADDRESS, die Basisadresse des Bilds speichert.</span><span class="sxs-lookup"><span data-stu-id="51571-107">[out] A pointer to a CLRDATA_ADDRESS that stores the base address of the image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="51571-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="51571-108">Remarks</span></span>  
 <span data-ttu-id="51571-109">Der Namen der Abbilddatei kann oder möglicherweise keinen Pfad aufweisen.</span><span class="sxs-lookup"><span data-stu-id="51571-109">The image file name may or may not have a path.</span></span> <span data-ttu-id="51571-110">Wenn kein Pfad angegeben ist, erfolgt für den gesamten Pfad übereinstimmenden; andernfalls Übereinstimmung nur auf den Dateinamen erfolgt.</span><span class="sxs-lookup"><span data-stu-id="51571-110">If a path is specified, matching is done on the whole path; otherwise, matching is done only on the file name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51571-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="51571-111">Requirements</span></span>  
 <span data-ttu-id="51571-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51571-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51571-113">**Header:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="51571-113">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="51571-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="51571-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="51571-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51571-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51571-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="51571-116">See also</span></span>

- [<span data-ttu-id="51571-117">ICLRDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="51571-117">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
