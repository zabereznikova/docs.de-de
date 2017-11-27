---
title: ICeeGen::GetSectionBlock-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICeeGen.GetSectionBlock
api_location: mscoree.dll
api_type: COM
f1_keywords: ICeeGen::GetSectionBlock
helpviewer_keywords:
- GetSectionBlock method [.NET Framework metadata]
- ICeeGen::GetSectionBlock method [.NET Framework metadata]
ms.assetid: 05c78aaf-5bbd-497e-9ae2-55f4fae0c5fb
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 4732eef9a47f9ea1e919bd9d855afbec18974454
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="iceegengetsectionblock-method"></a><span data-ttu-id="73f43-102">ICeeGen::GetSectionBlock-Methode</span><span class="sxs-lookup"><span data-stu-id="73f43-102">ICeeGen::GetSectionBlock Method</span></span>
<span data-ttu-id="73f43-103">Ruft einen Abschnittsblock der CodeBase ab.</span><span class="sxs-lookup"><span data-stu-id="73f43-103">Gets a section block of the code base.</span></span>  
  
 <span data-ttu-id="73f43-104">Diese Methode ist veraltet und sollte nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="73f43-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73f43-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="73f43-105">Syntax</span></span>  
  
```  
HRESULT GetSectionBlock (  
    [in]  HCEESECTION    section,     
    [in]  ULONG          len,  
    [in]  ULONG          align     = 1,  
    [out] void           **ppBytes = 0  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="73f43-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="73f43-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="73f43-107">[in] Dem Abschnitt von dem einen Speicherblock, der die CodeBase abgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="73f43-107">[in] The section from which to retrieve a block of the code base.</span></span>  
  
 `len`  
 <span data-ttu-id="73f43-108">[in] Die Länge des Blocks abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="73f43-108">[in] The length of the block to be retrieved.</span></span>  
  
 `align`  
 <span data-ttu-id="73f43-109">[in] Das Byte, relativ zum Anfang des Abschnitts, mit der das erste Byte des Blocks ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="73f43-109">[in] The byte, relative to the beginning of the section, with which to align the first byte of the block.</span></span> <span data-ttu-id="73f43-110">Dies ist die Position des Blocks innerhalb des Abschnitts.</span><span class="sxs-lookup"><span data-stu-id="73f43-110">This is the position of the block within the section.</span></span>  
  
 `ppBytes`  
 <span data-ttu-id="73f43-111">[out] Ein Zeiger auf einen Speicherort, der die Adresse des abgerufenen Blocks empfängt.</span><span class="sxs-lookup"><span data-stu-id="73f43-111">[out] A pointer to a location that receives the address of the retrieved block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="73f43-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="73f43-112">Remarks</span></span>  
 <span data-ttu-id="73f43-113">Rufen Sie `GetSectionBlock` nur bei besonderen Anforderungen, die nicht von anderen Methoden behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="73f43-113">Call `GetSectionBlock` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73f43-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="73f43-114">Requirements</span></span>  
 <span data-ttu-id="73f43-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73f43-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73f43-116">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="73f43-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="73f43-117">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="73f43-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="73f43-118">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73f43-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73f43-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="73f43-119">See Also</span></span>  
 [<span data-ttu-id="73f43-120">ICeeGen-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="73f43-120">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
