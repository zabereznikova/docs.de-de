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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e0bcabb32d50b236d42a555c073b50ba3a234dde
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796485"
---
# <a name="identity_attribute-structure"></a><span data-ttu-id="85787-102">IDENTITY_ATTRIBUTE-Struktur</span><span class="sxs-lookup"><span data-stu-id="85787-102">IDENTITY_ATTRIBUTE Structure</span></span>
<span data-ttu-id="85787-103">Enthält Metadaten-Attributinformationen zu einer [IDefinitionIdentity](idefinitionidentity-interface.md) -Instanz.</span><span class="sxs-lookup"><span data-stu-id="85787-103">Contains metadata attribute information about an [IDefinitionIdentity](idefinitionidentity-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85787-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="85787-104">Syntax</span></span>  
  
```cpp  
typedef struct _IDENTITY_ATTRIBUTE {  
    LPCWSTR  pszNamespace;  
    LPCWSTR  pszName;  
    LPCWSTR  pszValue;  
} IDENTITY_ATTRIBUTE;  
```  
  
## <a name="members"></a><span data-ttu-id="85787-105">Member</span><span class="sxs-lookup"><span data-stu-id="85787-105">Members</span></span>  
  
|<span data-ttu-id="85787-106">Member</span><span class="sxs-lookup"><span data-stu-id="85787-106">Member</span></span>|<span data-ttu-id="85787-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="85787-107">Description</span></span>|  
|------------|-----------------|  
|`pszNamespace`|<span data-ttu-id="85787-108">Ein Zeiger auf eine NULL-terminierte Zeichenfolge, die den Namespace enthält, in dem sich das Attribut befindet.</span><span class="sxs-lookup"><span data-stu-id="85787-108">A pointer to a null-terminated character string that contains the namespace the attribute is in.</span></span>|  
|`pszName`|<span data-ttu-id="85787-109">Ein Zeiger auf eine NULL-terminierte Zeichenfolge, die den Namen des Attributs enthält.</span><span class="sxs-lookup"><span data-stu-id="85787-109">A pointer to a null-terminated character string that contains the name of the attribute.</span></span>|  
|`pszValue`|<span data-ttu-id="85787-110">Ein Zeiger auf eine NULL-terminierte Zeichenfolge, die den Wert des Attributs enthält.</span><span class="sxs-lookup"><span data-stu-id="85787-110">A pointer to a null-terminated character string that contains the value of the attribute.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="85787-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="85787-111">Remarks</span></span>  
 <span data-ttu-id="85787-112">Die `IDENTITY_ATTRIBUTE` -Struktur enthält drei Zeiger auf auf NULL endend Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="85787-112">The `IDENTITY_ATTRIBUTE` structure contains three pointers to null-terminated character strings.</span></span> <span data-ttu-id="85787-113">Diese drei Zeichen folgen beschreiben ein Attribut.</span><span class="sxs-lookup"><span data-stu-id="85787-113">These three strings describe one attribute.</span></span>  
  
 <span data-ttu-id="85787-114">Eine Instanz `IDENTITY_ATTRIBUTE` einer-Struktur ist einer Instanz einer [IDENTITY_ATTRIBUTE_BLOB](identity-attribute-blob-structure.md) -Struktur zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="85787-114">An instance of an `IDENTITY_ATTRIBUTE` structure is associated with an instance of an [IDENTITY_ATTRIBUTE_BLOB](identity-attribute-blob-structure.md) structure.</span></span> <span data-ttu-id="85787-115">Die `IDENTITY_ATTRIBUTE` -Struktur enthält die eigentlichen Zeichen folgen, und `IDENTITY_ATTRIBUTE_BLOB` die entsprechende-Struktur listet die Offsets zu den drei Zeichen `IDENTITY_ATTRIBUTE` folgen auf, die in der-Struktur aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="85787-115">The `IDENTITY_ATTRIBUTE` structure contains the actual strings, and the corresponding `IDENTITY_ATTRIBUTE_BLOB` structure lists the offsets to the three strings listed in the `IDENTITY_ATTRIBUTE` structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85787-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="85787-116">Requirements</span></span>  
 <span data-ttu-id="85787-117">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85787-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85787-118">**Header:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="85787-118">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="85787-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85787-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85787-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="85787-120">See also</span></span>

- [<span data-ttu-id="85787-121">IDefinitionIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="85787-121">IDefinitionIdentity Interface</span></span>](idefinitionidentity-interface.md)
- [<span data-ttu-id="85787-122">IDENTITY_ATTRIBUTE_BLOB-Struktur</span><span class="sxs-lookup"><span data-stu-id="85787-122">IDENTITY_ATTRIBUTE_BLOB Structure</span></span>](identity-attribute-blob-structure.md)
- [<span data-ttu-id="85787-123">Fusion-Strukturen</span><span class="sxs-lookup"><span data-stu-id="85787-123">Fusion Structures</span></span>](fusion-structures.md)
