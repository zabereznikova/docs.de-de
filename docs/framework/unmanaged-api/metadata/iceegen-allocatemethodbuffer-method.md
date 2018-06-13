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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f56376d4400f4e24aefe2d1e5d4ad504b1d281cf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33446003"
---
# <a name="iceegenallocatemethodbuffer-method"></a><span data-ttu-id="ca7b7-102">ICeeGen::AllocateMethodBuffer-Methode</span><span class="sxs-lookup"><span data-stu-id="ca7b7-102">ICeeGen::AllocateMethodBuffer Method</span></span>
<span data-ttu-id="ca7b7-103">Erstellt einen Puffer der angegebenen Größe für eine Methode und ruft die relative virtuelle Adresse der Methode ab.</span><span class="sxs-lookup"><span data-stu-id="ca7b7-103">Creates a buffer of the specified size for a method, and gets the relative virtual address of the method.</span></span>  
  
 <span data-ttu-id="ca7b7-104">Diese Methode ist veraltet und sollte nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ca7b7-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca7b7-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="ca7b7-105">Syntax</span></span>  
  
```  
HRESULT AllocateMethodBuffer (   
    [in]  ULONG    cchBuffer,   
    [out] UCHAR    **lpBuffer,  
    [out] ULONG    *RVA  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ca7b7-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="ca7b7-106">Parameters</span></span>  
 `cchBuffer`  
 <span data-ttu-id="ca7b7-107">[in] Die Länge des zu erstellenden Puffers.</span><span class="sxs-lookup"><span data-stu-id="ca7b7-107">[in] The length of the buffer to create.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="ca7b7-108">[out] Der zurückgegebene Puffer.</span><span class="sxs-lookup"><span data-stu-id="ca7b7-108">[out] The returned buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="ca7b7-109">[out] Die relative virtuelle Adresse der Methode.</span><span class="sxs-lookup"><span data-stu-id="ca7b7-109">[out] The relative virtual address of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca7b7-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ca7b7-110">Requirements</span></span>  
 <span data-ttu-id="ca7b7-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca7b7-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca7b7-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ca7b7-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ca7b7-113">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="ca7b7-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ca7b7-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca7b7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca7b7-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ca7b7-115">See Also</span></span>  
 [<span data-ttu-id="ca7b7-116">ICeeGen-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ca7b7-116">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
