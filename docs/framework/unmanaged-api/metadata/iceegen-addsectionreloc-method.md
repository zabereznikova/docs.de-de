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
ms.openlocfilehash: 129750644962cee3206b9e38cbeaa77d38dddd71
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176109"
---
# <a name="iceegenaddsectionreloc-method"></a><span data-ttu-id="2c9fa-102">ICeeGen::AddSectionReloc-Methode</span><span class="sxs-lookup"><span data-stu-id="2c9fa-102">ICeeGen::AddSectionReloc Method</span></span>
<span data-ttu-id="2c9fa-103">Fügt der Codebasis eine .reloc-Anweisung hinzu.</span><span class="sxs-lookup"><span data-stu-id="2c9fa-103">Adds a .reloc instruction to the code base.</span></span>  
  
 <span data-ttu-id="2c9fa-104">Diese Methode ist veraltet und sollte nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2c9fa-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c9fa-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="2c9fa-105">Syntax</span></span>  
  
```cpp  
HRESULT AddSectionReloc (  
   [in] HCEESECTION            section,  
   [in] ULONG                  offset,  
   [in] HCEESECTION            relativeTo,
   [in] CeeSectionRelocType    relocType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c9fa-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="2c9fa-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="2c9fa-107">[in] Der Abschnitt des In-Memory-Codes, dem eine .reloc-Anweisung hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="2c9fa-107">[in] The section of in-memory code to which to add a .reloc instruction.</span></span>  
  
 `offset`  
 <span data-ttu-id="2c9fa-108">[in] Der Offset des Abschnitts.</span><span class="sxs-lookup"><span data-stu-id="2c9fa-108">[in] The offset of the section.</span></span>  
  
 `relativeTo`  
 <span data-ttu-id="2c9fa-109">[in] Der Abschnitt, `offset` auf den sich bezieht.</span><span class="sxs-lookup"><span data-stu-id="2c9fa-109">[in] The section to which `offset` refers.</span></span>  
  
 `relocType`  
 <span data-ttu-id="2c9fa-110">[in] Einer der [CeeSectionRelocType-Werte,](../../../../docs/framework/unmanaged-api/metadata/ceesectionreloctype-enumeration.md) der die Art der hinzuzufügenden .reloc-Anweisung angibt.</span><span class="sxs-lookup"><span data-stu-id="2c9fa-110">[in] One of the [CeeSectionRelocType](../../../../docs/framework/unmanaged-api/metadata/ceesectionreloctype-enumeration.md) values, indicating the kind of .reloc instruction to add.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c9fa-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2c9fa-111">Requirements</span></span>  
 <span data-ttu-id="2c9fa-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c9fa-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c9fa-113">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2c9fa-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2c9fa-114">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="2c9fa-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2c9fa-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c9fa-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c9fa-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2c9fa-116">See also</span></span>

- [<span data-ttu-id="2c9fa-117">ICeeGen-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2c9fa-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
