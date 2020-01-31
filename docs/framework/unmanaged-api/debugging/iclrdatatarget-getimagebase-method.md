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
ms.openlocfilehash: fcf0ab73c79a5fa116a89cdfcc2e73b17d9eabfc
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76785496"
---
# <a name="iclrdatatargetgetimagebase-method"></a><span data-ttu-id="f47fa-102">ICLRDataTarget::GetImageBase-Methode</span><span class="sxs-lookup"><span data-stu-id="f47fa-102">ICLRDataTarget::GetImageBase Method</span></span>
<span data-ttu-id="f47fa-103">Ruft die Basis Speicheradresse des angegebenen Bilds ab.</span><span class="sxs-lookup"><span data-stu-id="f47fa-103">Gets the base memory address of the specified image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f47fa-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f47fa-104">Syntax</span></span>  
  
```cpp  
HRESULT GetImageBase (  
    [in, string] LPCWSTR    imagePath,  
    [out] CLRDATA_ADDRESS   *baseAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f47fa-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="f47fa-105">Parameters</span></span>  
 `imagePath`  
 <span data-ttu-id="f47fa-106">in Der Dateiname des Bilds, einschließlich des Pfads.</span><span class="sxs-lookup"><span data-stu-id="f47fa-106">[in] The file name of the image, including its path.</span></span>  
  
 `baseAddress`  
 <span data-ttu-id="f47fa-107">vorgenommen Ein Zeiger auf einen CLRDATA_ADDRESS, der die Basisadresse des Bilds speichert.</span><span class="sxs-lookup"><span data-stu-id="f47fa-107">[out] A pointer to a CLRDATA_ADDRESS that stores the base address of the image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f47fa-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f47fa-108">Remarks</span></span>  
 <span data-ttu-id="f47fa-109">Der Bild Dateiname darf keinen Pfad aufweisen.</span><span class="sxs-lookup"><span data-stu-id="f47fa-109">The image file name may or may not have a path.</span></span> <span data-ttu-id="f47fa-110">Wenn ein Pfad angegeben ist, wird der entsprechende Vorgang für den gesamten Pfad ausgeführt. Andernfalls erfolgt die Übereinstimmung nur mit dem Dateinamen.</span><span class="sxs-lookup"><span data-stu-id="f47fa-110">If a path is specified, matching is done on the whole path; otherwise, matching is done only on the file name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f47fa-111">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f47fa-111">Requirements</span></span>  
 <span data-ttu-id="f47fa-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f47fa-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f47fa-113">**Header:** Clrdata. idl, Clrdata. h</span><span class="sxs-lookup"><span data-stu-id="f47fa-113">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="f47fa-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f47fa-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f47fa-115">**.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f47fa-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f47fa-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f47fa-116">See also</span></span>

- [<span data-ttu-id="f47fa-117">ICLRDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f47fa-117">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
