---
title: CorPEKind-Enumeration
ms.date: 03/30/2017
api_name:
- CorPEKind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorPEKind
helpviewer_keywords:
- CorPEKind enumeration [.NET Framework metadata]
ms.assetid: 22dc6dea-b1b9-4982-a730-a022d586b117
topic_type:
- apiref
ms.openlocfilehash: 8b6eab8156f72847eb6dd3369950f9b46a3fc877
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007558"
---
# <a name="corpekind-enumeration"></a><span data-ttu-id="fb28b-102">CorPEKind-Enumeration</span><span class="sxs-lookup"><span data-stu-id="fb28b-102">CorPEKind Enumeration</span></span>
<span data-ttu-id="fb28b-103">Enthält Werte, die eine portable ausführbare Datei (PE) beschreiben, wie von einem Aufrufen von [IMetaDataImport2:: getPeer Kind](imetadataimport2-getpekind-method.md)zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="fb28b-103">Contains values that describe a portable executable (PE) file, as returned from a call to [IMetaDataImport2::GetPEKind](imetadataimport2-getpekind-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb28b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fb28b-104">Syntax</span></span>  
  
```cpp  
typedef enum CorPEKind {  
  
    peNot           = 0x00000000,  
    peILonly        = 0x00000001,  
    pe32BitRequired = 0x00000002,  
    pe32Plus        = 0x00000004,  
    pe32Unmanaged   = 0x00000008,  
    pe32BitPreferred= 0x00000010  
  
} CorPEKind;  
```  
  
## <a name="members"></a><span data-ttu-id="fb28b-105">Member</span><span class="sxs-lookup"><span data-stu-id="fb28b-105">Members</span></span>  
  
|<span data-ttu-id="fb28b-106">Member</span><span class="sxs-lookup"><span data-stu-id="fb28b-106">Member</span></span>|<span data-ttu-id="fb28b-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fb28b-107">Description</span></span>|  
|------------|-----------------|  
|`peNot`|<span data-ttu-id="fb28b-108">Gibt an, dass es sich nicht um eine PE-Datei handelt.</span><span class="sxs-lookup"><span data-stu-id="fb28b-108">Indicates that this is not a PE file.</span></span>|  
|`peILOnly`|<span data-ttu-id="fb28b-109">Gibt an, dass diese PE-Datei nur verwalteten Code enthält.</span><span class="sxs-lookup"><span data-stu-id="fb28b-109">Indicates that this PE file contains only managed code.</span></span>|  
|`pe32BitRequired`|<span data-ttu-id="fb28b-110">Gibt an, dass diese PE-Datei Win32-Aufrufe ausführt.</span><span class="sxs-lookup"><span data-stu-id="fb28b-110">Indicates that this PE file makes Win32 calls.</span></span>|  
|`pe32Plus`|<span data-ttu-id="fb28b-111">Gibt an, dass diese PE-Datei auf einer 64-Bit-Plattform ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="fb28b-111">Indicates that this PE file runs on a 64-bit platform.</span></span>|  
|`pe32Unmanaged`|<span data-ttu-id="fb28b-112">Gibt an, dass diese PE-Datei nativer Code ist.</span><span class="sxs-lookup"><span data-stu-id="fb28b-112">Indicates that this PE file is native code.</span></span>|  
|<span data-ttu-id="fb28b-113">pe32BitPreferred</span><span class="sxs-lookup"><span data-stu-id="fb28b-113">pe32BitPreferred</span></span>|<span data-ttu-id="fb28b-114">Gibt an, dass diese PE-Datei Platt Form neutral ist und bevorzugt in eine 32-Bit-Umgebung geladen wird.</span><span class="sxs-lookup"><span data-stu-id="fb28b-114">Indicates that this PE file is platform-neutral and prefers to be loaded in a 32-bit environment.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fb28b-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fb28b-115">Remarks</span></span>  
 <span data-ttu-id="fb28b-116">Diese Werte können in bitweisen Kombinationen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fb28b-116">These values can be used in bitwise combinations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb28b-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="fb28b-117">Requirements</span></span>  
 <span data-ttu-id="fb28b-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb28b-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb28b-119">**Header:** Corhdr. h</span><span class="sxs-lookup"><span data-stu-id="fb28b-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="fb28b-120">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb28b-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb28b-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fb28b-121">See also</span></span>

- [<span data-ttu-id="fb28b-122">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="fb28b-122">Metadata Enumerations</span></span>](metadata-enumerations.md)
