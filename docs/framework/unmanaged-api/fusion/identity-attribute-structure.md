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
ms.openlocfilehash: de1646cdbc11369b43a821d8b762879d1df7ed2e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67751534"
---
# <a name="identityattribute-structure"></a><span data-ttu-id="59258-102">IDENTITY_ATTRIBUTE-Struktur</span><span class="sxs-lookup"><span data-stu-id="59258-102">IDENTITY_ATTRIBUTE Structure</span></span>
<span data-ttu-id="59258-103">Enthält Informationen über Bildattribute Metadaten über eine [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) Instanz.</span><span class="sxs-lookup"><span data-stu-id="59258-103">Contains metadata attribute information about an [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59258-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="59258-104">Syntax</span></span>  
  
```cpp  
typedef struct _IDENTITY_ATTRIBUTE {  
    LPCWSTR  pszNamespace;  
    LPCWSTR  pszName;  
    LPCWSTR  pszValue;  
} IDENTITY_ATTRIBUTE;  
```  
  
## <a name="members"></a><span data-ttu-id="59258-105">Member</span><span class="sxs-lookup"><span data-stu-id="59258-105">Members</span></span>  
  
|<span data-ttu-id="59258-106">Member</span><span class="sxs-lookup"><span data-stu-id="59258-106">Member</span></span>|<span data-ttu-id="59258-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="59258-107">Description</span></span>|  
|------------|-----------------|  
|`pszNamespace`|<span data-ttu-id="59258-108">Ein Zeiger auf eine Null-terminierte Zeichenfolge mit dem Namespace ist das Attribut ein.</span><span class="sxs-lookup"><span data-stu-id="59258-108">A pointer to a null-terminated character string that contains the namespace the attribute is in.</span></span>|  
|`pszName`|<span data-ttu-id="59258-109">Ein Zeiger auf eine Null-terminierte Zeichenfolge, die den Namen des Attributs enthält.</span><span class="sxs-lookup"><span data-stu-id="59258-109">A pointer to a null-terminated character string that contains the name of the attribute.</span></span>|  
|`pszValue`|<span data-ttu-id="59258-110">Ein Zeiger auf eine Null-terminierte Zeichenfolge, die den Wert des Attributs enthält.</span><span class="sxs-lookup"><span data-stu-id="59258-110">A pointer to a null-terminated character string that contains the value of the attribute.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="59258-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="59258-111">Remarks</span></span>  
 <span data-ttu-id="59258-112">Die `IDENTITY_ATTRIBUTE` Struktur enthält drei Zeigern auf Null endende Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="59258-112">The `IDENTITY_ATTRIBUTE` structure contains three pointers to null-terminated character strings.</span></span> <span data-ttu-id="59258-113">Diese drei Zeichenfolgen beschrieben, ein Attribut.</span><span class="sxs-lookup"><span data-stu-id="59258-113">These three strings describe one attribute.</span></span>  
  
 <span data-ttu-id="59258-114">Eine Instanz von einer `IDENTITY_ATTRIBUTE` Struktur bezieht sich auf einer Instanz von einem [IDENTITY_ATTRIBUTE_BLOB](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-blob-structure.md) Struktur.</span><span class="sxs-lookup"><span data-stu-id="59258-114">An instance of an `IDENTITY_ATTRIBUTE` structure is associated with an instance of an [IDENTITY_ATTRIBUTE_BLOB](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-blob-structure.md) structure.</span></span> <span data-ttu-id="59258-115">Die `IDENTITY_ATTRIBUTE` Struktur enthält die eigentlichen Zeichenfolgen, und die entsprechende `IDENTITY_ATTRIBUTE_BLOB` Struktur Listet die Offsets, die drei Zeichenfolgen aufgelistet, die der `IDENTITY_ATTRIBUTE` Struktur.</span><span class="sxs-lookup"><span data-stu-id="59258-115">The `IDENTITY_ATTRIBUTE` structure contains the actual strings, and the corresponding `IDENTITY_ATTRIBUTE_BLOB` structure lists the offsets to the three strings listed in the `IDENTITY_ATTRIBUTE` structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59258-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="59258-116">Requirements</span></span>  
 <span data-ttu-id="59258-117">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="59258-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59258-118">**Header:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="59258-118">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="59258-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59258-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59258-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="59258-120">See also</span></span>

- [<span data-ttu-id="59258-121">IDefinitionIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="59258-121">IDefinitionIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md)
- [<span data-ttu-id="59258-122">IDENTITY_ATTRIBUTE_BLOB-Struktur</span><span class="sxs-lookup"><span data-stu-id="59258-122">IDENTITY_ATTRIBUTE_BLOB Structure</span></span>](../../../../docs/framework/unmanaged-api/fusion/identity-attribute-blob-structure.md)
- [<span data-ttu-id="59258-123">Fusion-Strukturen</span><span class="sxs-lookup"><span data-stu-id="59258-123">Fusion Structures</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-structures.md)
