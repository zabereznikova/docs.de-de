---
title: IDENTITY_ATTRIBUTE-Struktur
ms.date: 03/30/2017
api_name:
- IDENTITY_ATTRIBUTE
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDENTITY_ATTRIBUTE
helpviewer_keywords:
- IDENTITY_ATTRIBUTE structure [.NET Framework fusion]
ms.assetid: 1ee7c434-9681-4fa8-badd-652cb1a9742b
topic_type:
- apiref
ms.openlocfilehash: da4b1d6f2a7079ef33859fce29c9555ac06fcfc2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725650"
---
# <a name="identity_attribute-structure"></a><span data-ttu-id="4eee9-102">IDENTITY_ATTRIBUTE-Struktur</span><span class="sxs-lookup"><span data-stu-id="4eee9-102">IDENTITY_ATTRIBUTE Structure</span></span>

<span data-ttu-id="4eee9-103">Enthält Metadaten-Attributinformationen zu einer [IDefinitionIdentity](idefinitionidentity-interface.md) -Instanz.</span><span class="sxs-lookup"><span data-stu-id="4eee9-103">Contains metadata attribute information about an [IDefinitionIdentity](idefinitionidentity-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4eee9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4eee9-104">Syntax</span></span>  
  
```cpp  
typedef struct _IDENTITY_ATTRIBUTE {  
    LPCWSTR  pszNamespace;  
    LPCWSTR  pszName;  
    LPCWSTR  pszValue;  
} IDENTITY_ATTRIBUTE;  
```  
  
## <a name="members"></a><span data-ttu-id="4eee9-105">Member</span><span class="sxs-lookup"><span data-stu-id="4eee9-105">Members</span></span>  
  
|<span data-ttu-id="4eee9-106">Member</span><span class="sxs-lookup"><span data-stu-id="4eee9-106">Member</span></span>|<span data-ttu-id="4eee9-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4eee9-107">Description</span></span>|  
|------------|-----------------|  
|`pszNamespace`|<span data-ttu-id="4eee9-108">Ein Zeiger auf eine NULL-terminierte Zeichenfolge, die den Namespace enthält, in dem sich das Attribut befindet.</span><span class="sxs-lookup"><span data-stu-id="4eee9-108">A pointer to a null-terminated character string that contains the namespace the attribute is in.</span></span>|  
|`pszName`|<span data-ttu-id="4eee9-109">Ein Zeiger auf eine NULL-terminierte Zeichenfolge, die den Namen des Attributs enthält.</span><span class="sxs-lookup"><span data-stu-id="4eee9-109">A pointer to a null-terminated character string that contains the name of the attribute.</span></span>|  
|`pszValue`|<span data-ttu-id="4eee9-110">Ein Zeiger auf eine NULL-terminierte Zeichenfolge, die den Wert des Attributs enthält.</span><span class="sxs-lookup"><span data-stu-id="4eee9-110">A pointer to a null-terminated character string that contains the value of the attribute.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4eee9-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4eee9-111">Remarks</span></span>  

 <span data-ttu-id="4eee9-112">Die- `IDENTITY_ATTRIBUTE` Struktur enthält drei Zeiger auf auf NULL endend Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="4eee9-112">The `IDENTITY_ATTRIBUTE` structure contains three pointers to null-terminated character strings.</span></span> <span data-ttu-id="4eee9-113">Diese drei Zeichen folgen beschreiben ein Attribut.</span><span class="sxs-lookup"><span data-stu-id="4eee9-113">These three strings describe one attribute.</span></span>  
  
 <span data-ttu-id="4eee9-114">Eine Instanz einer- `IDENTITY_ATTRIBUTE` Struktur ist einer Instanz einer [IDENTITY_ATTRIBUTE_BLOB](identity-attribute-blob-structure.md) -Struktur zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="4eee9-114">An instance of an `IDENTITY_ATTRIBUTE` structure is associated with an instance of an [IDENTITY_ATTRIBUTE_BLOB](identity-attribute-blob-structure.md) structure.</span></span> <span data-ttu-id="4eee9-115">Die `IDENTITY_ATTRIBUTE` -Struktur enthält die eigentlichen Zeichen folgen, und die entsprechende- `IDENTITY_ATTRIBUTE_BLOB` Struktur listet die Offsets zu den drei Zeichen folgen auf, die in der-Struktur aufgeführt sind `IDENTITY_ATTRIBUTE` .</span><span class="sxs-lookup"><span data-stu-id="4eee9-115">The `IDENTITY_ATTRIBUTE` structure contains the actual strings, and the corresponding `IDENTITY_ATTRIBUTE_BLOB` structure lists the offsets to the three strings listed in the `IDENTITY_ATTRIBUTE` structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4eee9-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="4eee9-116">Requirements</span></span>  

 <span data-ttu-id="4eee9-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4eee9-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4eee9-118">**Header:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="4eee9-118">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="4eee9-119">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4eee9-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4eee9-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4eee9-120">See also</span></span>

- [<span data-ttu-id="4eee9-121">IDefinitionIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4eee9-121">IDefinitionIdentity Interface</span></span>](idefinitionidentity-interface.md)
- [<span data-ttu-id="4eee9-122">IDENTITY_ATTRIBUTE_BLOB-Struktur</span><span class="sxs-lookup"><span data-stu-id="4eee9-122">IDENTITY_ATTRIBUTE_BLOB Structure</span></span>](identity-attribute-blob-structure.md)
- [<span data-ttu-id="4eee9-123">Fusionsstrukturen</span><span class="sxs-lookup"><span data-stu-id="4eee9-123">Fusion Structures</span></span>](fusion-structures.md)
