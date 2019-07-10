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
ms.openlocfilehash: 080c16d3a7baceaa277b3418ac2e17391090f00c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67750596"
---
# <a name="iceegenallocatemethodbuffer-method"></a><span data-ttu-id="75b0c-102">ICeeGen::AllocateMethodBuffer-Methode</span><span class="sxs-lookup"><span data-stu-id="75b0c-102">ICeeGen::AllocateMethodBuffer Method</span></span>
<span data-ttu-id="75b0c-103">Erstellt einen Puffer mit der angegebenen Größe für eine Methode und ruft die relative virtuelle Adresse der Methode.</span><span class="sxs-lookup"><span data-stu-id="75b0c-103">Creates a buffer of the specified size for a method, and gets the relative virtual address of the method.</span></span>  
  
 <span data-ttu-id="75b0c-104">Diese Methode ist veraltet und sollte nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="75b0c-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75b0c-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="75b0c-105">Syntax</span></span>  
  
```cpp  
HRESULT AllocateMethodBuffer (   
    [in]  ULONG    cchBuffer,   
    [out] UCHAR    **lpBuffer,  
    [out] ULONG    *RVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="75b0c-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="75b0c-106">Parameters</span></span>  
 `cchBuffer`  
 <span data-ttu-id="75b0c-107">[in] Die Länge des zu erstellenden Puffers.</span><span class="sxs-lookup"><span data-stu-id="75b0c-107">[in] The length of the buffer to create.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="75b0c-108">[out] Der zurückgegebene Puffer.</span><span class="sxs-lookup"><span data-stu-id="75b0c-108">[out] The returned buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="75b0c-109">[out] Die relative virtuelle Adresse der Methode.</span><span class="sxs-lookup"><span data-stu-id="75b0c-109">[out] The relative virtual address of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75b0c-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="75b0c-110">Requirements</span></span>  
 <span data-ttu-id="75b0c-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="75b0c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75b0c-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="75b0c-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="75b0c-113">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="75b0c-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="75b0c-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75b0c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75b0c-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="75b0c-115">See also</span></span>

- [<span data-ttu-id="75b0c-116">ICeeGen-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="75b0c-116">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
