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
ms.openlocfilehash: fed643ae52f50b1b8cd134880c644c8941da6f56
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122874"
---
# <a name="iclrdatatargetgetimagebase-method"></a><span data-ttu-id="3871f-102">ICLRDataTarget::GetImageBase-Methode</span><span class="sxs-lookup"><span data-stu-id="3871f-102">ICLRDataTarget::GetImageBase Method</span></span>
<span data-ttu-id="3871f-103">Ruft die Basis Speicheradresse des angegebenen Bilds ab.</span><span class="sxs-lookup"><span data-stu-id="3871f-103">Gets the base memory address of the specified image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3871f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3871f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetImageBase (  
    [in, string] LPCWSTR    imagePath,  
    [out] CLRDATA_ADDRESS   *baseAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3871f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3871f-105">Parameters</span></span>  
 `imagePath`  
 <span data-ttu-id="3871f-106">in Der Dateiname des Bilds, einschließlich des Pfads.</span><span class="sxs-lookup"><span data-stu-id="3871f-106">[in] The file name of the image, including its path.</span></span>  
  
 `baseAddress`  
 <span data-ttu-id="3871f-107">vorgenommen Ein Zeiger auf ein CLRDATA_ADDRESS, in dem die Basisadresse des Bilds gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="3871f-107">[out] A pointer to a CLRDATA_ADDRESS that stores the base address of the image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3871f-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3871f-108">Remarks</span></span>  
 <span data-ttu-id="3871f-109">Der Bild Dateiname darf keinen Pfad aufweisen.</span><span class="sxs-lookup"><span data-stu-id="3871f-109">The image file name may or may not have a path.</span></span> <span data-ttu-id="3871f-110">Wenn ein Pfad angegeben ist, wird der entsprechende Vorgang für den gesamten Pfad ausgeführt. Andernfalls erfolgt die Übereinstimmung nur mit dem Dateinamen.</span><span class="sxs-lookup"><span data-stu-id="3871f-110">If a path is specified, matching is done on the whole path; otherwise, matching is done only on the file name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3871f-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3871f-111">Requirements</span></span>  
 <span data-ttu-id="3871f-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3871f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3871f-113">**Header:** Clrdata. idl, Clrdata. h</span><span class="sxs-lookup"><span data-stu-id="3871f-113">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="3871f-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3871f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3871f-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3871f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3871f-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3871f-116">See also</span></span>

- [<span data-ttu-id="3871f-117">ICLRDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3871f-117">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)
