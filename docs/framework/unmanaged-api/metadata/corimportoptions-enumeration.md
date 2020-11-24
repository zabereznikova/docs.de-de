---
title: CorImportOptions-Enumeration
ms.date: 03/30/2017
api_name:
- CorImportOptions
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorImportOptions
helpviewer_keywords:
- CorImportOptions enumeration [.NET Framework metadata]
ms.assetid: 4e5d03cb-97c9-4ff4-8dbd-17d94ee374d3
topic_type:
- apiref
ms.openlocfilehash: 3d5989d43644088403a77f26c02af9ffaae0732b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677218"
---
# <a name="corimportoptions-enumeration"></a><span data-ttu-id="e39dc-102">CorImportOptions-Enumeration</span><span class="sxs-lookup"><span data-stu-id="e39dc-102">CorImportOptions Enumeration</span></span>

<span data-ttu-id="e39dc-103">Enthält Flagwerte, die das Verhalten beim Import einer Assembly außerhalb des aktuellen Bereichs steuern.</span><span class="sxs-lookup"><span data-stu-id="e39dc-103">Contains flag values that control the behavior during importation of an assembly outside the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e39dc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e39dc-104">Syntax</span></span>  
  
```cpp  
typedef enum CorImportOptions {  
  
    MDImportOptionDefault                = 0x00000000,  
    MDImportOptionAll                    = 0xFFFFFFFF,  
    MDImportOptionAllTypeDefs            = 0x00000001,  
    MDImportOptionAllMethodDefs          = 0x00000002,  
    MDImportOptionAllFieldDefs           = 0x00000004,  
    MDImportOptionAllProperties          = 0x00000008,  
    MDImportOptionAllEvents              = 0x00000010,  
    MDImportOptionAllCustomAttributes    = 0x00000020,  
    MDImportOptionAllExportedTypes       = 0x00000040  
  
} CorImportOptions;  
```  
  
## <a name="members"></a><span data-ttu-id="e39dc-105">Member</span><span class="sxs-lookup"><span data-stu-id="e39dc-105">Members</span></span>  
  
|<span data-ttu-id="e39dc-106">Member</span><span class="sxs-lookup"><span data-stu-id="e39dc-106">Member</span></span>|<span data-ttu-id="e39dc-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e39dc-107">Description</span></span>|  
|------------|-----------------|  
|`MDImportOptionDefault`|<span data-ttu-id="e39dc-108">Gibt das Standardverhalten an, das zum Überspringen gelöschter Datensätze dient.</span><span class="sxs-lookup"><span data-stu-id="e39dc-108">Indicates the default behavior, which is to skip deleted records.</span></span>|  
|`MDImportOptionAll`|<span data-ttu-id="e39dc-109">Gibt an, dass alle Metadaten aufgezählt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e39dc-109">Indicates that all metadata should be enumerated.</span></span>|  
|`MDImportOptionAllTypeDefs`|<span data-ttu-id="e39dc-110">Gibt an, dass alle Typedefs, einschließlich gelöschter Typen, aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e39dc-110">Indicates that all TypeDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllMethodDefs`|<span data-ttu-id="e39dc-111">Gibt an, dass alle methoddefs, einschließlich der gelöschten, aufgezählt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e39dc-111">Indicates that all MethodDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllFieldDefs`|<span data-ttu-id="e39dc-112">Gibt an, dass alle FieldDefs, einschließlich gelöschter, aufgezählt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e39dc-112">Indicates that all FieldDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllProperties`|<span data-ttu-id="e39dc-113">Gibt an, dass alle PropertyDefs, einschließlich gelöschter Werte, aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e39dc-113">Indicates that all PropertyDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllEvents`|<span data-ttu-id="e39dc-114">Gibt an, dass alle EventDefs, einschließlich der gelöschten, aufgezählt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e39dc-114">Indicates that all EventDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllCustomAttributes`|<span data-ttu-id="e39dc-115">Gibt an, dass alle benutzerdefinierten Attribute, einschließlich gelöschter Attribute, aufgezählt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e39dc-115">Indicates that all custom attributes, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllExportedTypes`|<span data-ttu-id="e39dc-116">Gibt an, dass alle exportierten Typen, einschließlich gelöschter Typen, aufgezählt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e39dc-116">Indicates that all exported types, including deleted ones, should be enumerated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e39dc-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e39dc-117">Requirements</span></span>  

 <span data-ttu-id="e39dc-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e39dc-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e39dc-119">**Header:** Corhdr. h</span><span class="sxs-lookup"><span data-stu-id="e39dc-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="e39dc-120">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e39dc-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e39dc-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e39dc-121">See also</span></span>

- [<span data-ttu-id="e39dc-122">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="e39dc-122">Metadata Enumerations</span></span>](metadata-enumerations.md)
