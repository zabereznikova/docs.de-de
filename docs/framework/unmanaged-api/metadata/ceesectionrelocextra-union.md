---
title: CeeSectionRelocExtra-Union
ms.date: 03/30/2017
api_name:
- CeeSectionRelocExtra Union
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CeeSectionRelocExtra
helpviewer_keywords:
- CeeSectionRelocExtra union [.NET Framework metadata]
ms.assetid: d9568cf6-7f98-4cd6-ab36-0a2bd509afcc
topic_type:
- apiref
ms.openlocfilehash: d5f61aa9b4a65a5f33e64aa4441370c3f7ca5b03
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732722"
---
# <a name="ceesectionrelocextra-union"></a><span data-ttu-id="4e03f-102">CeeSectionRelocExtra-Union</span><span class="sxs-lookup"><span data-stu-id="4e03f-102">CeeSectionRelocExtra Union</span></span>

<span data-ttu-id="4e03f-103">Stellt einen Adress Offset dar, der von der [ICeeGen](iceegen-interface.md) -Schnittstelle zum Verschieben eines Abschnitts verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4e03f-103">Represents an address offset that is used by the [ICeeGen](iceegen-interface.md) interface to relocate a section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e03f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4e03f-104">Syntax</span></span>  
  
```cpp  
typedef union  {  
    USHORT highAdj;  
} CeeSectionRelocExtra;  
```  
  
## <a name="members"></a><span data-ttu-id="4e03f-105">Member</span><span class="sxs-lookup"><span data-stu-id="4e03f-105">Members</span></span>  
  
|<span data-ttu-id="4e03f-106">Member</span><span class="sxs-lookup"><span data-stu-id="4e03f-106">Member</span></span>|<span data-ttu-id="4e03f-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4e03f-107">Description</span></span>|  
|------------|-----------------|  
|`highAdj`|<span data-ttu-id="4e03f-108">Die obere Adress Anpassung für den Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="4e03f-108">The upper address adjustment for the section.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4e03f-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="4e03f-109">Requirements</span></span>  

 <span data-ttu-id="4e03f-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e03f-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e03f-111">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="4e03f-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4e03f-112">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="4e03f-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4e03f-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e03f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e03f-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4e03f-114">See also</span></span>

- [<span data-ttu-id="4e03f-115">Metadaten-Unions</span><span class="sxs-lookup"><span data-stu-id="4e03f-115">Metadata Unions</span></span>](metadata-unions.md)
