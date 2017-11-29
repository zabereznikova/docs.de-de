---
title: CorFieldAttr-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorFieldAttr
api_location: mscoree.dll
api_type: COM
f1_keywords: CorFieldAttr
helpviewer_keywords: CorFieldAttr enumeration [.NET Framework metadata]
ms.assetid: 6ae2c4be-212c-4e74-9288-40a11dc26522
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b199764ea0fb2d02b01d7cf04d1fa8fad743109f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="corfieldattr-enumeration"></a><span data-ttu-id="18011-102">CorFieldAttr-Enumeration</span><span class="sxs-lookup"><span data-stu-id="18011-102">CorFieldAttr Enumeration</span></span>
<span data-ttu-id="18011-103">Enthält Werte, die die Metadaten über ein Feld beschreiben.</span><span class="sxs-lookup"><span data-stu-id="18011-103">Contains values that describe metadata about a field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18011-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="18011-104">Syntax</span></span>  
  
```  
typedef enum CorFieldAttr {  
  
    fdFieldAccessMask           =   0x0007,  
    fdPrivateScope              =   0x0000,  
    fdPrivate                   =   0x0001,  
    fdFamANDAssem               =   0x0002,  
    fdAssembly                  =   0x0003,  
    fdFamily                    =   0x0004,  
    fdFamORAssem                =   0x0005,  
    fdPublic                    =   0x0006,  
  
    fdStatic                    =   0x0010,  
    fdInitOnly                  =   0x0020,  
    fdLiteral                   =   0x0040,  
    fdNotSerialized             =   0x0080,  
  
    fdSpecialName               =   0x0200,  
  
    fdPinvokeImpl               =   0x2000,  
  
    fdReservedMask              =   0x9500,  
    fdRTSpecialName             =   0x0400,  
    fdHasFieldMarshal           =   0x1000,  
    fdHasDefault                =   0x8000,  
    fdHasFieldRVA               =   0x0100  
  
} CorFieldAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="18011-105">Member</span><span class="sxs-lookup"><span data-stu-id="18011-105">Members</span></span>  
  
|<span data-ttu-id="18011-106">Member</span><span class="sxs-lookup"><span data-stu-id="18011-106">Member</span></span>|<span data-ttu-id="18011-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="18011-107">Description</span></span>|  
|------------|-----------------|  
|`fdFieldAccessMask`|<span data-ttu-id="18011-108">Gibt Informationen über Eingabehilfen an.</span><span class="sxs-lookup"><span data-stu-id="18011-108">Specifies accessibility information.</span></span>|  
|`fdPrivateScope`|<span data-ttu-id="18011-109">Gibt an, dass auf das Feld nicht verwiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="18011-109">Specifies that the field cannot be referenced.</span></span>|  
|`fdPrivate`|<span data-ttu-id="18011-110">Gibt an, dass das Feld nur einen übergeordneten Typ zugänglich ist.</span><span class="sxs-lookup"><span data-stu-id="18011-110">Specifies that the field is accessible only by its parent type.</span></span>|  
|`fdFamANDAssem`|<span data-ttu-id="18011-111">Gibt an, dass das Feld von abgeleiteten Klassen in seiner Assembly zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="18011-111">Specifies that the field is accessible by derived classes in its assembly.</span></span>|  
|`fdAssembly`|<span data-ttu-id="18011-112">Gibt an, dass das Feld von allen Typen in seiner Assembly zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="18011-112">Specifies that the field is accessible by all types in its assembly.</span></span>|  
|`fdFamily`|<span data-ttu-id="18011-113">Gibt an, dass das Feld nur anhand des Typs zugegriffen werden kann und Klassen abgeleitete.</span><span class="sxs-lookup"><span data-stu-id="18011-113">Specifies that the field is accessible only by its type and derived classes.</span></span>|  
|`fdFamORAssem`|<span data-ttu-id="18011-114">Gibt an, dass das Feld von abgeleiteten Klassen und alle Typen in seiner Assembly zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="18011-114">Specifies that the field is accessible by derived classes and by all types in its assembly.</span></span>|  
|`fdPublic`|<span data-ttu-id="18011-115">Gibt an, dass das Feld alle Typen mit Sichtbarkeit dieses Bereichs zugänglich ist.</span><span class="sxs-lookup"><span data-stu-id="18011-115">Specifies that the field is accessible by all types with visibility of this scope.</span></span>|  
|`fdStatic`|<span data-ttu-id="18011-116">Gibt an, dass das Feld ein Member dieses Typs statt einen Instanzmember ist.</span><span class="sxs-lookup"><span data-stu-id="18011-116">Specifies that the field is a member of its type rather than an instance member.</span></span>|  
|`fdInitOnly`|<span data-ttu-id="18011-117">Gibt an, dass das Feld nach der Initialisierung nicht geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="18011-117">Specifies that the field cannot be changed after it is initialized.</span></span>|  
|`fdLiteral`|<span data-ttu-id="18011-118">Gibt an, dass der Wert des Felds eine Kompilierzeitkonstante.</span><span class="sxs-lookup"><span data-stu-id="18011-118">Specifies that the field value is a compile-time constant.</span></span>|  
|`fdNotSerialized`|<span data-ttu-id="18011-119">Gibt an, dass das Feld nicht serialisiert wird, wenn dessen Typ Remote ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="18011-119">Specifies that the field is not serialized when its type is remoted.</span></span>|  
|`fdSpecialName`|<span data-ttu-id="18011-120">Gibt an, dass das Feld besondere und seinen Namen wird beschrieben, wie.</span><span class="sxs-lookup"><span data-stu-id="18011-120">Specifies that the field is special, and that its name describes how.</span></span>|  
|`fdPinvokeImpl`|<span data-ttu-id="18011-121">Gibt an, dass die Implementierung des Felds über PInvoke weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="18011-121">Specifies that the field implementation is forwarded through PInvoke.</span></span>|  
|`fdReservedMask`|<span data-ttu-id="18011-122">Reserviert für interne Verwendung durch die common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="18011-122">Reserved for internal use by the common language runtime.</span></span>|  
|`fdRTSpecialName`|<span data-ttu-id="18011-123">Gibt an, dass die common Language Runtime-Metadaten über interne APIs überprüfen soll, die die Codierung des Namens.</span><span class="sxs-lookup"><span data-stu-id="18011-123">Specifies that the common language runtime metadata internal APIs should check the encoding of the name.</span></span>|  
|`fdHasFieldMarshal`|<span data-ttu-id="18011-124">Gibt an, dass das Feld Marshallinginformationen enthält.</span><span class="sxs-lookup"><span data-stu-id="18011-124">Specifies that the field contains marshaling information.</span></span>|  
|`fdHasDefault`|<span data-ttu-id="18011-125">Gibt an, dass das Feld einen Standardwert besitzt.</span><span class="sxs-lookup"><span data-stu-id="18011-125">Specifies that the field has a default value.</span></span>|  
|`fdHasFieldRVA`|<span data-ttu-id="18011-126">Gibt an, dass das Feld eine relative virtuelle Adresse verfügt.</span><span class="sxs-lookup"><span data-stu-id="18011-126">Specifies that the field has a relative virtual address.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="18011-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="18011-127">Requirements</span></span>  
 <span data-ttu-id="18011-128">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="18011-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18011-129">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="18011-129">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="18011-130">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18011-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18011-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="18011-131">See Also</span></span>  
 [<span data-ttu-id="18011-132">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="18011-132">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
