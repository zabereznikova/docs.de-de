---
title: CorSerializationType-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorSerializationType
api_location: mscoree.dll
api_type: COM
f1_keywords: CorSerializationType
helpviewer_keywords: CorSerializationType enumeration [.NET Framework metadata]
ms.assetid: 6b1fcd11-c7fb-4be2-8910-abc862d4caf4
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f6650298364f7deb60d553ee21f5028f5cbe7400
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="corserializationtype-enumeration"></a><span data-ttu-id="980ce-102">CorSerializationType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="980ce-102">CorSerializationType Enumeration</span></span>
<span data-ttu-id="980ce-103">Gibt an, wie ein Objekt von der common Language Runtime serialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="980ce-103">Specifies how an object is serialized by the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="980ce-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="980ce-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="980ce-105">Member</span><span class="sxs-lookup"><span data-stu-id="980ce-105">Members</span></span>  
  
|<span data-ttu-id="980ce-106">Member</span><span class="sxs-lookup"><span data-stu-id="980ce-106">Member</span></span>|<span data-ttu-id="980ce-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="980ce-107">Description</span></span>|  
|------------|-----------------|  
|`SERIALIZATION_TYPE_UNDEFINED`|<span data-ttu-id="980ce-108">Die Serialisierung des Objekts ist nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="980ce-108">Serialization of the object is undefined.</span></span>|  
|`SERIALIZATION_TYPE_BOOLEAN`|<span data-ttu-id="980ce-109">Das Objekt wird als einem Boolean-Typ serialisiert.</span><span class="sxs-lookup"><span data-stu-id="980ce-109">Object is serialized as a Boolean type</span></span>|  
|`SERIALIZATION_TYPE_CHAR`|<span data-ttu-id="980ce-110">Das Objekt wird als ein Zeichentyp serialisiert.</span><span class="sxs-lookup"><span data-stu-id="980ce-110">Object is serialized as a character type.</span></span>|  
|`SERIALIZATION_TYPE_I1`|<span data-ttu-id="980ce-111">Das Objekt wird als eine 1-Byte-Ganzzahl mit Vorzeichen serialisiert.</span><span class="sxs-lookup"><span data-stu-id="980ce-111">Object is serialized as a signed 1-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_U1`|<span data-ttu-id="980ce-112">Das Objekt wird als eine 1-Byte-Ganzzahl ohne Vorzeichen serialisiert.</span><span class="sxs-lookup"><span data-stu-id="980ce-112">Object is serialized as an unsigned 1-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_I2`|<span data-ttu-id="980ce-113">Das Objekt wird als eine 2-Byte-Ganzzahl mit Vorzeichen serialisiert.</span><span class="sxs-lookup"><span data-stu-id="980ce-113">Object is serialized as a signed 2-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_U2`|<span data-ttu-id="980ce-114">Das Objekt wird als eine 2-Byte-Ganzzahl ohne Vorzeichen serialisiert.</span><span class="sxs-lookup"><span data-stu-id="980ce-114">Object is serialized as an unsigned 2-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_I4`|<span data-ttu-id="980ce-115">Objekt wird als ein 4-Byte-Ganzzahl mit Vorzeichen serialisiert.</span><span class="sxs-lookup"><span data-stu-id="980ce-115">Object is serialized as a signed 4-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_U4`|<span data-ttu-id="980ce-116">Das Objekt wird als ein 4-Byte-Ganzzahl ohne Vorzeichen serialisiert.</span><span class="sxs-lookup"><span data-stu-id="980ce-116">Object is serialized as an unsigned 4-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_I8`|<span data-ttu-id="980ce-117">Das Objekt wird als eine 8-Byte-Ganzzahl mit Vorzeichen serialisiert.</span><span class="sxs-lookup"><span data-stu-id="980ce-117">Object is serialized as a signed 8-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_U8`|<span data-ttu-id="980ce-118">Das Objekt wird als eine 8-Byte-Ganzzahl ohne Vorzeichen serialisiert.</span><span class="sxs-lookup"><span data-stu-id="980ce-118">Object is serialized as an unsigned 8-byte integer.</span></span>|  
|`SERIALIZATION_TYPE_R4`|<span data-ttu-id="980ce-119">Objekt wird als ein 4-Byte-Gleitkommazahl serialisiert.</span><span class="sxs-lookup"><span data-stu-id="980ce-119">Object is serialized as a 4-byte floating point.</span></span>|  
|`SERIALIZATION_TYPE_R8`|<span data-ttu-id="980ce-120">Das Objekt wird als eine 8-Byte-Gleitkommazahl serialisiert.</span><span class="sxs-lookup"><span data-stu-id="980ce-120">Object is serialized as an 8-byte floating point.</span></span>|  
|`SERIALIZATION_TYPE_STRING`|<span data-ttu-id="980ce-121">Objekt wird als System.String-Typ serialisiert.</span><span class="sxs-lookup"><span data-stu-id="980ce-121">Object is serialized as a System.String type.</span></span>|  
|`SERIALIZATION_TYPE_SZARRAY`|<span data-ttu-id="980ce-122">Objekt wird serialisiert, wie ein eindimensionales, 0 (null) Untergrenze Array.</span><span class="sxs-lookup"><span data-stu-id="980ce-122">Object is serialized as a single-dimensional, zero lower-bound array.</span></span>|  
|`SERIALIZATION_TYPE_TYPE`|<span data-ttu-id="980ce-123">Objekt wird als generischer Typ serialisiert.</span><span class="sxs-lookup"><span data-stu-id="980ce-123">Object is serialized as a generic type.</span></span>|  
|`SERIALIZATION_TYPE_TAGGED_OBJECT`|<span data-ttu-id="980ce-124">Objekt wird als markiertes Objekt serialisiert.</span><span class="sxs-lookup"><span data-stu-id="980ce-124">Object is serialized as a tagged object.</span></span>|  
|`SERIALIZATION_TYPE_FIELD`|<span data-ttu-id="980ce-125">Objekt wird als Feld serialisiert.</span><span class="sxs-lookup"><span data-stu-id="980ce-125">Object is serialized as a field.</span></span>|  
|`SERIALIZATION_TYPE_PROPERTY`|<span data-ttu-id="980ce-126">Das Objekt wird als eine Eigenschaft serialisiert.</span><span class="sxs-lookup"><span data-stu-id="980ce-126">Object is serialized as a property.</span></span>|  
|`SERIALIZATION_TYPE_ENUM`|<span data-ttu-id="980ce-127">Das Objekt wird als eine Enumeration serialisiert.</span><span class="sxs-lookup"><span data-stu-id="980ce-127">Object is serialized as an enumeration.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="980ce-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="980ce-128">Requirements</span></span>  
 <span data-ttu-id="980ce-129">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="980ce-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="980ce-130">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="980ce-130">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="980ce-131">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="980ce-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="980ce-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="980ce-132">See Also</span></span>  
 [<span data-ttu-id="980ce-133">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="980ce-133">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
