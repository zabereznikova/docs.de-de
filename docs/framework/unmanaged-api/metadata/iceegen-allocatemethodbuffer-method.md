---
title: ICeeGen::AllocateMethodBuffer-Methode
ms.date: 03/30/2017
api_name:
- ICeeGen.AllocateMethodBuffer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::AllocateMethodBuffer
helpviewer_keywords:
- AllocateMethodBuffer method [.NET Framework metadata]
- ICeeGen::AllocateMethodBuffer method [.NET Framework metadata]
ms.assetid: 845ab77e-9639-47f5-99fb-f3b619e3e779
topic_type:
- apiref
ms.openlocfilehash: 8dc7f439cac56c2d55916ff8631ec3095c67680d
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008884"
---
# <a name="iceegenallocatemethodbuffer-method"></a><span data-ttu-id="de39d-102">ICeeGen::AllocateMethodBuffer-Methode</span><span class="sxs-lookup"><span data-stu-id="de39d-102">ICeeGen::AllocateMethodBuffer Method</span></span>
<span data-ttu-id="de39d-103">Erstellt einen Puffer mit der angegebenen Größe für eine Methode und ruft die relative virtuelle Adresse der Methode ab.</span><span class="sxs-lookup"><span data-stu-id="de39d-103">Creates a buffer of the specified size for a method, and gets the relative virtual address of the method.</span></span>  
  
 <span data-ttu-id="de39d-104">Diese Methode ist veraltet und sollte nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="de39d-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de39d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="de39d-105">Syntax</span></span>  
  
```cpp  
HRESULT AllocateMethodBuffer (
    [in]  ULONG    cchBuffer,
    [out] UCHAR    **lpBuffer,  
    [out] ULONG    *RVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="de39d-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="de39d-106">Parameters</span></span>  
 `cchBuffer`  
 <span data-ttu-id="de39d-107">in Die Länge des zu erstellenden Puffers.</span><span class="sxs-lookup"><span data-stu-id="de39d-107">[in] The length of the buffer to create.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="de39d-108">vorgenommen Der zurückgegebene Puffer.</span><span class="sxs-lookup"><span data-stu-id="de39d-108">[out] The returned buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="de39d-109">vorgenommen Die relative virtuelle Adresse der Methode.</span><span class="sxs-lookup"><span data-stu-id="de39d-109">[out] The relative virtual address of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de39d-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="de39d-110">Requirements</span></span>  
 <span data-ttu-id="de39d-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de39d-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de39d-112">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="de39d-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="de39d-113">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="de39d-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="de39d-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de39d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de39d-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="de39d-115">See also</span></span>

- [<span data-ttu-id="de39d-116">ICeeGen-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="de39d-116">ICeeGen Interface</span></span>](iceegen-interface.md)
