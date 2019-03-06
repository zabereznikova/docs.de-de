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
ms.openlocfilehash: b5e86461973d24e9bd61df9ce27da5a614a49aa3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471010"
---
# <a name="iceegenallocatemethodbuffer-method"></a><span data-ttu-id="94e54-102">ICeeGen::AllocateMethodBuffer-Methode</span><span class="sxs-lookup"><span data-stu-id="94e54-102">ICeeGen::AllocateMethodBuffer Method</span></span>
<span data-ttu-id="94e54-103">Erstellt einen Puffer mit der angegebenen Größe für eine Methode und ruft die relative virtuelle Adresse der Methode.</span><span class="sxs-lookup"><span data-stu-id="94e54-103">Creates a buffer of the specified size for a method, and gets the relative virtual address of the method.</span></span>  
  
 <span data-ttu-id="94e54-104">Diese Methode ist veraltet und sollte nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="94e54-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94e54-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="94e54-105">Syntax</span></span>  
  
```  
HRESULT AllocateMethodBuffer (   
    [in]  ULONG    cchBuffer,   
    [out] UCHAR    **lpBuffer,  
    [out] ULONG    *RVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="94e54-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="94e54-106">Parameters</span></span>  
 `cchBuffer`  
 <span data-ttu-id="94e54-107">[in] Die Länge des zu erstellenden Puffers.</span><span class="sxs-lookup"><span data-stu-id="94e54-107">[in] The length of the buffer to create.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="94e54-108">[out] Der zurückgegebene Puffer.</span><span class="sxs-lookup"><span data-stu-id="94e54-108">[out] The returned buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="94e54-109">[out] Die relative virtuelle Adresse der Methode.</span><span class="sxs-lookup"><span data-stu-id="94e54-109">[out] The relative virtual address of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94e54-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="94e54-110">Requirements</span></span>  
 <span data-ttu-id="94e54-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94e54-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94e54-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="94e54-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="94e54-113">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="94e54-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="94e54-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94e54-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94e54-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="94e54-115">See also</span></span>
- [<span data-ttu-id="94e54-116">ICeeGen-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="94e54-116">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
