---
title: ICeeGen::AddSectionReloc-Methode
ms.date: 03/30/2017
api_name:
- ICeeGen.AddSectionReloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::AddSectionReloc
helpviewer_keywords:
- AddSectionReloc method [.NET Framework metadata]
- ICeeGen::AddSectionReloc method [.NET Framework metadata]
ms.assetid: b500a260-1d57-4953-95e1-c27063f7c8da
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c281d03c6e3774938cfa6e4b4b3a541738b38489
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444342"
---
# <a name="iceegenaddsectionreloc-method"></a><span data-ttu-id="390e5-102">ICeeGen::AddSectionReloc-Methode</span><span class="sxs-lookup"><span data-stu-id="390e5-102">ICeeGen::AddSectionReloc Method</span></span>
<span data-ttu-id="390e5-103">Die CodeBase hinzugefügt eine .reloc-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="390e5-103">Adds a .reloc instruction to the code base.</span></span>  
  
 <span data-ttu-id="390e5-104">Diese Methode ist veraltet und sollte nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="390e5-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="390e5-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="390e5-105">Syntax</span></span>  
  
```  
HRESULT AddSectionReloc (  
   [in] HCEESECTION            section,  
   [in] ULONG                  offset,  
   [in] HCEESECTION            relativeTo,   
   [in] CeeSectionRelocType    relocType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="390e5-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="390e5-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="390e5-107">[in] Der Codeabschnitt im Speicher, der eine .reloc-Anweisung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="390e5-107">[in] The section of in-memory code to which to add a .reloc instruction.</span></span>  
  
 `offset`  
 <span data-ttu-id="390e5-108">[in] Der Offset des Abschnitts.</span><span class="sxs-lookup"><span data-stu-id="390e5-108">[in] The offset of the section.</span></span>  
  
 `relativeTo`  
 <span data-ttu-id="390e5-109">[in] Im Abschnitt zu dem `offset` verweist.</span><span class="sxs-lookup"><span data-stu-id="390e5-109">[in] The section to which `offset` refers.</span></span>  
  
 `relocType`  
 <span data-ttu-id="390e5-110">[in] Eines der [CeeSectionRelocType](../../../../docs/framework/unmanaged-api/metadata/ceesectionreloctype-enumeration.md) Werte, die angibt, welche Art von .reloc-Anweisung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="390e5-110">[in] One of the [CeeSectionRelocType](../../../../docs/framework/unmanaged-api/metadata/ceesectionreloctype-enumeration.md) values, indicating the kind of .reloc instruction to add.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="390e5-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="390e5-111">Requirements</span></span>  
 <span data-ttu-id="390e5-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="390e5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="390e5-113">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="390e5-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="390e5-114">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="390e5-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="390e5-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="390e5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="390e5-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="390e5-116">See Also</span></span>  
 [<span data-ttu-id="390e5-117">ICeeGen-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="390e5-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
