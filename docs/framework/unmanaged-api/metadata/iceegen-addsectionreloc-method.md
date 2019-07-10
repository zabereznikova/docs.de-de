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
ms.openlocfilehash: da3b83191ce1acdf40e27c5ee1d843a1fb4a54f8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67750677"
---
# <a name="iceegenaddsectionreloc-method"></a><span data-ttu-id="f7d33-102">ICeeGen::AddSectionReloc-Methode</span><span class="sxs-lookup"><span data-stu-id="f7d33-102">ICeeGen::AddSectionReloc Method</span></span>
<span data-ttu-id="f7d33-103">Fügt eine .reloc-Anweisung in die Codebasis.</span><span class="sxs-lookup"><span data-stu-id="f7d33-103">Adds a .reloc instruction to the code base.</span></span>  
  
 <span data-ttu-id="f7d33-104">Diese Methode ist veraltet und sollte nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f7d33-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7d33-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f7d33-105">Syntax</span></span>  
  
```cpp  
HRESULT AddSectionReloc (  
   [in] HCEESECTION            section,  
   [in] ULONG                  offset,  
   [in] HCEESECTION            relativeTo,   
   [in] CeeSectionRelocType    relocType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7d33-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="f7d33-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="f7d33-107">[in] Der Codeabschnitt im Speicher, der eine .reloc-Anweisung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f7d33-107">[in] The section of in-memory code to which to add a .reloc instruction.</span></span>  
  
 `offset`  
 <span data-ttu-id="f7d33-108">[in] Der Offset des Abschnitts.</span><span class="sxs-lookup"><span data-stu-id="f7d33-108">[in] The offset of the section.</span></span>  
  
 `relativeTo`  
 <span data-ttu-id="f7d33-109">[in] Der Abschnitt, dem `offset` verweist.</span><span class="sxs-lookup"><span data-stu-id="f7d33-109">[in] The section to which `offset` refers.</span></span>  
  
 `relocType`  
 <span data-ttu-id="f7d33-110">[in] Eines der [CeeSectionRelocType](../../../../docs/framework/unmanaged-api/metadata/ceesectionreloctype-enumeration.md) Werte, der die Art der .reloc-Anweisung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="f7d33-110">[in] One of the [CeeSectionRelocType](../../../../docs/framework/unmanaged-api/metadata/ceesectionreloctype-enumeration.md) values, indicating the kind of .reloc instruction to add.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7d33-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f7d33-111">Requirements</span></span>  
 <span data-ttu-id="f7d33-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7d33-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7d33-113">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f7d33-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f7d33-114">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="f7d33-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f7d33-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7d33-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7d33-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f7d33-116">See also</span></span>

- [<span data-ttu-id="f7d33-117">ICeeGen-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f7d33-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
