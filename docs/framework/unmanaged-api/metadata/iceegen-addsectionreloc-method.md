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
ms.openlocfilehash: 87a5224247c2d94613de482fbaa34bf978198bf0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715536"
---
# <a name="iceegenaddsectionreloc-method"></a><span data-ttu-id="5f86e-102">ICeeGen::AddSectionReloc-Methode</span><span class="sxs-lookup"><span data-stu-id="5f86e-102">ICeeGen::AddSectionReloc Method</span></span>

<span data-ttu-id="5f86e-103">Fügt der Codebasis eine reloc-Anweisung hinzu.</span><span class="sxs-lookup"><span data-stu-id="5f86e-103">Adds a .reloc instruction to the code base.</span></span>  
  
 <span data-ttu-id="5f86e-104">Diese Methode ist veraltet und sollte nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5f86e-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f86e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="5f86e-105">Syntax</span></span>  
  
```cpp  
HRESULT AddSectionReloc (  
   [in] HCEESECTION            section,  
   [in] ULONG                  offset,  
   [in] HCEESECTION            relativeTo,
   [in] CeeSectionRelocType    relocType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f86e-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="5f86e-106">Parameters</span></span>  

 `section`  
 <span data-ttu-id="5f86e-107">in Der Abschnitt des in-Memory-Codes, dem eine reloc-Anweisung hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5f86e-107">[in] The section of in-memory code to which to add a .reloc instruction.</span></span>  
  
 `offset`  
 <span data-ttu-id="5f86e-108">in Der Offset des Abschnitts.</span><span class="sxs-lookup"><span data-stu-id="5f86e-108">[in] The offset of the section.</span></span>  
  
 `relativeTo`  
 <span data-ttu-id="5f86e-109">in Der Abschnitt, auf den `offset` verweist.</span><span class="sxs-lookup"><span data-stu-id="5f86e-109">[in] The section to which `offset` refers.</span></span>  
  
 `relocType`  
 <span data-ttu-id="5f86e-110">in Einer der [CeeSectionRelocType](ceesectionreloctype-enumeration.md) -Werte, der die Art der hinzu zufügenden reloc-Anweisung angibt.</span><span class="sxs-lookup"><span data-stu-id="5f86e-110">[in] One of the [CeeSectionRelocType](ceesectionreloctype-enumeration.md) values, indicating the kind of .reloc instruction to add.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f86e-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="5f86e-111">Requirements</span></span>  

 <span data-ttu-id="5f86e-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f86e-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f86e-113">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="5f86e-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5f86e-114">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="5f86e-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5f86e-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f86e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f86e-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5f86e-116">See also</span></span>

- [<span data-ttu-id="5f86e-117">ICeeGen-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5f86e-117">ICeeGen Interface</span></span>](iceegen-interface.md)
