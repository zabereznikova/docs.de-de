---
title: CorSerializationType-Enumeration
ms.date: 03/30/2017
api_name:
- CorSerializationType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSerializationType
helpviewer_keywords:
- CorSerializationType enumeration [.NET Framework metadata]
ms.assetid: 6b1fcd11-c7fb-4be2-8910-abc862d4caf4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4959d595030df476f5554841c2ae3c73a86a2c31
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33446658"
---
# <a name="corserializationtype-enumeration"></a><span data-ttu-id="7944e-102">CorSerializationType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="7944e-102">CorSerializationType Enumeration</span></span>
<span data-ttu-id="7944e-103">Gibt an, wie ein Objekt von der common Language Runtime serialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="7944e-103">Specifies how an object is serialized by the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7944e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7944e-104">Syntax</span></span>  
  
```  
typedef enum CorSerializationType {  
  
    SERIALIZATION_TYPE_UNDEFINED     = 0,  
    SERIALIZATION_TYPE_BOOLEAN       = ELEMENT_TYPE_BOOLEAN,  
    SERIALIZATION_TYPE_CHAR          = ELEMENT_TYPE_CHAR,  
    SERIALIZATION_TYPE_I1            = ELEMENT_TYPE_I1,  
    SERIALIZATION_TYPE_U1            = ELEMENT_TYPE_U1,  
    SERIALIZATION_TYPE_I2            = ELEMENT_TYPE_I2,  
    SERIALIZATION_TYPE_U2            = ELEMENT_TYPE_U2,  
    SERIALIZATION_TYPE_I4            = ELEMENT_TYPE_I4,  
    SERIALIZATION_TYPE_U4            = ELEMENT_TYPE_U4,  
    SERIALIZATION_TYPE_I8            = ELEMENT_TYPE_I8,  
    SERIALIZATION_TYPE_U8            = ELEMENT_TYPE_U8,  
    SERIALIZATION_TYPE_R4            = ELEMENT_TYPE_R4,  
    SERIALIZATION_TYPE_R8            = ELEMENT_TYPE_R8,  
    SERIALIZATION_TYPE_STRING        = ELEMENT_TYPE_STRING,  
    SERIALIZATION_TYPE_SZARRAY       = ELEMENT_TYPE_SZARRAY,  
    SERIALIZATION_TYPE_TYPE          = 0x50,  
    SERIALIZATION_TYPE_TAGGED_OBJECT = 0x51,  
    SERIALIZATION_TYPE_FIELD         = 0x53,  
    SERIALIZATION_TYPE_PROPERTY      = 0x54,  
    SERIALIZATION_TYPE_ENUM          = 0x55  
  
} CorSerializationType;  
```  
  
## <a name="members"></a><span data-ttu-id="7944e-105">Member</span><span class="sxs-lookup"><span data-stu-id="7944e-105">Members</span></span>  
  
|<span data-ttu-id="7944e-106">Member</span><span class="sxs-lookup"><span data-stu-id="7944e-106">Member</span></span>|<span data-ttu-id="7944e-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7944e-107">Description</span></span>|  
|------------|-----------------|  
|`SERIALIZATION_TYPE_UNDEFINED`|<span data-ttu-id="7944e-108">Die Serialisierung des Objekts ist nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="7944e-108">Serialization of the object is undefined.</span></span>|  
|`SERIALIZATION_TYPE_BOOLEAN`|<span data-ttu-id="7944e-109">Das Objekt wird als einem Boolean-Typ serialisiert.</span><span class="sxs-lookup"><span data-stu-id="7944e-109">Object is serialized as a Boolean type</span></span>|  
|`SERIALIZATION_TYPE_CHAR`|<span data-ttu-id="7944e-110">Das Objekt wird als ein Zeichentyp serialisiert.</span><span class="sxs-lookup"><span data-stu-id="7944e-110">Object is serialized as a character type.</span></span>|  
|`SERIALIZATION_TYPE_I1`|<span data-ttu-id="7944e-111">Das Objekt wird als eine 1-Byte-Ganzzahl mit Vorzeichen serialisiert.</span><span class="sxs-lookup"><span data-stu-id="7944e-111">Object is serialized as a signed 1-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_U1`|<span data-ttu-id="7944e-112">Das Objekt wird als eine 1-Byte-Ganzzahl ohne Vorzeichen serialisiert.</span><span class="sxs-lookup"><span data-stu-id="7944e-112">Object is serialized as an unsigned 1-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_I2`|<span data-ttu-id="7944e-113">Das Objekt wird als eine 2-Byte-Ganzzahl mit Vorzeichen serialisiert.</span><span class="sxs-lookup"><span data-stu-id="7944e-113">Object is serialized as a signed 2-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_U2`|<span data-ttu-id="7944e-114">Das Objekt wird als eine 2-Byte-Ganzzahl ohne Vorzeichen serialisiert.</span><span class="sxs-lookup"><span data-stu-id="7944e-114">Object is serialized as an unsigned 2-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_I4`|<span data-ttu-id="7944e-115">Objekt wird als ein 4-Byte-Ganzzahl mit Vorzeichen serialisiert.</span><span class="sxs-lookup"><span data-stu-id="7944e-115">Object is serialized as a signed 4-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_U4`|<span data-ttu-id="7944e-116">Das Objekt wird als ein 4-Byte-Ganzzahl ohne Vorzeichen serialisiert.</span><span class="sxs-lookup"><span data-stu-id="7944e-116">Object is serialized as an unsigned 4-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_I8`|<span data-ttu-id="7944e-117">Das Objekt wird als eine 8-Byte-Ganzzahl mit Vorzeichen serialisiert.</span><span class="sxs-lookup"><span data-stu-id="7944e-117">Object is serialized as a signed 8-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_U8`|<span data-ttu-id="7944e-118">Das Objekt wird als eine 8-Byte-Ganzzahl ohne Vorzeichen serialisiert.</span><span class="sxs-lookup"><span data-stu-id="7944e-118">Object is serialized as an unsigned 8-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_R4`|<span data-ttu-id="7944e-119">Objekt wird als ein 4-Byte-Gleitkommazahl serialisiert.</span><span class="sxs-lookup"><span data-stu-id="7944e-119">Object is serialized as a 4-byte floating point.</span></span>|  
|`SERIALIZATION_TYPE_R8`|<span data-ttu-id="7944e-120">Das Objekt wird als eine 8-Byte-Gleitkommazahl serialisiert.</span><span class="sxs-lookup"><span data-stu-id="7944e-120">Object is serialized as an 8-byte floating point.</span></span>|  
|`SERIALIZATION_TYPE_STRING`|<span data-ttu-id="7944e-121">Objekt wird als System.String-Typ serialisiert.</span><span class="sxs-lookup"><span data-stu-id="7944e-121">Object is serialized as a System.String type.</span></span>|  
|`SERIALIZATION_TYPE_SZARRAY`|<span data-ttu-id="7944e-122">Objekt wird serialisiert, wie ein eindimensionales, 0 (null) Untergrenze Array.</span><span class="sxs-lookup"><span data-stu-id="7944e-122">Object is serialized as a single-dimensional, zero lower-bound array.</span></span>|  
|`SERIALIZATION_TYPE_TYPE`|<span data-ttu-id="7944e-123">Objekt wird als generischer Typ serialisiert.</span><span class="sxs-lookup"><span data-stu-id="7944e-123">Object is serialized as a generic type.</span></span>|  
|`SERIALIZATION_TYPE_TAGGED_OBJECT`|<span data-ttu-id="7944e-124">Objekt wird als markiertes Objekt serialisiert.</span><span class="sxs-lookup"><span data-stu-id="7944e-124">Object is serialized as a tagged object.</span></span>|  
|`SERIALIZATION_TYPE_FIELD`|<span data-ttu-id="7944e-125">Objekt wird als Feld serialisiert.</span><span class="sxs-lookup"><span data-stu-id="7944e-125">Object is serialized as a field.</span></span>|  
|`SERIALIZATION_TYPE_PROPERTY`|<span data-ttu-id="7944e-126">Das Objekt wird als eine Eigenschaft serialisiert.</span><span class="sxs-lookup"><span data-stu-id="7944e-126">Object is serialized as a property.</span></span>|  
|`SERIALIZATION_TYPE_ENUM`|<span data-ttu-id="7944e-127">Das Objekt wird als eine Enumeration serialisiert.</span><span class="sxs-lookup"><span data-stu-id="7944e-127">Object is serialized as an enumeration.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7944e-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7944e-128">Requirements</span></span>  
 <span data-ttu-id="7944e-129">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7944e-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7944e-130">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="7944e-130">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="7944e-131">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7944e-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7944e-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7944e-132">See Also</span></span>  
 [<span data-ttu-id="7944e-133">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="7944e-133">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
