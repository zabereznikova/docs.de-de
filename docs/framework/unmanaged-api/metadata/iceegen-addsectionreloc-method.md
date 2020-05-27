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
ms.openlocfilehash: 2f66d34fcfdd8c61dcc92817ec1a928ac5b603fc
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008897"
---
# <a name="iceegenaddsectionreloc-method"></a><span data-ttu-id="b73dc-102">ICeeGen::AddSectionReloc-Methode</span><span class="sxs-lookup"><span data-stu-id="b73dc-102">ICeeGen::AddSectionReloc Method</span></span>
<span data-ttu-id="b73dc-103">Fügt der Codebasis eine reloc-Anweisung hinzu.</span><span class="sxs-lookup"><span data-stu-id="b73dc-103">Adds a .reloc instruction to the code base.</span></span>  
  
 <span data-ttu-id="b73dc-104">Diese Methode ist veraltet und sollte nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b73dc-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b73dc-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b73dc-105">Syntax</span></span>  
  
```cpp  
HRESULT AddSectionReloc (  
   [in] HCEESECTION            section,  
   [in] ULONG                  offset,  
   [in] HCEESECTION            relativeTo,
   [in] CeeSectionRelocType    relocType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b73dc-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="b73dc-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="b73dc-107">in Der Abschnitt des in-Memory-Codes, dem eine reloc-Anweisung hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="b73dc-107">[in] The section of in-memory code to which to add a .reloc instruction.</span></span>  
  
 `offset`  
 <span data-ttu-id="b73dc-108">in Der Offset des Abschnitts.</span><span class="sxs-lookup"><span data-stu-id="b73dc-108">[in] The offset of the section.</span></span>  
  
 `relativeTo`  
 <span data-ttu-id="b73dc-109">in Der Abschnitt, auf den `offset` verweist.</span><span class="sxs-lookup"><span data-stu-id="b73dc-109">[in] The section to which `offset` refers.</span></span>  
  
 `relocType`  
 <span data-ttu-id="b73dc-110">in Einer der [CeeSectionRelocType](ceesectionreloctype-enumeration.md) -Werte, der die Art der hinzu zufügenden reloc-Anweisung angibt.</span><span class="sxs-lookup"><span data-stu-id="b73dc-110">[in] One of the [CeeSectionRelocType](ceesectionreloctype-enumeration.md) values, indicating the kind of .reloc instruction to add.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b73dc-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b73dc-111">Requirements</span></span>  
 <span data-ttu-id="b73dc-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b73dc-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b73dc-113">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b73dc-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b73dc-114">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="b73dc-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b73dc-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b73dc-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b73dc-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b73dc-116">See also</span></span>

- [<span data-ttu-id="b73dc-117">ICeeGen-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b73dc-117">ICeeGen Interface</span></span>](iceegen-interface.md)
