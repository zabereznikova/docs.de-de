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
ms.openlocfilehash: e1849eb95401e3637a1fd1b00715332f9886071e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715516"
---
# <a name="iceegenallocatemethodbuffer-method"></a><span data-ttu-id="d39c9-102">ICeeGen::AllocateMethodBuffer-Methode</span><span class="sxs-lookup"><span data-stu-id="d39c9-102">ICeeGen::AllocateMethodBuffer Method</span></span>

<span data-ttu-id="d39c9-103">Erstellt einen Puffer mit der angegebenen Größe für eine Methode und ruft die relative virtuelle Adresse der Methode ab.</span><span class="sxs-lookup"><span data-stu-id="d39c9-103">Creates a buffer of the specified size for a method, and gets the relative virtual address of the method.</span></span>  
  
 <span data-ttu-id="d39c9-104">Diese Methode ist veraltet und sollte nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d39c9-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d39c9-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="d39c9-105">Syntax</span></span>  
  
```cpp  
HRESULT AllocateMethodBuffer (
    [in]  ULONG    cchBuffer,
    [out] UCHAR    **lpBuffer,  
    [out] ULONG    *RVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d39c9-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="d39c9-106">Parameters</span></span>  

 `cchBuffer`  
 <span data-ttu-id="d39c9-107">in Die Länge des zu erstellenden Puffers.</span><span class="sxs-lookup"><span data-stu-id="d39c9-107">[in] The length of the buffer to create.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="d39c9-108">vorgenommen Der zurückgegebene Puffer.</span><span class="sxs-lookup"><span data-stu-id="d39c9-108">[out] The returned buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="d39c9-109">vorgenommen Die relative virtuelle Adresse der Methode.</span><span class="sxs-lookup"><span data-stu-id="d39c9-109">[out] The relative virtual address of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d39c9-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d39c9-110">Requirements</span></span>  

 <span data-ttu-id="d39c9-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d39c9-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d39c9-112">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d39c9-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d39c9-113">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="d39c9-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d39c9-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d39c9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d39c9-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d39c9-115">See also</span></span>

- [<span data-ttu-id="d39c9-116">ICeeGen-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d39c9-116">ICeeGen Interface</span></span>](iceegen-interface.md)
