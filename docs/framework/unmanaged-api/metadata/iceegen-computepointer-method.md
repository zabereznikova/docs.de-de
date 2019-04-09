---
title: ICeeGen::ComputePointer-Methode
ms.date: 03/30/2017
api_name:
- ICeeGen.ComputePointer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::ComputePointer
helpviewer_keywords:
- ICeeGen::ComputePointer method [.NET Framework metadata]
- ComputePointer method [.NET Framework metadata]
ms.assetid: b6b95c04-0f2c-4fcc-a8bc-3b1dcbdba731
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 79ef272e0c8afa0cd1942416c3a5eb9b825c2e6f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59145144"
---
# <a name="iceegencomputepointer-method"></a><span data-ttu-id="36a84-102">ICeeGen::ComputePointer-Methode</span><span class="sxs-lookup"><span data-stu-id="36a84-102">ICeeGen::ComputePointer Method</span></span>
<span data-ttu-id="36a84-103">Bestimmt den Puffer für den angegebenen Codeabschnitt.</span><span class="sxs-lookup"><span data-stu-id="36a84-103">Determines the buffer for the specified code section.</span></span>  
  
 <span data-ttu-id="36a84-104">Diese Methode ist veraltet und sollte nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="36a84-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36a84-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="36a84-105">Syntax</span></span>  
  
```  
HRESULT ComputePointer (  
    [in]  HCEESECTION  section,  
    [in]  ULONG        RVA,   
    [out] UCHAR        **lpBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="36a84-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="36a84-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="36a84-107">[in] Im Abschnitt für den Code für den Puffer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="36a84-107">[in] The code section for which to return a buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="36a84-108">[in] Die relative virtuelle Adresse der Methode für das Abrufen eines Zeigers.</span><span class="sxs-lookup"><span data-stu-id="36a84-108">[in] The relative virtual address of the method for which to get a pointer.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="36a84-109">[out] Ein Zeiger auf die zurückgegebene Puffer.</span><span class="sxs-lookup"><span data-stu-id="36a84-109">[out] A pointer to the returned buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36a84-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="36a84-110">Requirements</span></span>  
 <span data-ttu-id="36a84-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36a84-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36a84-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="36a84-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="36a84-113">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="36a84-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="36a84-114">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="36a84-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="36a84-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="36a84-115">See also</span></span>

- [<span data-ttu-id="36a84-116">ICeeGen-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="36a84-116">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
