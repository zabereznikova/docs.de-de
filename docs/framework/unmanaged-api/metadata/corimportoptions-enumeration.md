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
ms.openlocfilehash: a2f71a277484adbbfe3628222c635528cdab03e6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62045746"
---
# <a name="corimportoptions-enumeration"></a><span data-ttu-id="be375-102">CorImportOptions-Enumeration</span><span class="sxs-lookup"><span data-stu-id="be375-102">CorImportOptions Enumeration</span></span>
<span data-ttu-id="be375-103">Enthält Flagwerte, die das Verhalten beim Import einer Assembly außerhalb des aktuellen Bereichs steuern.</span><span class="sxs-lookup"><span data-stu-id="be375-103">Contains flag values that control the behavior during importation of an assembly outside the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be375-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="be375-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="be375-105">Member</span><span class="sxs-lookup"><span data-stu-id="be375-105">Members</span></span>  
  
|<span data-ttu-id="be375-106">Member</span><span class="sxs-lookup"><span data-stu-id="be375-106">Member</span></span>|<span data-ttu-id="be375-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="be375-107">Description</span></span>|  
|------------|-----------------|  
|`MDImportOptionDefault`|<span data-ttu-id="be375-108">Gibt an, das Standardverhalten, das gelöschte Datensätze übersprungen wird.</span><span class="sxs-lookup"><span data-stu-id="be375-108">Indicates the default behavior, which is to skip deleted records.</span></span>|  
|`MDImportOptionAll`|<span data-ttu-id="be375-109">Gibt an, dass alle Metadaten, die aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="be375-109">Indicates that all metadata should be enumerated.</span></span>|  
|`MDImportOptionAllTypeDefs`|<span data-ttu-id="be375-110">Gibt an, dass alle TypeDefs, einschließlich der gelöschten, aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="be375-110">Indicates that all TypeDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllMethodDefs`|<span data-ttu-id="be375-111">Gibt an, dass alle MethodDefs, einschließlich der gelöschten, aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="be375-111">Indicates that all MethodDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllFieldDefs`|<span data-ttu-id="be375-112">Gibt an, dass alle FieldDefs, einschließlich der gelöschten, aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="be375-112">Indicates that all FieldDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllProperties`|<span data-ttu-id="be375-113">Gibt an, dass alle PropertyDefs, einschließlich der gelöschten, aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="be375-113">Indicates that all PropertyDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllEvents`|<span data-ttu-id="be375-114">Gibt an, dass alle EventDefs, einschließlich der gelöschten, aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="be375-114">Indicates that all EventDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllCustomAttributes`|<span data-ttu-id="be375-115">Gibt an, dass alle benutzerdefinierten Attribute, einschließlich der gelöschten, aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="be375-115">Indicates that all custom attributes, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllExportedTypes`|<span data-ttu-id="be375-116">Gibt an, dass alle exportierte Typen, einschließlich der gelöschten, aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="be375-116">Indicates that all exported types, including deleted ones, should be enumerated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="be375-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="be375-117">Requirements</span></span>  
 <span data-ttu-id="be375-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be375-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be375-119">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="be375-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="be375-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be375-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be375-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="be375-121">See also</span></span>

- [<span data-ttu-id="be375-122">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="be375-122">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
