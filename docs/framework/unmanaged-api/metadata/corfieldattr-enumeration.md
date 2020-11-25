---
title: CorFieldAttr-Enumeration
ms.date: 03/30/2017
api_name:
- CorFieldAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorFieldAttr
helpviewer_keywords:
- CorFieldAttr enumeration [.NET Framework metadata]
ms.assetid: 6ae2c4be-212c-4e74-9288-40a11dc26522
topic_type:
- apiref
ms.openlocfilehash: 4e40f684cc1578672cb8ff474972ce9cdc39efb2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718825"
---
# <a name="corfieldattr-enumeration"></a><span data-ttu-id="518f8-102">CorFieldAttr-Enumeration</span><span class="sxs-lookup"><span data-stu-id="518f8-102">CorFieldAttr Enumeration</span></span>

<span data-ttu-id="518f8-103">Enthält Werte, die die Metadaten über ein Feld beschreiben.</span><span class="sxs-lookup"><span data-stu-id="518f8-103">Contains values that describe metadata about a field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="518f8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="518f8-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="518f8-105">Member</span><span class="sxs-lookup"><span data-stu-id="518f8-105">Members</span></span>  
  
|<span data-ttu-id="518f8-106">Member</span><span class="sxs-lookup"><span data-stu-id="518f8-106">Member</span></span>|<span data-ttu-id="518f8-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="518f8-107">Description</span></span>|  
|------------|-----------------|  
|`fdFieldAccessMask`|<span data-ttu-id="518f8-108">Gibt Barrierefreiheits Informationen an.</span><span class="sxs-lookup"><span data-stu-id="518f8-108">Specifies accessibility information.</span></span>|  
|`fdPrivateScope`|<span data-ttu-id="518f8-109">Gibt an, dass auf das Feld nicht verwiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="518f8-109">Specifies that the field cannot be referenced.</span></span>|  
|`fdPrivate`|<span data-ttu-id="518f8-110">Gibt an, dass auf das Feld nur über den übergeordneten Typ zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="518f8-110">Specifies that the field is accessible only by its parent type.</span></span>|  
|`fdFamANDAssem`|<span data-ttu-id="518f8-111">Gibt an, dass abgeleitete Klassen in der Assembly auf das Feld zugreifen.</span><span class="sxs-lookup"><span data-stu-id="518f8-111">Specifies that the field is accessible by derived classes in its assembly.</span></span>|  
|`fdAssembly`|<span data-ttu-id="518f8-112">Gibt an, dass auf das Feld für alle Typen in der Assembly zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="518f8-112">Specifies that the field is accessible by all types in its assembly.</span></span>|  
|`fdFamily`|<span data-ttu-id="518f8-113">Gibt an, dass auf das Feld nur über den Typ und die abgeleiteten Klassen zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="518f8-113">Specifies that the field is accessible only by its type and derived classes.</span></span>|  
|`fdFamORAssem`|<span data-ttu-id="518f8-114">Gibt an, dass auf das Feld von abgeleiteten Klassen und von allen Typen in der Assembly zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="518f8-114">Specifies that the field is accessible by derived classes and by all types in its assembly.</span></span>|  
|`fdPublic`|<span data-ttu-id="518f8-115">Gibt an, dass auf das Feld alle Typen mit Sichtbarkeit dieses Bereichs zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="518f8-115">Specifies that the field is accessible by all types with visibility of this scope.</span></span>|  
|`fdStatic`|<span data-ttu-id="518f8-116">Gibt an, dass das Feld ein Member seines Typs und kein Instanzmember ist.</span><span class="sxs-lookup"><span data-stu-id="518f8-116">Specifies that the field is a member of its type rather than an instance member.</span></span>|  
|`fdInitOnly`|<span data-ttu-id="518f8-117">Gibt an, dass das Feld nicht geändert werden kann, nachdem es initialisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="518f8-117">Specifies that the field cannot be changed after it is initialized.</span></span>|  
|`fdLiteral`|<span data-ttu-id="518f8-118">Gibt an, dass der Feldwert eine Kompilierzeit Konstante ist.</span><span class="sxs-lookup"><span data-stu-id="518f8-118">Specifies that the field value is a compile-time constant.</span></span>|  
|`fdNotSerialized`|<span data-ttu-id="518f8-119">Gibt an, dass das Feld nicht serialisiert wird, wenn der Typ Remote ist.</span><span class="sxs-lookup"><span data-stu-id="518f8-119">Specifies that the field is not serialized when its type is remoted.</span></span>|  
|`fdSpecialName`|<span data-ttu-id="518f8-120">Gibt an, dass es sich um ein spezielles Feld handelt und wie der Name beschreibt.</span><span class="sxs-lookup"><span data-stu-id="518f8-120">Specifies that the field is special, and that its name describes how.</span></span>|  
|`fdPinvokeImpl`|<span data-ttu-id="518f8-121">Gibt an, dass die Feld Implementierung über PInvoke weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="518f8-121">Specifies that the field implementation is forwarded through PInvoke.</span></span>|  
|`fdReservedMask`|<span data-ttu-id="518f8-122">Reserviert für die interne Verwendung durch den Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="518f8-122">Reserved for internal use by the common language runtime.</span></span>|  
|`fdRTSpecialName`|<span data-ttu-id="518f8-123">Gibt an, dass die Common Language Runtime Metadaten-internen APIs die Codierung des Namens überprüfen sollen.</span><span class="sxs-lookup"><span data-stu-id="518f8-123">Specifies that the common language runtime metadata internal APIs should check the encoding of the name.</span></span>|  
|`fdHasFieldMarshal`|<span data-ttu-id="518f8-124">Gibt an, dass das Feld Marshallinginformationen enthält.</span><span class="sxs-lookup"><span data-stu-id="518f8-124">Specifies that the field contains marshaling information.</span></span>|  
|`fdHasDefault`|<span data-ttu-id="518f8-125">Gibt an, dass das Feld einen Standardwert besitzt.</span><span class="sxs-lookup"><span data-stu-id="518f8-125">Specifies that the field has a default value.</span></span>|  
|`fdHasFieldRVA`|<span data-ttu-id="518f8-126">Gibt an, dass das Feld über eine relative virtuelle Adresse verfügt.</span><span class="sxs-lookup"><span data-stu-id="518f8-126">Specifies that the field has a relative virtual address.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="518f8-127">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="518f8-127">Requirements</span></span>  

 <span data-ttu-id="518f8-128">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="518f8-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="518f8-129">**Header:** Corhdr. h</span><span class="sxs-lookup"><span data-stu-id="518f8-129">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="518f8-130">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="518f8-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="518f8-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="518f8-131">See also</span></span>

- [<span data-ttu-id="518f8-132">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="518f8-132">Metadata Enumerations</span></span>](metadata-enumerations.md)
