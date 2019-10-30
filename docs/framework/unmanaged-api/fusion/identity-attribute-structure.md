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
ms.openlocfilehash: 8b7edf1cc642228c4a79c855b51727264f31741c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73107986"
---
# <a name="identity_attribute-structure"></a><span data-ttu-id="9f71b-102">IDENTITY_ATTRIBUTE-Struktur</span><span class="sxs-lookup"><span data-stu-id="9f71b-102">IDENTITY_ATTRIBUTE Structure</span></span>
<span data-ttu-id="9f71b-103">Enthält Metadaten-Attributinformationen zu einer [IDefinitionIdentity](idefinitionidentity-interface.md) -Instanz.</span><span class="sxs-lookup"><span data-stu-id="9f71b-103">Contains metadata attribute information about an [IDefinitionIdentity](idefinitionidentity-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f71b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9f71b-104">Syntax</span></span>  
  
```cpp  
typedef struct _IDENTITY_ATTRIBUTE {  
    LPCWSTR  pszNamespace;  
    LPCWSTR  pszName;  
    LPCWSTR  pszValue;  
} IDENTITY_ATTRIBUTE;  
```  
  
## <a name="members"></a><span data-ttu-id="9f71b-105">Member</span><span class="sxs-lookup"><span data-stu-id="9f71b-105">Members</span></span>  
  
|<span data-ttu-id="9f71b-106">Member</span><span class="sxs-lookup"><span data-stu-id="9f71b-106">Member</span></span>|<span data-ttu-id="9f71b-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9f71b-107">Description</span></span>|  
|------------|-----------------|  
|`pszNamespace`|<span data-ttu-id="9f71b-108">Ein Zeiger auf eine NULL-terminierte Zeichenfolge, die den Namespace enthält, in dem sich das Attribut befindet.</span><span class="sxs-lookup"><span data-stu-id="9f71b-108">A pointer to a null-terminated character string that contains the namespace the attribute is in.</span></span>|  
|`pszName`|<span data-ttu-id="9f71b-109">Ein Zeiger auf eine NULL-terminierte Zeichenfolge, die den Namen des Attributs enthält.</span><span class="sxs-lookup"><span data-stu-id="9f71b-109">A pointer to a null-terminated character string that contains the name of the attribute.</span></span>|  
|`pszValue`|<span data-ttu-id="9f71b-110">Ein Zeiger auf eine NULL-terminierte Zeichenfolge, die den Wert des Attributs enthält.</span><span class="sxs-lookup"><span data-stu-id="9f71b-110">A pointer to a null-terminated character string that contains the value of the attribute.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9f71b-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9f71b-111">Remarks</span></span>  
 <span data-ttu-id="9f71b-112">Die `IDENTITY_ATTRIBUTE`-Struktur enthält drei Zeiger auf auf NULL endend Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="9f71b-112">The `IDENTITY_ATTRIBUTE` structure contains three pointers to null-terminated character strings.</span></span> <span data-ttu-id="9f71b-113">Diese drei Zeichen folgen beschreiben ein Attribut.</span><span class="sxs-lookup"><span data-stu-id="9f71b-113">These three strings describe one attribute.</span></span>  
  
 <span data-ttu-id="9f71b-114">Eine Instanz einer `IDENTITY_ATTRIBUTE`-Struktur ist einer Instanz einer [IDENTITY_ATTRIBUTE_BLOB](identity-attribute-blob-structure.md) -Struktur zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="9f71b-114">An instance of an `IDENTITY_ATTRIBUTE` structure is associated with an instance of an [IDENTITY_ATTRIBUTE_BLOB](identity-attribute-blob-structure.md) structure.</span></span> <span data-ttu-id="9f71b-115">Die `IDENTITY_ATTRIBUTE`-Struktur enthält die eigentlichen Zeichen folgen, und die entsprechende `IDENTITY_ATTRIBUTE_BLOB` Struktur listet die Offsets zu den drei Zeichen folgen auf, die in der `IDENTITY_ATTRIBUTE`-Struktur aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="9f71b-115">The `IDENTITY_ATTRIBUTE` structure contains the actual strings, and the corresponding `IDENTITY_ATTRIBUTE_BLOB` structure lists the offsets to the three strings listed in the `IDENTITY_ATTRIBUTE` structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f71b-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9f71b-116">Requirements</span></span>  
 <span data-ttu-id="9f71b-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f71b-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f71b-118">**Header:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="9f71b-118">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="9f71b-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f71b-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f71b-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9f71b-120">See also</span></span>

- [<span data-ttu-id="9f71b-121">IDefinitionIdentity-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9f71b-121">IDefinitionIdentity Interface</span></span>](idefinitionidentity-interface.md)
- [<span data-ttu-id="9f71b-122">IDENTITY_ATTRIBUTE_BLOB-Struktur</span><span class="sxs-lookup"><span data-stu-id="9f71b-122">IDENTITY_ATTRIBUTE_BLOB Structure</span></span>](identity-attribute-blob-structure.md)
- [<span data-ttu-id="9f71b-123">Fusion-Strukturen</span><span class="sxs-lookup"><span data-stu-id="9f71b-123">Fusion Structures</span></span>](fusion-structures.md)
