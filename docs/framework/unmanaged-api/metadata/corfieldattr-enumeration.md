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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 432e202eb8db105e8d56d3d36cdc8001bac5320c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62045941"
---
# <a name="corfieldattr-enumeration"></a><span data-ttu-id="192e0-102">CorFieldAttr-Enumeration</span><span class="sxs-lookup"><span data-stu-id="192e0-102">CorFieldAttr Enumeration</span></span>
<span data-ttu-id="192e0-103">Enthält Werte, die die Metadaten über ein Feld beschreiben.</span><span class="sxs-lookup"><span data-stu-id="192e0-103">Contains values that describe metadata about a field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="192e0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="192e0-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="192e0-105">Member</span><span class="sxs-lookup"><span data-stu-id="192e0-105">Members</span></span>  
  
|<span data-ttu-id="192e0-106">Member</span><span class="sxs-lookup"><span data-stu-id="192e0-106">Member</span></span>|<span data-ttu-id="192e0-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="192e0-107">Description</span></span>|  
|------------|-----------------|  
|`fdFieldAccessMask`|<span data-ttu-id="192e0-108">Gibt Informationen zur Barrierefreiheit an.</span><span class="sxs-lookup"><span data-stu-id="192e0-108">Specifies accessibility information.</span></span>|  
|`fdPrivateScope`|<span data-ttu-id="192e0-109">Gibt an, dass auf das Feld nicht verwiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="192e0-109">Specifies that the field cannot be referenced.</span></span>|  
|`fdPrivate`|<span data-ttu-id="192e0-110">Gibt an, dass das Feld nur von übergeordneten Typs zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="192e0-110">Specifies that the field is accessible only by its parent type.</span></span>|  
|`fdFamANDAssem`|<span data-ttu-id="192e0-111">Gibt an, dass das Feld von abgeleiteten Klassen in seiner Assembly zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="192e0-111">Specifies that the field is accessible by derived classes in its assembly.</span></span>|  
|`fdAssembly`|<span data-ttu-id="192e0-112">Gibt an, dass das Feld von allen Typen in seiner Assembly zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="192e0-112">Specifies that the field is accessible by all types in its assembly.</span></span>|  
|`fdFamily`|<span data-ttu-id="192e0-113">Gibt an, dass das Feld nur über den Typ ist und den abgeleiteten Klassen.</span><span class="sxs-lookup"><span data-stu-id="192e0-113">Specifies that the field is accessible only by its type and derived classes.</span></span>|  
|`fdFamORAssem`|<span data-ttu-id="192e0-114">Gibt an, dass das Feld von abgeleiteten Klassen und alle Typen in der Assembly zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="192e0-114">Specifies that the field is accessible by derived classes and by all types in its assembly.</span></span>|  
|`fdPublic`|<span data-ttu-id="192e0-115">Gibt an, dass das Feld von allen Typen mit Sichtbarkeit dieses Bereichs zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="192e0-115">Specifies that the field is accessible by all types with visibility of this scope.</span></span>|  
|`fdStatic`|<span data-ttu-id="192e0-116">Gibt an, dass das Feld ein Member dieses Typs kein Instanzmember.</span><span class="sxs-lookup"><span data-stu-id="192e0-116">Specifies that the field is a member of its type rather than an instance member.</span></span>|  
|`fdInitOnly`|<span data-ttu-id="192e0-117">Gibt an, dass das Feld kann nicht geändert werden, nach der Initialisierung.</span><span class="sxs-lookup"><span data-stu-id="192e0-117">Specifies that the field cannot be changed after it is initialized.</span></span>|  
|`fdLiteral`|<span data-ttu-id="192e0-118">Gibt an, dass der Wert des Felds eine Kompilierzeitkonstante.</span><span class="sxs-lookup"><span data-stu-id="192e0-118">Specifies that the field value is a compile-time constant.</span></span>|  
|`fdNotSerialized`|<span data-ttu-id="192e0-119">Gibt an, dass das Feld nicht serialisiert wird, wenn der Typ Remote übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="192e0-119">Specifies that the field is not serialized when its type is remoted.</span></span>|  
|`fdSpecialName`|<span data-ttu-id="192e0-120">Gibt an, dass das Feld spezielle ist und seinen Namen wird beschrieben, wie.</span><span class="sxs-lookup"><span data-stu-id="192e0-120">Specifies that the field is special, and that its name describes how.</span></span>|  
|`fdPinvokeImpl`|<span data-ttu-id="192e0-121">Gibt an, dass die Feld-Implementierung über PInvoke weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="192e0-121">Specifies that the field implementation is forwarded through PInvoke.</span></span>|  
|`fdReservedMask`|<span data-ttu-id="192e0-122">Durch die common Language Runtime können Sie für die interne Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="192e0-122">Reserved for internal use by the common language runtime.</span></span>|  
|`fdRTSpecialName`|<span data-ttu-id="192e0-123">Gibt an, dass die common Language Runtime-Metadaten über interne APIs überprüfen soll, die die Codierung mit dem Namen.</span><span class="sxs-lookup"><span data-stu-id="192e0-123">Specifies that the common language runtime metadata internal APIs should check the encoding of the name.</span></span>|  
|`fdHasFieldMarshal`|<span data-ttu-id="192e0-124">Gibt an, dass das Feld über Marshallinginformationen enthält.</span><span class="sxs-lookup"><span data-stu-id="192e0-124">Specifies that the field contains marshaling information.</span></span>|  
|`fdHasDefault`|<span data-ttu-id="192e0-125">Gibt an, dass das Feld einen Standardwert besitzt.</span><span class="sxs-lookup"><span data-stu-id="192e0-125">Specifies that the field has a default value.</span></span>|  
|`fdHasFieldRVA`|<span data-ttu-id="192e0-126">Gibt an, dass das Feld eine relative virtuelle Adresse.</span><span class="sxs-lookup"><span data-stu-id="192e0-126">Specifies that the field has a relative virtual address.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="192e0-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="192e0-127">Requirements</span></span>  
 <span data-ttu-id="192e0-128">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="192e0-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="192e0-129">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="192e0-129">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="192e0-130">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="192e0-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="192e0-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="192e0-131">See also</span></span>

- [<span data-ttu-id="192e0-132">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="192e0-132">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
