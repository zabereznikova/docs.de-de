---
title: ICeeGen::AddSectionReloc-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICeeGen.AddSectionReloc
api_location: mscoree.dll
api_type: COM
f1_keywords: ICeeGen::AddSectionReloc
helpviewer_keywords:
- AddSectionReloc method [.NET Framework metadata]
- ICeeGen::AddSectionReloc method [.NET Framework metadata]
ms.assetid: b500a260-1d57-4953-95e1-c27063f7c8da
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a74f01e3904c6f3f472110288abbec42fa892fdc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="iceegenaddsectionreloc-method"></a><span data-ttu-id="52922-102">ICeeGen::AddSectionReloc-Methode</span><span class="sxs-lookup"><span data-stu-id="52922-102">ICeeGen::AddSectionReloc Method</span></span>
<span data-ttu-id="52922-103">Die CodeBase hinzugefügt eine .reloc-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="52922-103">Adds a .reloc instruction to the code base.</span></span>  
  
 <span data-ttu-id="52922-104">Diese Methode ist veraltet und sollte nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="52922-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52922-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="52922-105">Syntax</span></span>  
  
```  
HRESULT AddSectionReloc (  
   [in] HCEESECTION            section,  
   [in] ULONG                  offset,  
   [in] HCEESECTION            relativeTo,   
   [in] CeeSectionRelocType    relocType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="52922-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="52922-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="52922-107">[in] Der Codeabschnitt im Speicher, der eine .reloc-Anweisung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="52922-107">[in] The section of in-memory code to which to add a .reloc instruction.</span></span>  
  
 `offset`  
 <span data-ttu-id="52922-108">[in] Der Offset des Abschnitts.</span><span class="sxs-lookup"><span data-stu-id="52922-108">[in] The offset of the section.</span></span>  
  
 `relativeTo`  
 <span data-ttu-id="52922-109">[in] Im Abschnitt zu dem `offset` verweist.</span><span class="sxs-lookup"><span data-stu-id="52922-109">[in] The section to which `offset` refers.</span></span>  
  
 `relocType`  
 <span data-ttu-id="52922-110">[in] Eines der [CeeSectionRelocType](../../../../docs/framework/unmanaged-api/metadata/ceesectionreloctype-enumeration.md) Werte, die angibt, welche Art von .reloc-Anweisung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="52922-110">[in] One of the [CeeSectionRelocType](../../../../docs/framework/unmanaged-api/metadata/ceesectionreloctype-enumeration.md) values, indicating the kind of .reloc instruction to add.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52922-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="52922-111">Requirements</span></span>  
 <span data-ttu-id="52922-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52922-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52922-113">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="52922-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="52922-114">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="52922-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="52922-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52922-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52922-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="52922-116">See Also</span></span>  
 [<span data-ttu-id="52922-117">ICeeGen-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="52922-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
