---
title: CorImportOptions-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorImportOptions
api_location: mscoree.dll
api_type: COM
f1_keywords: CorImportOptions
helpviewer_keywords: CorImportOptions enumeration [.NET Framework metadata]
ms.assetid: 4e5d03cb-97c9-4ff4-8dbd-17d94ee374d3
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3e014443945574cff2733e5bc5d992691acc3fd9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="corimportoptions-enumeration"></a><span data-ttu-id="1890f-102">CorImportOptions-Enumeration</span><span class="sxs-lookup"><span data-stu-id="1890f-102">CorImportOptions Enumeration</span></span>
<span data-ttu-id="1890f-103">Enthält Flagwerte, die das Verhalten beim Import einer Assembly außerhalb des aktuellen Bereichs steuern.</span><span class="sxs-lookup"><span data-stu-id="1890f-103">Contains flag values that control the behavior during importation of an assembly outside the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1890f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1890f-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="1890f-105">Member</span><span class="sxs-lookup"><span data-stu-id="1890f-105">Members</span></span>  
  
|<span data-ttu-id="1890f-106">Member</span><span class="sxs-lookup"><span data-stu-id="1890f-106">Member</span></span>|<span data-ttu-id="1890f-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1890f-107">Description</span></span>|  
|------------|-----------------|  
|`MDImportOptionDefault`|<span data-ttu-id="1890f-108">Gibt an, das Standardverhalten, d. h. gelöschten Datensätze übersprungen.</span><span class="sxs-lookup"><span data-stu-id="1890f-108">Indicates the default behavior, which is to skip deleted records.</span></span>|  
|`MDImportOptionAll`|<span data-ttu-id="1890f-109">Gibt an, dass alle Metadaten aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1890f-109">Indicates that all metadata should be enumerated.</span></span>|  
|`MDImportOptionAllTypeDefs`|<span data-ttu-id="1890f-110">Gibt an, dass alle TypeDefs, auch die gelöschten, aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1890f-110">Indicates that all TypeDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllMethodDefs`|<span data-ttu-id="1890f-111">Gibt an, dass alle MethodDefs, auch die gelöschten, aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1890f-111">Indicates that all MethodDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllFieldDefs`|<span data-ttu-id="1890f-112">Gibt an, dass alle FieldDefs, auch die gelöschten, aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1890f-112">Indicates that all FieldDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllProperties`|<span data-ttu-id="1890f-113">Gibt an, dass alle PropertyDefs, auch die gelöschten, aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1890f-113">Indicates that all PropertyDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllEvents`|<span data-ttu-id="1890f-114">Gibt an, dass alle EventDefs, auch die gelöschten, aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1890f-114">Indicates that all EventDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllCustomAttributes`|<span data-ttu-id="1890f-115">Gibt an, dass alle benutzerdefinierten Attribute, einschließlich der gelöschten, aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1890f-115">Indicates that all custom attributes, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllExportedTypes`|<span data-ttu-id="1890f-116">Gibt an, dass alle exportierte Typen, einschließlich der gelöschten, aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1890f-116">Indicates that all exported types, including deleted ones, should be enumerated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1890f-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1890f-117">Requirements</span></span>  
 <span data-ttu-id="1890f-118">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1890f-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1890f-119">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="1890f-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="1890f-120">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1890f-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1890f-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1890f-121">See Also</span></span>  
 [<span data-ttu-id="1890f-122">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="1890f-122">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
