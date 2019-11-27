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
ms.openlocfilehash: 064374285216e9fb054b299937087f1ca7c351a4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432875"
---
# <a name="corserializationtype-enumeration"></a><span data-ttu-id="e7148-102">CorSerializationType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="e7148-102">CorSerializationType Enumeration</span></span>
<span data-ttu-id="e7148-103">Gibt an, wie ein Objekt vom Common Language Runtime serialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="e7148-103">Specifies how an object is serialized by the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7148-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e7148-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="e7148-105">Member</span><span class="sxs-lookup"><span data-stu-id="e7148-105">Members</span></span>  
  
|<span data-ttu-id="e7148-106">Member</span><span class="sxs-lookup"><span data-stu-id="e7148-106">Member</span></span>|<span data-ttu-id="e7148-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e7148-107">Description</span></span>|  
|------------|-----------------|  
|`SERIALIZATION_TYPE_UNDEFINED`|<span data-ttu-id="e7148-108">Die Serialisierung des Objekts ist nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="e7148-108">Serialization of the object is undefined.</span></span>|  
|`SERIALIZATION_TYPE_BOOLEAN`|<span data-ttu-id="e7148-109">Das Objekt wird als boolescher Typ serialisiert.</span><span class="sxs-lookup"><span data-stu-id="e7148-109">Object is serialized as a Boolean type</span></span>|  
|`SERIALIZATION_TYPE_CHAR`|<span data-ttu-id="e7148-110">Das Objekt wird als Zeichentyp serialisiert.</span><span class="sxs-lookup"><span data-stu-id="e7148-110">Object is serialized as a character type.</span></span>|  
|`SERIALIZATION_TYPE_I1`|<span data-ttu-id="e7148-111">Das Objekt wird als 1-Byte-Ganzzahl mit Vorzeichen serialisiert.</span><span class="sxs-lookup"><span data-stu-id="e7148-111">Object is serialized as a signed 1-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_U1`|<span data-ttu-id="e7148-112">Das Objekt wird als 1-Byte-Ganzzahl ohne Vorzeichen serialisiert.</span><span class="sxs-lookup"><span data-stu-id="e7148-112">Object is serialized as an unsigned 1-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_I2`|<span data-ttu-id="e7148-113">Das Objekt wird als eine ganze 2-Byte-Ganzzahl mit Vorzeichen serialisiert.</span><span class="sxs-lookup"><span data-stu-id="e7148-113">Object is serialized as a signed 2-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_U2`|<span data-ttu-id="e7148-114">Das Objekt wird als ganze 2-Byte-Ganzzahl ohne Vorzeichen serialisiert.</span><span class="sxs-lookup"><span data-stu-id="e7148-114">Object is serialized as an unsigned 2-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_I4`|<span data-ttu-id="e7148-115">Das Objekt wird als eine ganze 4-Byte-Ganzzahl mit Vorzeichen serialisiert.</span><span class="sxs-lookup"><span data-stu-id="e7148-115">Object is serialized as a signed 4-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_U4`|<span data-ttu-id="e7148-116">Das Objekt wird als ganze 4-Byte-Ganzzahl ohne Vorzeichen serialisiert.</span><span class="sxs-lookup"><span data-stu-id="e7148-116">Object is serialized as an unsigned 4-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_I8`|<span data-ttu-id="e7148-117">Das Objekt wird als ganze 8-Byte-Ganzzahl mit Vorzeichen serialisiert.</span><span class="sxs-lookup"><span data-stu-id="e7148-117">Object is serialized as a signed 8-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_U8`|<span data-ttu-id="e7148-118">Das Objekt wird als ganze 8-Byte-Ganzzahl ohne Vorzeichen serialisiert.</span><span class="sxs-lookup"><span data-stu-id="e7148-118">Object is serialized as an unsigned 8-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_R4`|<span data-ttu-id="e7148-119">Das Objekt wird als 4-Byte-Gleit Komma Wert serialisiert.</span><span class="sxs-lookup"><span data-stu-id="e7148-119">Object is serialized as a 4-byte floating point.</span></span>|  
|`SERIALIZATION_TYPE_R8`|<span data-ttu-id="e7148-120">Das Objekt wird als 8-Byte-Gleit Komma Wert serialisiert.</span><span class="sxs-lookup"><span data-stu-id="e7148-120">Object is serialized as an 8-byte floating point.</span></span>|  
|`SERIALIZATION_TYPE_STRING`|<span data-ttu-id="e7148-121">Das Objekt wird als System. String-Typ serialisiert.</span><span class="sxs-lookup"><span data-stu-id="e7148-121">Object is serialized as a System.String type.</span></span>|  
|`SERIALIZATION_TYPE_SZARRAY`|<span data-ttu-id="e7148-122">Das Objekt wird als eindimensionales und NULL-Array mit niedriger Grenze serialisiert.</span><span class="sxs-lookup"><span data-stu-id="e7148-122">Object is serialized as a single-dimensional, zero lower-bound array.</span></span>|  
|`SERIALIZATION_TYPE_TYPE`|<span data-ttu-id="e7148-123">Das Objekt wird als generischer Typ serialisiert.</span><span class="sxs-lookup"><span data-stu-id="e7148-123">Object is serialized as a generic type.</span></span>|  
|`SERIALIZATION_TYPE_TAGGED_OBJECT`|<span data-ttu-id="e7148-124">Das Objekt wird als gemarkigtes Objekt serialisiert.</span><span class="sxs-lookup"><span data-stu-id="e7148-124">Object is serialized as a tagged object.</span></span>|  
|`SERIALIZATION_TYPE_FIELD`|<span data-ttu-id="e7148-125">Das Objekt wird als Feld serialisiert.</span><span class="sxs-lookup"><span data-stu-id="e7148-125">Object is serialized as a field.</span></span>|  
|`SERIALIZATION_TYPE_PROPERTY`|<span data-ttu-id="e7148-126">Das Objekt wird als Eigenschaft serialisiert.</span><span class="sxs-lookup"><span data-stu-id="e7148-126">Object is serialized as a property.</span></span>|  
|`SERIALIZATION_TYPE_ENUM`|<span data-ttu-id="e7148-127">Das Objekt wird als Enumeration serialisiert.</span><span class="sxs-lookup"><span data-stu-id="e7148-127">Object is serialized as an enumeration.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e7148-128">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="e7148-128">Requirements</span></span>  
 <span data-ttu-id="e7148-129">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7148-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7148-130">**Header:** Corhdr. h</span><span class="sxs-lookup"><span data-stu-id="e7148-130">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="e7148-131">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7148-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7148-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e7148-132">See also</span></span>

- [<span data-ttu-id="e7148-133">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="e7148-133">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
