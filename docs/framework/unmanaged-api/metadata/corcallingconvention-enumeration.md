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
ms.openlocfilehash: 9d4690cb6adedc77717e577d409cb52b18b1b5ca
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443833"
---
# <a name="corcallingconvention-enumeration"></a><span data-ttu-id="35426-102">CorCallingConvention-Enumeration</span><span class="sxs-lookup"><span data-stu-id="35426-102">CorCallingConvention Enumeration</span></span>
<span data-ttu-id="35426-103">Enthält Werte, die die Typen der Aufrufkonventionen beschreiben, die in verwaltetem Code durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="35426-103">Contains values that describe the types of calling conventions that are made in managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35426-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="35426-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="35426-105">Mitglieder</span><span class="sxs-lookup"><span data-stu-id="35426-105">Members</span></span>  
  
|<span data-ttu-id="35426-106">Member</span><span class="sxs-lookup"><span data-stu-id="35426-106">Member</span></span>|<span data-ttu-id="35426-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="35426-107">Description</span></span>|  
|------------|-----------------|  
|`IMAGE_CEE_CS_CALLCONV_DEFAULT`|<span data-ttu-id="35426-108">Gibt eine Standard Aufruf Konvention an.</span><span class="sxs-lookup"><span data-stu-id="35426-108">Indicates a default calling convention.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_VARARG`|<span data-ttu-id="35426-109">Gibt an, dass die Methode eine Variable Anzahl von Parametern annimmt.</span><span class="sxs-lookup"><span data-stu-id="35426-109">Indicates that the method takes a variable number of parameters.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_FIELD`|<span data-ttu-id="35426-110">Gibt an, dass der-Befehl ein-Feld ist.</span><span class="sxs-lookup"><span data-stu-id="35426-110">Indicates that the call is to a field.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_LOCAL_SIG`|<span data-ttu-id="35426-111">Gibt an, dass der-Befehl an eine lokale Methode erfolgt.</span><span class="sxs-lookup"><span data-stu-id="35426-111">Indicates that the call is to a local method.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_PROPERTY`|<span data-ttu-id="35426-112">Gibt an, dass der-Befehl eine Eigenschaft ist.</span><span class="sxs-lookup"><span data-stu-id="35426-112">Indicates that the call is to a property.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_UNMGD`|<span data-ttu-id="35426-113">Gibt an, dass der-Befehl nicht verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="35426-113">Indicates that the call is unmanaged.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_GENERICINST`|<span data-ttu-id="35426-114">Gibt eine generische Instanziierung einer Methode an.</span><span class="sxs-lookup"><span data-stu-id="35426-114">Indicates a generic method instantiation.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_NATIVEVARARG`|<span data-ttu-id="35426-115">Gibt einen 64-Bit-PInvoke-Aufrufe an eine Methode an, die eine Variable Anzahl von Parametern annimmt.</span><span class="sxs-lookup"><span data-stu-id="35426-115">Indicates a 64-bit PInvoke call to a method that takes a variable number of parameters.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_MAX`|<span data-ttu-id="35426-116">Beschreibt einen ungültigen 4-Bit-Wert.</span><span class="sxs-lookup"><span data-stu-id="35426-116">Describes an invalid 4-bit value.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_MASK`|<span data-ttu-id="35426-117">Gibt an, dass die Aufruf Konvention durch die untersten vier Bits beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="35426-117">Indicates that the calling convention is described by the bottom four bits.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_HASTHIS`|<span data-ttu-id="35426-118">Gibt an, dass im oberen Bit ein `this` Parameter beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="35426-118">Indicates that the top bit describes a `this` parameter.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_EXPLICITTHIS`|<span data-ttu-id="35426-119">Gibt an, dass ein `this`-Parameter explizit in der Signatur beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="35426-119">Indicates that a `this` parameter is explicitly described in the signature.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_GENERIC`|<span data-ttu-id="35426-120">Gibt eine generische Methoden Signatur mit einer expliziten Anzahl von Typargumenten an.</span><span class="sxs-lookup"><span data-stu-id="35426-120">Indicates a generic method signature with an explicit number of type arguments.</span></span> <span data-ttu-id="35426-121">Dabei geht es um eine normale Parameter Anzahl.</span><span class="sxs-lookup"><span data-stu-id="35426-121">This precedes an ordinary parameter count.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="35426-122">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="35426-122">Requirements</span></span>  
 <span data-ttu-id="35426-123">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35426-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35426-124">**Header:** Corhdr. h</span><span class="sxs-lookup"><span data-stu-id="35426-124">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="35426-125">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35426-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35426-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="35426-126">See also</span></span>

- [<span data-ttu-id="35426-127">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="35426-127">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
