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
ms.openlocfilehash: fbe721bad56ec2be434039f00e741ad9a177815f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718968"
---
# <a name="corattributetargets-enumeration"></a><span data-ttu-id="0a406-102">CorAttributeTargets-Enumeration</span><span class="sxs-lookup"><span data-stu-id="0a406-102">CorAttributeTargets Enumeration</span></span>

<span data-ttu-id="0a406-103">Gibt die Anwendungselemente an, auf die Attribute angewendet werden können.</span><span class="sxs-lookup"><span data-stu-id="0a406-103">Specifies the application elements on which it is valid to apply an attribute.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a406-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0a406-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="0a406-105">Member</span><span class="sxs-lookup"><span data-stu-id="0a406-105">Members</span></span>  
  
|<span data-ttu-id="0a406-106">Member</span><span class="sxs-lookup"><span data-stu-id="0a406-106">Member</span></span>|<span data-ttu-id="0a406-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0a406-107">Description</span></span>|  
|------------|-----------------|  
|`catAssembly`|<span data-ttu-id="0a406-108">Auf Assemblys können Attribute angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="0a406-108">Attribute can be applied to an assembly.</span></span>|  
|`catModule`|<span data-ttu-id="0a406-109">Das Attribut kann auf ein ausführbares ausführbares ausführbares Modul (. dll oder. exe) angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="0a406-109">Attribute can be applied to a portable executable (.dll or .exe) module.</span></span>|  
|`catClass`|<span data-ttu-id="0a406-110">Auf Klassen können Attribute angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="0a406-110">Attribute can be applied to a class.</span></span>|  
|`catStruct`|<span data-ttu-id="0a406-111">Auf Strukturen, d. h. auf Werttypen, können Attribute angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="0a406-111">Attribute can be applied to a structure; that is, a value type.</span></span>|  
|`catEnum`|<span data-ttu-id="0a406-112">Auf Enumerationen können Attribute angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="0a406-112">Attribute can be applied to an enumeration.</span></span>|  
|`catConstructor`|<span data-ttu-id="0a406-113">Auf Konstruktoren können Attribute angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="0a406-113">Attribute can be applied to a constructor.</span></span>|  
|`catMethod`|<span data-ttu-id="0a406-114">Auf Methoden können Attribute angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="0a406-114">Attribute can be applied to a method.</span></span>|  
|`catProperty`|<span data-ttu-id="0a406-115">Auf Eigenschaften können Attribute angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="0a406-115">Attribute can be applied to a property.</span></span>|  
|`catField`|<span data-ttu-id="0a406-116">Auf Felder können Attribute angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="0a406-116">Attribute can be applied to a field.</span></span>|  
|`catEvent`|<span data-ttu-id="0a406-117">Auf Ereignisse können Attribute angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="0a406-117">Attribute can be applied to an event.</span></span>|  
|`catInterface`|<span data-ttu-id="0a406-118">Auf Schnittstellen können Attribute angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="0a406-118">Attribute can be applied to an interface.</span></span>|  
|`catParameter`|<span data-ttu-id="0a406-119">Auf Parameter können Attribute angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="0a406-119">Attribute can be applied to a parameter.</span></span>|  
|`catDelegate`|<span data-ttu-id="0a406-120">Auf Delegaten können Attribute angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="0a406-120">Attribute can be applied to a delegate.</span></span>|  
|`catGenericParameter`|<span data-ttu-id="0a406-121">Auf generische Parameter können Attribute angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="0a406-121">Attribute can be applied to a generic parameter.</span></span>|  
|`catAll`|<span data-ttu-id="0a406-122">Auf jedes Anwendungselement können Attribute angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="0a406-122">Attribute can be applied to any application element.</span></span>|  
|`catClassMembers`|<span data-ttu-id="0a406-123">Das Attribut kann auf einen Member einer Klasse angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="0a406-123">Attribute can be applied to a member of a class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0a406-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0a406-124">Remarks</span></span>  

 <span data-ttu-id="0a406-125">Die `CorAttributeTargets` Enumerationswerte können mit einer bitweisen OR-Operation kombiniert werden, um die bevorzugte Kombination zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="0a406-125">The `CorAttributeTargets` enumeration values can be combined with a bitwise OR operation to get the preferred combination.</span></span>  
  
 <span data-ttu-id="0a406-126">Der entspricht `CorAttributeTargets` der verwalteten <xref:System.AttributeTargets?displayProperty=nameWithType> Enumeration.</span><span class="sxs-lookup"><span data-stu-id="0a406-126">The `CorAttributeTargets` parallels the managed <xref:System.AttributeTargets?displayProperty=nameWithType> enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a406-127">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="0a406-127">Requirements</span></span>  

 <span data-ttu-id="0a406-128">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0a406-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a406-129">**Header:** Corhdr. h</span><span class="sxs-lookup"><span data-stu-id="0a406-129">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="0a406-130">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a406-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a406-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0a406-131">See also</span></span>

- [<span data-ttu-id="0a406-132">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="0a406-132">Metadata Enumerations</span></span>](metadata-enumerations.md)
