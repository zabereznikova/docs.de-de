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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992627"
---
# <a name="iceegencomputepointer-method"></a><span data-ttu-id="8c5e2-102">ICeeGen::ComputePointer-Methode</span><span class="sxs-lookup"><span data-stu-id="8c5e2-102">ICeeGen::ComputePointer Method</span></span>
<span data-ttu-id="8c5e2-103">Bestimmt den Puffer für den angegebenen Codeabschnitt.</span><span class="sxs-lookup"><span data-stu-id="8c5e2-103">Determines the buffer for the specified code section.</span></span>  
  
 <span data-ttu-id="8c5e2-104">Diese Methode ist veraltet und sollte nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8c5e2-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c5e2-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="8c5e2-105">Syntax</span></span>  
  
```  
HRESULT ComputePointer (  
    [in]  HCEESECTION  section,  
    [in]  ULONG        RVA,   
    [out] UCHAR        **lpBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8c5e2-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="8c5e2-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="8c5e2-107">[in] Im Abschnitt für den Code für den Puffer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8c5e2-107">[in] The code section for which to return a buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="8c5e2-108">[in] Die relative virtuelle Adresse der Methode für das Abrufen eines Zeigers.</span><span class="sxs-lookup"><span data-stu-id="8c5e2-108">[in] The relative virtual address of the method for which to get a pointer.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="8c5e2-109">[out] Ein Zeiger auf die zurückgegebene Puffer.</span><span class="sxs-lookup"><span data-stu-id="8c5e2-109">[out] A pointer to the returned buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c5e2-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8c5e2-110">Requirements</span></span>  
 <span data-ttu-id="8c5e2-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c5e2-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c5e2-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8c5e2-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8c5e2-113">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="8c5e2-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8c5e2-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c5e2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c5e2-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8c5e2-115">See also</span></span>

- [<span data-ttu-id="8c5e2-116">ICeeGen-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8c5e2-116">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
