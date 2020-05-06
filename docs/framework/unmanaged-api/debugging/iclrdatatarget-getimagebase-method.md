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
ms.openlocfilehash: 71b07e11cd3fec1a0dbebe986d98067c2e6f18e1
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860635"
---
# <a name="iclrdatatargetgetimagebase-method"></a><span data-ttu-id="08a28-102">ICLRDataTarget::GetImageBase-Methode</span><span class="sxs-lookup"><span data-stu-id="08a28-102">ICLRDataTarget::GetImageBase Method</span></span>
<span data-ttu-id="08a28-103">Ruft die Basis Speicheradresse des angegebenen Bilds ab.</span><span class="sxs-lookup"><span data-stu-id="08a28-103">Gets the base memory address of the specified image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08a28-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="08a28-104">Syntax</span></span>  
  
```cpp  
HRESULT GetImageBase (  
    [in, string] LPCWSTR    imagePath,  
    [out] CLRDATA_ADDRESS   *baseAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="08a28-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="08a28-105">Parameters</span></span>  
 `imagePath`  
 <span data-ttu-id="08a28-106">in Der Dateiname des Bilds, einschließlich des Pfads.</span><span class="sxs-lookup"><span data-stu-id="08a28-106">[in] The file name of the image, including its path.</span></span>  
  
 `baseAddress`  
 <span data-ttu-id="08a28-107">vorgenommen Ein Zeiger auf einen CLRDATA_ADDRESS, der die Basisadresse des Bilds speichert.</span><span class="sxs-lookup"><span data-stu-id="08a28-107">[out] A pointer to a CLRDATA_ADDRESS that stores the base address of the image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="08a28-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="08a28-108">Remarks</span></span>  
 <span data-ttu-id="08a28-109">Der Bild Dateiname darf keinen Pfad aufweisen.</span><span class="sxs-lookup"><span data-stu-id="08a28-109">The image file name may or may not have a path.</span></span> <span data-ttu-id="08a28-110">Wenn ein Pfad angegeben ist, wird der entsprechende Vorgang für den gesamten Pfad ausgeführt. Andernfalls erfolgt die Übereinstimmung nur mit dem Dateinamen.</span><span class="sxs-lookup"><span data-stu-id="08a28-110">If a path is specified, matching is done on the whole path; otherwise, matching is done only on the file name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08a28-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="08a28-111">Requirements</span></span>  
 <span data-ttu-id="08a28-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08a28-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08a28-113">**Header:** Clrdata. idl, Clrdata. h</span><span class="sxs-lookup"><span data-stu-id="08a28-113">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="08a28-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="08a28-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="08a28-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08a28-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08a28-116">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="08a28-116">See also</span></span>

- [<span data-ttu-id="08a28-117">ICLRDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="08a28-117">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
