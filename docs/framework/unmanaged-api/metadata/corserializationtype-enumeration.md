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
ms.openlocfilehash: e9c9674bfe0e5a8006a4881e103b633ee8f2af1d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706050"
---
# <a name="corserializationtype-enumeration"></a><span data-ttu-id="ce17c-102">CorSerializationType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="ce17c-102">CorSerializationType Enumeration</span></span>

<span data-ttu-id="ce17c-103">Gibt an, wie ein Objekt vom Common Language Runtime serialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="ce17c-103">Specifies how an object is serialized by the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce17c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ce17c-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="ce17c-105">Member</span><span class="sxs-lookup"><span data-stu-id="ce17c-105">Members</span></span>  
  
|<span data-ttu-id="ce17c-106">Member</span><span class="sxs-lookup"><span data-stu-id="ce17c-106">Member</span></span>|<span data-ttu-id="ce17c-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ce17c-107">Description</span></span>|  
|------------|-----------------|  
|`SERIALIZATION_TYPE_UNDEFINED`|<span data-ttu-id="ce17c-108">Die Serialisierung des Objekts ist nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="ce17c-108">Serialization of the object is undefined.</span></span>|  
|`SERIALIZATION_TYPE_BOOLEAN`|<span data-ttu-id="ce17c-109">Das Objekt wird als boolescher Typ serialisiert.</span><span class="sxs-lookup"><span data-stu-id="ce17c-109">Object is serialized as a Boolean type</span></span>|  
|`SERIALIZATION_TYPE_CHAR`|<span data-ttu-id="ce17c-110">Das Objekt wird als Zeichentyp serialisiert.</span><span class="sxs-lookup"><span data-stu-id="ce17c-110">Object is serialized as a character type.</span></span>|  
|`SERIALIZATION_TYPE_I1`|<span data-ttu-id="ce17c-111">Das Objekt wird als 1-Byte-Ganzzahl mit Vorzeichen serialisiert.</span><span class="sxs-lookup"><span data-stu-id="ce17c-111">Object is serialized as a signed 1-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_U1`|<span data-ttu-id="ce17c-112">Das Objekt wird als 1-Byte-Ganzzahl ohne Vorzeichen serialisiert.</span><span class="sxs-lookup"><span data-stu-id="ce17c-112">Object is serialized as an unsigned 1-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_I2`|<span data-ttu-id="ce17c-113">Das Objekt wird als eine ganze 2-Byte-Ganzzahl mit Vorzeichen serialisiert.</span><span class="sxs-lookup"><span data-stu-id="ce17c-113">Object is serialized as a signed 2-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_U2`|<span data-ttu-id="ce17c-114">Das Objekt wird als ganze 2-Byte-Ganzzahl ohne Vorzeichen serialisiert.</span><span class="sxs-lookup"><span data-stu-id="ce17c-114">Object is serialized as an unsigned 2-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_I4`|<span data-ttu-id="ce17c-115">Das Objekt wird als eine ganze 4-Byte-Ganzzahl mit Vorzeichen serialisiert.</span><span class="sxs-lookup"><span data-stu-id="ce17c-115">Object is serialized as a signed 4-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_U4`|<span data-ttu-id="ce17c-116">Das Objekt wird als ganze 4-Byte-Ganzzahl ohne Vorzeichen serialisiert.</span><span class="sxs-lookup"><span data-stu-id="ce17c-116">Object is serialized as an unsigned 4-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_I8`|<span data-ttu-id="ce17c-117">Das Objekt wird als ganze 8-Byte-Ganzzahl mit Vorzeichen serialisiert.</span><span class="sxs-lookup"><span data-stu-id="ce17c-117">Object is serialized as a signed 8-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_U8`|<span data-ttu-id="ce17c-118">Das Objekt wird als ganze 8-Byte-Ganzzahl ohne Vorzeichen serialisiert.</span><span class="sxs-lookup"><span data-stu-id="ce17c-118">Object is serialized as an unsigned 8-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_R4`|<span data-ttu-id="ce17c-119">Das Objekt wird als 4-Byte-Gleit Komma Wert serialisiert.</span><span class="sxs-lookup"><span data-stu-id="ce17c-119">Object is serialized as a 4-byte floating point.</span></span>|  
|`SERIALIZATION_TYPE_R8`|<span data-ttu-id="ce17c-120">Das Objekt wird als 8-Byte-Gleit Komma Wert serialisiert.</span><span class="sxs-lookup"><span data-stu-id="ce17c-120">Object is serialized as an 8-byte floating point.</span></span>|  
|`SERIALIZATION_TYPE_STRING`|<span data-ttu-id="ce17c-121">Das Objekt wird als System. String-Typ serialisiert.</span><span class="sxs-lookup"><span data-stu-id="ce17c-121">Object is serialized as a System.String type.</span></span>|  
|`SERIALIZATION_TYPE_SZARRAY`|<span data-ttu-id="ce17c-122">Das Objekt wird als eindimensionales und NULL-Array mit niedriger Grenze serialisiert.</span><span class="sxs-lookup"><span data-stu-id="ce17c-122">Object is serialized as a single-dimensional, zero lower-bound array.</span></span>|  
|`SERIALIZATION_TYPE_TYPE`|<span data-ttu-id="ce17c-123">Das Objekt wird als generischer Typ serialisiert.</span><span class="sxs-lookup"><span data-stu-id="ce17c-123">Object is serialized as a generic type.</span></span>|  
|`SERIALIZATION_TYPE_TAGGED_OBJECT`|<span data-ttu-id="ce17c-124">Das Objekt wird als gemarkigtes Objekt serialisiert.</span><span class="sxs-lookup"><span data-stu-id="ce17c-124">Object is serialized as a tagged object.</span></span>|  
|`SERIALIZATION_TYPE_FIELD`|<span data-ttu-id="ce17c-125">Das Objekt wird als Feld serialisiert.</span><span class="sxs-lookup"><span data-stu-id="ce17c-125">Object is serialized as a field.</span></span>|  
|`SERIALIZATION_TYPE_PROPERTY`|<span data-ttu-id="ce17c-126">Das Objekt wird als Eigenschaft serialisiert.</span><span class="sxs-lookup"><span data-stu-id="ce17c-126">Object is serialized as a property.</span></span>|  
|`SERIALIZATION_TYPE_ENUM`|<span data-ttu-id="ce17c-127">Das Objekt wird als Enumeration serialisiert.</span><span class="sxs-lookup"><span data-stu-id="ce17c-127">Object is serialized as an enumeration.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ce17c-128">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ce17c-128">Requirements</span></span>  

 <span data-ttu-id="ce17c-129">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce17c-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce17c-130">**Header:** Corhdr. h</span><span class="sxs-lookup"><span data-stu-id="ce17c-130">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="ce17c-131">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce17c-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce17c-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ce17c-132">See also</span></span>

- [<span data-ttu-id="ce17c-133">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="ce17c-133">Metadata Enumerations</span></span>](metadata-enumerations.md)
