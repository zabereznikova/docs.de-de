---
title: CorAttributeTargets-Enumeration
ms.date: 03/30/2017
api_name:
- CorAttributeTargets
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorAttributeTargets
helpviewer_keywords:
- CorAttributeTargets enumeration [.NET Framework metadata]
ms.assetid: 694c0fa0-7011-41a9-9dfd-f0e16ea574b5
topic_type:
- apiref
ms.openlocfilehash: 5f83cb96e39b257a1d35786130cd5ed31d071de7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443869"
---
# <a name="corattributetargets-enumeration"></a><span data-ttu-id="926d4-102">CorAttributeTargets-Enumeration</span><span class="sxs-lookup"><span data-stu-id="926d4-102">CorAttributeTargets Enumeration</span></span>
<span data-ttu-id="926d4-103">Gibt die Anwendungselemente an, auf die ein Attribut angewendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="926d4-103">Specifies the application elements on which it is valid to apply an attribute.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="926d4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="926d4-104">Syntax</span></span>  
  
```cpp  
typedef enum CorAttributeTargets  
{  
    catAssembly            = 0x0001,  
    catModule              = 0x0002,  
    catClass               = 0x0004,  
    catStruct              = 0x0008,  
    catEnum                = 0x0010,  
    catConstructor         = 0x0020,  
    catMethod              = 0x0040,  
    catProperty            = 0x0080,  
    catField               = 0x0100,  
    catEvent               = 0x0200,  
    catInterface           = 0x0400,  
    catParameter           = 0x0800,  
    catDelegate            = 0x1000,  
    catGenericParameter    = 0x4000,  
  
    catAll                 =   
        catAssembly | catModule | catClass | catStruct |   
        catEnum | catConstructor | catMethod | catProperty |   
        catField | catEvent | catInterface | catParameter |   
        catDelegate | catGenericParameter,  
  
    catClassMembers        =   
        catClass | catStruct | catEnum | catConstructor |   
        catMethod | catProperty | catField | catEvent |   
        catDelegate | catInterface  
  
} CorAttributeTargets;  
```  
  
## <a name="members"></a><span data-ttu-id="926d4-105">Member</span><span class="sxs-lookup"><span data-stu-id="926d4-105">Members</span></span>  
  
|<span data-ttu-id="926d4-106">Member</span><span class="sxs-lookup"><span data-stu-id="926d4-106">Member</span></span>|<span data-ttu-id="926d4-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="926d4-107">Description</span></span>|  
|------------|-----------------|  
|`catAssembly`|<span data-ttu-id="926d4-108">Das Attribut kann auf eine Assembly angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="926d4-108">Attribute can be applied to an assembly.</span></span>|  
|`catModule`|<span data-ttu-id="926d4-109">Das Attribut kann auf ein ausführbares ausführbares ausführbares Modul (. dll oder. exe) angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="926d4-109">Attribute can be applied to a portable executable (.dll or .exe) module.</span></span>|  
|`catClass`|<span data-ttu-id="926d4-110">Das Attribut kann auf eine Klasse angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="926d4-110">Attribute can be applied to a class.</span></span>|  
|`catStruct`|<span data-ttu-id="926d4-111">Das Attribut kann auf eine Struktur angewendet werden. Das heißt, ein Werttyp.</span><span class="sxs-lookup"><span data-stu-id="926d4-111">Attribute can be applied to a structure; that is, a value type.</span></span>|  
|`catEnum`|<span data-ttu-id="926d4-112">Das Attribut kann auf eine Enumeration angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="926d4-112">Attribute can be applied to an enumeration.</span></span>|  
|`catConstructor`|<span data-ttu-id="926d4-113">Das Attribut kann auf einen Konstruktor angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="926d4-113">Attribute can be applied to a constructor.</span></span>|  
|`catMethod`|<span data-ttu-id="926d4-114">Das Attribut kann auf eine Methode angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="926d4-114">Attribute can be applied to a method.</span></span>|  
|`catProperty`|<span data-ttu-id="926d4-115">Das Attribut kann auf eine Eigenschaft angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="926d4-115">Attribute can be applied to a property.</span></span>|  
|`catField`|<span data-ttu-id="926d4-116">Das Attribut kann auf ein Feld angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="926d4-116">Attribute can be applied to a field.</span></span>|  
|`catEvent`|<span data-ttu-id="926d4-117">Das Attribut kann auf ein Ereignis angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="926d4-117">Attribute can be applied to an event.</span></span>|  
|`catInterface`|<span data-ttu-id="926d4-118">Das Attribut kann auf eine Schnittstelle angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="926d4-118">Attribute can be applied to an interface.</span></span>|  
|`catParameter`|<span data-ttu-id="926d4-119">Das Attribut kann auf einen Parameter angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="926d4-119">Attribute can be applied to a parameter.</span></span>|  
|`catDelegate`|<span data-ttu-id="926d4-120">Das Attribut kann auf einen Delegaten angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="926d4-120">Attribute can be applied to a delegate.</span></span>|  
|`catGenericParameter`|<span data-ttu-id="926d4-121">Das Attribut kann auf einen generischen Parameter angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="926d4-121">Attribute can be applied to a generic parameter.</span></span>|  
|`catAll`|<span data-ttu-id="926d4-122">Das Attribut kann auf ein beliebiges Anwendungs Element angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="926d4-122">Attribute can be applied to any application element.</span></span>|  
|`catClassMembers`|<span data-ttu-id="926d4-123">Das Attribut kann auf einen Member einer Klasse angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="926d4-123">Attribute can be applied to a member of a class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="926d4-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="926d4-124">Remarks</span></span>  
 <span data-ttu-id="926d4-125">Die `CorAttributeTargets` Enumerationswerte können mit einer bitweisen OR-Operation kombiniert werden, um die bevorzugte Kombination zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="926d4-125">The `CorAttributeTargets` enumeration values can be combined with a bitwise OR operation to get the preferred combination.</span></span>  
  
 <span data-ttu-id="926d4-126">Der `CorAttributeTargets` der die verwaltete <xref:System.AttributeTargets?displayProperty=nameWithType>-Enumeration entspricht.</span><span class="sxs-lookup"><span data-stu-id="926d4-126">The `CorAttributeTargets` parallels the managed <xref:System.AttributeTargets?displayProperty=nameWithType> enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="926d4-127">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="926d4-127">Requirements</span></span>  
 <span data-ttu-id="926d4-128">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="926d4-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="926d4-129">**Header:** Corhdr. h</span><span class="sxs-lookup"><span data-stu-id="926d4-129">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="926d4-130">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="926d4-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="926d4-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="926d4-131">See also</span></span>

- [<span data-ttu-id="926d4-132">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="926d4-132">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
