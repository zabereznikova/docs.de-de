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
ms.openlocfilehash: 7d50f7488c2b231ea66c12cc4903469d9e2337fb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59088378"
---
# <a name="iceegenaddsectionreloc-method"></a><span data-ttu-id="062ef-102">ICeeGen::AddSectionReloc-Methode</span><span class="sxs-lookup"><span data-stu-id="062ef-102">ICeeGen::AddSectionReloc Method</span></span>
<span data-ttu-id="062ef-103">Fügt eine .reloc-Anweisung in die Codebasis.</span><span class="sxs-lookup"><span data-stu-id="062ef-103">Adds a .reloc instruction to the code base.</span></span>  
  
 <span data-ttu-id="062ef-104">Diese Methode ist veraltet und sollte nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="062ef-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="062ef-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="062ef-105">Syntax</span></span>  
  
```  
HRESULT AddSectionReloc (  
   [in] HCEESECTION            section,  
   [in] ULONG                  offset,  
   [in] HCEESECTION            relativeTo,   
   [in] CeeSectionRelocType    relocType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="062ef-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="062ef-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="062ef-107">[in] Der Codeabschnitt im Speicher, der eine .reloc-Anweisung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="062ef-107">[in] The section of in-memory code to which to add a .reloc instruction.</span></span>  
  
 `offset`  
 <span data-ttu-id="062ef-108">[in] Der Offset des Abschnitts.</span><span class="sxs-lookup"><span data-stu-id="062ef-108">[in] The offset of the section.</span></span>  
  
 `relativeTo`  
 <span data-ttu-id="062ef-109">[in] Der Abschnitt, dem `offset` verweist.</span><span class="sxs-lookup"><span data-stu-id="062ef-109">[in] The section to which `offset` refers.</span></span>  
  
 `relocType`  
 <span data-ttu-id="062ef-110">[in] Eines der [CeeSectionRelocType](../../../../docs/framework/unmanaged-api/metadata/ceesectionreloctype-enumeration.md) Werte, der die Art der .reloc-Anweisung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="062ef-110">[in] One of the [CeeSectionRelocType](../../../../docs/framework/unmanaged-api/metadata/ceesectionreloctype-enumeration.md) values, indicating the kind of .reloc instruction to add.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="062ef-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="062ef-111">Requirements</span></span>  
 <span data-ttu-id="062ef-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="062ef-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="062ef-113">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="062ef-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="062ef-114">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="062ef-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="062ef-115">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="062ef-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="062ef-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="062ef-116">See also</span></span>

- [<span data-ttu-id="062ef-117">ICeeGen-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="062ef-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
