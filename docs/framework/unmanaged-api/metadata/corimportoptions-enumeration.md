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
ms.openlocfilehash: 44d1776e2902988353ef4fd58aca20e56203b9da
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442841"
---
# <a name="corimportoptions-enumeration"></a><span data-ttu-id="bdc8a-102">CorImportOptions-Enumeration</span><span class="sxs-lookup"><span data-stu-id="bdc8a-102">CorImportOptions Enumeration</span></span>
<span data-ttu-id="bdc8a-103">Enthält Flagwerte, die das Verhalten beim Import einer Assembly außerhalb des aktuellen Bereichs steuern.</span><span class="sxs-lookup"><span data-stu-id="bdc8a-103">Contains flag values that control the behavior during importation of an assembly outside the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdc8a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bdc8a-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="bdc8a-105">Member</span><span class="sxs-lookup"><span data-stu-id="bdc8a-105">Members</span></span>  
  
|<span data-ttu-id="bdc8a-106">Member</span><span class="sxs-lookup"><span data-stu-id="bdc8a-106">Member</span></span>|<span data-ttu-id="bdc8a-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bdc8a-107">Description</span></span>|  
|------------|-----------------|  
|`MDImportOptionDefault`|<span data-ttu-id="bdc8a-108">Indicates the default behavior, which is to skip deleted records.</span><span class="sxs-lookup"><span data-stu-id="bdc8a-108">Indicates the default behavior, which is to skip deleted records.</span></span>|  
|`MDImportOptionAll`|<span data-ttu-id="bdc8a-109">Indicates that all metadata should be enumerated.</span><span class="sxs-lookup"><span data-stu-id="bdc8a-109">Indicates that all metadata should be enumerated.</span></span>|  
|`MDImportOptionAllTypeDefs`|<span data-ttu-id="bdc8a-110">Indicates that all TypeDefs, including deleted ones, should be enumerated.</span><span class="sxs-lookup"><span data-stu-id="bdc8a-110">Indicates that all TypeDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllMethodDefs`|<span data-ttu-id="bdc8a-111">Indicates that all MethodDefs, including deleted ones, should be enumerated.</span><span class="sxs-lookup"><span data-stu-id="bdc8a-111">Indicates that all MethodDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllFieldDefs`|<span data-ttu-id="bdc8a-112">Indicates that all FieldDefs, including deleted ones, should be enumerated.</span><span class="sxs-lookup"><span data-stu-id="bdc8a-112">Indicates that all FieldDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllProperties`|<span data-ttu-id="bdc8a-113">Indicates that all PropertyDefs, including deleted ones, should be enumerated.</span><span class="sxs-lookup"><span data-stu-id="bdc8a-113">Indicates that all PropertyDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllEvents`|<span data-ttu-id="bdc8a-114">Indicates that all EventDefs, including deleted ones, should be enumerated.</span><span class="sxs-lookup"><span data-stu-id="bdc8a-114">Indicates that all EventDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllCustomAttributes`|<span data-ttu-id="bdc8a-115">Indicates that all custom attributes, including deleted ones, should be enumerated.</span><span class="sxs-lookup"><span data-stu-id="bdc8a-115">Indicates that all custom attributes, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllExportedTypes`|<span data-ttu-id="bdc8a-116">Indicates that all exported types, including deleted ones, should be enumerated.</span><span class="sxs-lookup"><span data-stu-id="bdc8a-116">Indicates that all exported types, including deleted ones, should be enumerated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bdc8a-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bdc8a-117">Requirements</span></span>  
 <span data-ttu-id="bdc8a-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bdc8a-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bdc8a-119">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="bdc8a-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="bdc8a-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bdc8a-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdc8a-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bdc8a-121">See also</span></span>

- [<span data-ttu-id="bdc8a-122">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="bdc8a-122">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
