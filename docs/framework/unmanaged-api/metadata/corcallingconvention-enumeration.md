---
title: CorCallingConvention-Enumeration
ms.date: 03/30/2017
api_name:
- CorCallingConvention
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorCallingConvention
helpviewer_keywords:
- CorCallingConvention enumeration [.NET Framework metadata]
ms.assetid: 69156fbf-7219-43bf-b4b8-b13f1a2fcb86
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 468ad1acf55c4d1b4fc2b53730f16ee8630cf19b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444014"
---
# <a name="corcallingconvention-enumeration"></a><span data-ttu-id="d39be-102">CorCallingConvention-Enumeration</span><span class="sxs-lookup"><span data-stu-id="d39be-102">CorCallingConvention Enumeration</span></span>
<span data-ttu-id="d39be-103">Enthält Werte, die die Typen der Aufrufkonventionen beschreiben, die in verwaltetem Code durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d39be-103">Contains values that describe the types of calling conventions that are made in managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d39be-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d39be-104">Syntax</span></span>  
  
```  
typedef enum CorCallingConvention  
{  
    IMAGE_CEE_CS_CALLCONV_DEFAULT       = 0x0,  
  
    IMAGE_CEE_CS_CALLCONV_VARARG        = 0x5,  
    IMAGE_CEE_CS_CALLCONV_FIELD         = 0x6,  
    IMAGE_CEE_CS_CALLCONV_LOCAL_SIG     = 0x7,  
    IMAGE_CEE_CS_CALLCONV_PROPERTY      = 0x8,  
    IMAGE_CEE_CS_CALLCONV_UNMGD         = 0x9,  
    IMAGE_CEE_CS_CALLCONV_GENERICINST   = 0xa,  
    IMAGE_CEE_CS_CALLCONV_NATIVEVARARG  = 0xb,  
    IMAGE_CEE_CS_CALLCONV_MAX           = 0xc,  
  
    IMAGE_CEE_CS_CALLCONV_MASK          = 0x0f,  
    IMAGE_CEE_CS_CALLCONV_HASTHIS       = 0x20,  
    IMAGE_CEE_CS_CALLCONV_EXPLICITTHIS  = 0x40,  
    IMAGE_CEE_CS_CALLCONV_GENERIC       = 0x10  
  
} CorCallingConvention;  
```  
  
## <a name="members"></a><span data-ttu-id="d39be-105">Member</span><span class="sxs-lookup"><span data-stu-id="d39be-105">Members</span></span>  
  
|<span data-ttu-id="d39be-106">Member</span><span class="sxs-lookup"><span data-stu-id="d39be-106">Member</span></span>|<span data-ttu-id="d39be-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d39be-107">Description</span></span>|  
|------------|-----------------|  
|`IMAGE_CEE_CS_CALLCONV_DEFAULT`|<span data-ttu-id="d39be-108">Gibt eine Standardaufrufkonvention an.</span><span class="sxs-lookup"><span data-stu-id="d39be-108">Indicates a default calling convention.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_VARARG`|<span data-ttu-id="d39be-109">Gibt an, dass die Methode eine Variable Anzahl von Parametern akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="d39be-109">Indicates that the method takes a variable number of parameters.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_FIELD`|<span data-ttu-id="d39be-110">Gibt an, dass ein Feld aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="d39be-110">Indicates that the call is to a field.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_LOCAL_SIG`|<span data-ttu-id="d39be-111">Gibt an, dass eine lokale Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="d39be-111">Indicates that the call is to a local method.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_PROPERTY`|<span data-ttu-id="d39be-112">Gibt an, dass eine Eigenschaft aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="d39be-112">Indicates that the call is to a property.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_UNMGD`|<span data-ttu-id="d39be-113">Gibt an, dass der Aufruf nicht verwaltet ist.</span><span class="sxs-lookup"><span data-stu-id="d39be-113">Indicates that the call is unmanaged.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_GENERICINST`|<span data-ttu-id="d39be-114">Gibt die Instanziierung einer generischen Methode an.</span><span class="sxs-lookup"><span data-stu-id="d39be-114">Indicates a generic method instantiation.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_NATIVEVARARG`|<span data-ttu-id="d39be-115">Gibt einen 64-Bit-PInvoke-Aufrufs an eine Methode, die eine Variable von Parametern Anzahl an.</span><span class="sxs-lookup"><span data-stu-id="d39be-115">Indicates a 64-bit PInvoke call to a method that takes a variable number of parameters.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_MAX`|<span data-ttu-id="d39be-116">Beschreibt einen ungültigen 4-Bit-Wert.</span><span class="sxs-lookup"><span data-stu-id="d39be-116">Describes an invalid 4-bit value.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_MASK`|<span data-ttu-id="d39be-117">Gibt an, dass die Aufrufkonvention durch die unteren vier Bits beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="d39be-117">Indicates that the calling convention is described by the bottom four bits.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_HASTHIS`|<span data-ttu-id="d39be-118">Gibt an, dass das oberste Bit beschreibt eine `this` Parameter.</span><span class="sxs-lookup"><span data-stu-id="d39be-118">Indicates that the top bit describes a `this` parameter.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_EXPLICITTHIS`|<span data-ttu-id="d39be-119">Gibt an, dass eine `this` Parameter ist in der Signatur explizit beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d39be-119">Indicates that a `this` parameter is explicitly described in the signature.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_GENERIC`|<span data-ttu-id="d39be-120">Gibt die Signatur einer generischen Methode mit einer expliziten Anzahl von Typargumenten an.</span><span class="sxs-lookup"><span data-stu-id="d39be-120">Indicates a generic method signature with an explicit number of type arguments.</span></span> <span data-ttu-id="d39be-121">Dies ist eine normale Parameteranzahl vorangestellt.</span><span class="sxs-lookup"><span data-stu-id="d39be-121">This precedes an ordinary parameter count.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d39be-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d39be-122">Requirements</span></span>  
 <span data-ttu-id="d39be-123">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d39be-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d39be-124">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="d39be-124">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="d39be-125">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d39be-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d39be-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d39be-126">See Also</span></span>  
 [<span data-ttu-id="d39be-127">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="d39be-127">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
