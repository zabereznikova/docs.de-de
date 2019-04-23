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
ms.openlocfilehash: 15b1f6be2dac6bc7566852791ac22e495949521c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59179625"
---
# <a name="corserializationtype-enumeration"></a><span data-ttu-id="9e051-102">CorSerializationType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="9e051-102">CorSerializationType Enumeration</span></span>
<span data-ttu-id="9e051-103">Gibt an, wie ein Objekt von der common Language Runtime serialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="9e051-103">Specifies how an object is serialized by the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e051-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9e051-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="9e051-105">Member</span><span class="sxs-lookup"><span data-stu-id="9e051-105">Members</span></span>  
  
|<span data-ttu-id="9e051-106">Member</span><span class="sxs-lookup"><span data-stu-id="9e051-106">Member</span></span>|<span data-ttu-id="9e051-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9e051-107">Description</span></span>|  
|------------|-----------------|  
|`SERIALIZATION_TYPE_UNDEFINED`|<span data-ttu-id="9e051-108">Serialisierung des Objekts ist nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="9e051-108">Serialization of the object is undefined.</span></span>|  
|`SERIALIZATION_TYPE_BOOLEAN`|<span data-ttu-id="9e051-109">Das Objekt wird als einem Boolean-Typ serialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="9e051-109">Object is serialized as a Boolean type</span></span>|  
|`SERIALIZATION_TYPE_CHAR`|<span data-ttu-id="9e051-110">Das Objekt wird als ein Zeichentyp serialisiert.</span><span class="sxs-lookup"><span data-stu-id="9e051-110">Object is serialized as a character type.</span></span>|  
|`SERIALIZATION_TYPE_I1`|<span data-ttu-id="9e051-111">Das Objekt wird als eine 1-Byte-Ganzzahl mit Vorzeichen serialisiert.</span><span class="sxs-lookup"><span data-stu-id="9e051-111">Object is serialized as a signed 1-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_U1`|<span data-ttu-id="9e051-112">Das Objekt wird als eine 1-Byte-Ganzzahl ohne Vorzeichen serialisiert.</span><span class="sxs-lookup"><span data-stu-id="9e051-112">Object is serialized as an unsigned 1-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_I2`|<span data-ttu-id="9e051-113">Das Objekt wird als eine 2-Byte-Ganzzahl mit Vorzeichen serialisiert.</span><span class="sxs-lookup"><span data-stu-id="9e051-113">Object is serialized as a signed 2-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_U2`|<span data-ttu-id="9e051-114">Das Objekt wird als eine 2-Byte-Ganzzahl ohne Vorzeichen serialisiert.</span><span class="sxs-lookup"><span data-stu-id="9e051-114">Object is serialized as an unsigned 2-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_I4`|<span data-ttu-id="9e051-115">Objekt wird als ein 4-Byte-Ganzzahl mit Vorzeichen serialisiert.</span><span class="sxs-lookup"><span data-stu-id="9e051-115">Object is serialized as a signed 4-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_U4`|<span data-ttu-id="9e051-116">Das Objekt wird als eine 4-Byte-Ganzzahl ohne Vorzeichen serialisiert.</span><span class="sxs-lookup"><span data-stu-id="9e051-116">Object is serialized as an unsigned 4-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_I8`|<span data-ttu-id="9e051-117">Das Objekt wird als eine 8-Byte-Ganzzahl mit Vorzeichen serialisiert.</span><span class="sxs-lookup"><span data-stu-id="9e051-117">Object is serialized as a signed 8-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_U8`|<span data-ttu-id="9e051-118">Das Objekt wird als eine 8-Byte-Ganzzahl ohne Vorzeichen serialisiert.</span><span class="sxs-lookup"><span data-stu-id="9e051-118">Object is serialized as an unsigned 8-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_R4`|<span data-ttu-id="9e051-119">Objekt wird als ein 4-Byte-Gleitkommazahl serialisiert.</span><span class="sxs-lookup"><span data-stu-id="9e051-119">Object is serialized as a 4-byte floating point.</span></span>|  
|`SERIALIZATION_TYPE_R8`|<span data-ttu-id="9e051-120">Objekt wird als eine 8-Byte-Gleitkommazahl serialisiert.</span><span class="sxs-lookup"><span data-stu-id="9e051-120">Object is serialized as an 8-byte floating point.</span></span>|  
|`SERIALIZATION_TYPE_STRING`|<span data-ttu-id="9e051-121">Das Objekt wird als ein System.String-Typ serialisiert.</span><span class="sxs-lookup"><span data-stu-id="9e051-121">Object is serialized as a System.String type.</span></span>|  
|`SERIALIZATION_TYPE_SZARRAY`|<span data-ttu-id="9e051-122">Objekt wird serialisiert, wie ein eindimensionales, keine untere Begrenzung-Array.</span><span class="sxs-lookup"><span data-stu-id="9e051-122">Object is serialized as a single-dimensional, zero lower-bound array.</span></span>|  
|`SERIALIZATION_TYPE_TYPE`|<span data-ttu-id="9e051-123">Objekt wird als generischer Typ serialisiert.</span><span class="sxs-lookup"><span data-stu-id="9e051-123">Object is serialized as a generic type.</span></span>|  
|`SERIALIZATION_TYPE_TAGGED_OBJECT`|<span data-ttu-id="9e051-124">Objekt wird als markierte Objekt serialisiert.</span><span class="sxs-lookup"><span data-stu-id="9e051-124">Object is serialized as a tagged object.</span></span>|  
|`SERIALIZATION_TYPE_FIELD`|<span data-ttu-id="9e051-125">Objekt wird als Feld serialisiert.</span><span class="sxs-lookup"><span data-stu-id="9e051-125">Object is serialized as a field.</span></span>|  
|`SERIALIZATION_TYPE_PROPERTY`|<span data-ttu-id="9e051-126">Objekt wird als Eigenschaft serialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="9e051-126">Object is serialized as a property.</span></span>|  
|`SERIALIZATION_TYPE_ENUM`|<span data-ttu-id="9e051-127">Objekt wird als eine Enumeration serialisiert.</span><span class="sxs-lookup"><span data-stu-id="9e051-127">Object is serialized as an enumeration.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9e051-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9e051-128">Requirements</span></span>  
 <span data-ttu-id="9e051-129">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e051-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e051-130">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="9e051-130">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="9e051-131">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e051-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e051-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9e051-132">See also</span></span>

- [<span data-ttu-id="9e051-133">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="9e051-133">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
