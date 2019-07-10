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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 38c0937804eb82d1c96a605b55a00784ba58fe13
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781826"
---
# <a name="corimportoptions-enumeration"></a><span data-ttu-id="b0488-102">CorImportOptions-Enumeration</span><span class="sxs-lookup"><span data-stu-id="b0488-102">CorImportOptions Enumeration</span></span>
<span data-ttu-id="b0488-103">Enthält Flagwerte, die das Verhalten beim Import einer Assembly außerhalb des aktuellen Bereichs steuern.</span><span class="sxs-lookup"><span data-stu-id="b0488-103">Contains flag values that control the behavior during importation of an assembly outside the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0488-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b0488-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="b0488-105">Member</span><span class="sxs-lookup"><span data-stu-id="b0488-105">Members</span></span>  
  
|<span data-ttu-id="b0488-106">Member</span><span class="sxs-lookup"><span data-stu-id="b0488-106">Member</span></span>|<span data-ttu-id="b0488-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b0488-107">Description</span></span>|  
|------------|-----------------|  
|`MDImportOptionDefault`|<span data-ttu-id="b0488-108">Gibt an, das Standardverhalten, das gelöschte Datensätze übersprungen wird.</span><span class="sxs-lookup"><span data-stu-id="b0488-108">Indicates the default behavior, which is to skip deleted records.</span></span>|  
|`MDImportOptionAll`|<span data-ttu-id="b0488-109">Gibt an, dass alle Metadaten, die aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b0488-109">Indicates that all metadata should be enumerated.</span></span>|  
|`MDImportOptionAllTypeDefs`|<span data-ttu-id="b0488-110">Gibt an, dass alle TypeDefs, einschließlich der gelöschten, aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b0488-110">Indicates that all TypeDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllMethodDefs`|<span data-ttu-id="b0488-111">Gibt an, dass alle MethodDefs, einschließlich der gelöschten, aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b0488-111">Indicates that all MethodDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllFieldDefs`|<span data-ttu-id="b0488-112">Gibt an, dass alle FieldDefs, einschließlich der gelöschten, aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b0488-112">Indicates that all FieldDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllProperties`|<span data-ttu-id="b0488-113">Gibt an, dass alle PropertyDefs, einschließlich der gelöschten, aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b0488-113">Indicates that all PropertyDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllEvents`|<span data-ttu-id="b0488-114">Gibt an, dass alle EventDefs, einschließlich der gelöschten, aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b0488-114">Indicates that all EventDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllCustomAttributes`|<span data-ttu-id="b0488-115">Gibt an, dass alle benutzerdefinierten Attribute, einschließlich der gelöschten, aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b0488-115">Indicates that all custom attributes, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllExportedTypes`|<span data-ttu-id="b0488-116">Gibt an, dass alle exportierte Typen, einschließlich der gelöschten, aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b0488-116">Indicates that all exported types, including deleted ones, should be enumerated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b0488-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b0488-117">Requirements</span></span>  
 <span data-ttu-id="b0488-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0488-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0488-119">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="b0488-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="b0488-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0488-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0488-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b0488-121">See also</span></span>

- [<span data-ttu-id="b0488-122">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="b0488-122">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
