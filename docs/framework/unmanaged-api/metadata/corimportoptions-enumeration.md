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
ms.openlocfilehash: 3be8a004be752af8a8675a3499bdb6cbfd785840
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009196"
---
# <a name="corimportoptions-enumeration"></a><span data-ttu-id="f0298-102">CorImportOptions-Enumeration</span><span class="sxs-lookup"><span data-stu-id="f0298-102">CorImportOptions Enumeration</span></span>
<span data-ttu-id="f0298-103">Enthält Flagwerte, die das Verhalten beim Import einer Assembly außerhalb des aktuellen Bereichs steuern.</span><span class="sxs-lookup"><span data-stu-id="f0298-103">Contains flag values that control the behavior during importation of an assembly outside the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0298-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f0298-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="f0298-105">Member</span><span class="sxs-lookup"><span data-stu-id="f0298-105">Members</span></span>  
  
|<span data-ttu-id="f0298-106">Member</span><span class="sxs-lookup"><span data-stu-id="f0298-106">Member</span></span>|<span data-ttu-id="f0298-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f0298-107">Description</span></span>|  
|------------|-----------------|  
|`MDImportOptionDefault`|<span data-ttu-id="f0298-108">Gibt das Standardverhalten an, das zum Überspringen gelöschter Datensätze dient.</span><span class="sxs-lookup"><span data-stu-id="f0298-108">Indicates the default behavior, which is to skip deleted records.</span></span>|  
|`MDImportOptionAll`|<span data-ttu-id="f0298-109">Gibt an, dass alle Metadaten aufgezählt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f0298-109">Indicates that all metadata should be enumerated.</span></span>|  
|`MDImportOptionAllTypeDefs`|<span data-ttu-id="f0298-110">Gibt an, dass alle Typedefs, einschließlich gelöschter Typen, aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f0298-110">Indicates that all TypeDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllMethodDefs`|<span data-ttu-id="f0298-111">Gibt an, dass alle methoddefs, einschließlich der gelöschten, aufgezählt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f0298-111">Indicates that all MethodDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllFieldDefs`|<span data-ttu-id="f0298-112">Gibt an, dass alle FieldDefs, einschließlich gelöschter, aufgezählt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f0298-112">Indicates that all FieldDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllProperties`|<span data-ttu-id="f0298-113">Gibt an, dass alle PropertyDefs, einschließlich gelöschter Werte, aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f0298-113">Indicates that all PropertyDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllEvents`|<span data-ttu-id="f0298-114">Gibt an, dass alle EventDefs, einschließlich der gelöschten, aufgezählt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f0298-114">Indicates that all EventDefs, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllCustomAttributes`|<span data-ttu-id="f0298-115">Gibt an, dass alle benutzerdefinierten Attribute, einschließlich gelöschter Attribute, aufgezählt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f0298-115">Indicates that all custom attributes, including deleted ones, should be enumerated.</span></span>|  
|`MDImportOptionAllExportedTypes`|<span data-ttu-id="f0298-116">Gibt an, dass alle exportierten Typen, einschließlich gelöschter Typen, aufgezählt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f0298-116">Indicates that all exported types, including deleted ones, should be enumerated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f0298-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f0298-117">Requirements</span></span>  
 <span data-ttu-id="f0298-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0298-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0298-119">**Header:** Corhdr. h</span><span class="sxs-lookup"><span data-stu-id="f0298-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="f0298-120">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0298-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0298-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f0298-121">See also</span></span>

- [<span data-ttu-id="f0298-122">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="f0298-122">Metadata Enumerations</span></span>](metadata-enumerations.md)
