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
ms.openlocfilehash: f1b9f55a383f1deb867c6b3e2fa385a82158d1e9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703576"
---
# <a name="iclrdatatargetgetimagebase-method"></a><span data-ttu-id="50e26-102">ICLRDataTarget::GetImageBase-Methode</span><span class="sxs-lookup"><span data-stu-id="50e26-102">ICLRDataTarget::GetImageBase Method</span></span>

<span data-ttu-id="50e26-103">Ruft die Basis Speicheradresse des angegebenen Bilds ab.</span><span class="sxs-lookup"><span data-stu-id="50e26-103">Gets the base memory address of the specified image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50e26-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="50e26-104">Syntax</span></span>  
  
```cpp  
HRESULT GetImageBase (  
    [in, string] LPCWSTR    imagePath,  
    [out] CLRDATA_ADDRESS   *baseAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="50e26-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="50e26-105">Parameters</span></span>  

 `imagePath`  
 <span data-ttu-id="50e26-106">in Der Dateiname des Bilds, einschließlich des Pfads.</span><span class="sxs-lookup"><span data-stu-id="50e26-106">[in] The file name of the image, including its path.</span></span>  
  
 `baseAddress`  
 <span data-ttu-id="50e26-107">vorgenommen Ein Zeiger auf einen CLRDATA_ADDRESS, der die Basisadresse des Bilds speichert.</span><span class="sxs-lookup"><span data-stu-id="50e26-107">[out] A pointer to a CLRDATA_ADDRESS that stores the base address of the image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="50e26-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="50e26-108">Remarks</span></span>  

 <span data-ttu-id="50e26-109">Der Bild Dateiname darf keinen Pfad aufweisen.</span><span class="sxs-lookup"><span data-stu-id="50e26-109">The image file name may or may not have a path.</span></span> <span data-ttu-id="50e26-110">Wenn ein Pfad angegeben ist, wird der entsprechende Vorgang für den gesamten Pfad ausgeführt. Andernfalls erfolgt die Übereinstimmung nur mit dem Dateinamen.</span><span class="sxs-lookup"><span data-stu-id="50e26-110">If a path is specified, matching is done on the whole path; otherwise, matching is done only on the file name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50e26-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="50e26-111">Requirements</span></span>  

 <span data-ttu-id="50e26-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50e26-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50e26-113">**Header:** Clrdata. idl, Clrdata. h</span><span class="sxs-lookup"><span data-stu-id="50e26-113">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="50e26-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="50e26-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="50e26-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50e26-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50e26-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="50e26-116">See also</span></span>

- [<span data-ttu-id="50e26-117">ICLRDataTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="50e26-117">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
