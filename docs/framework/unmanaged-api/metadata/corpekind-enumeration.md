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
ms.openlocfilehash: 001be0c5e8897bacf76d2a044fb9400768473052
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673526"
---
# <a name="corpekind-enumeration"></a><span data-ttu-id="95e85-102">CorPEKind-Enumeration</span><span class="sxs-lookup"><span data-stu-id="95e85-102">CorPEKind Enumeration</span></span>

<span data-ttu-id="95e85-103">Enthält Werte, die eine portable ausführbare Datei (PE) beschreiben, wie von einem Aufrufen von [IMetaDataImport2:: getPeer Kind](imetadataimport2-getpekind-method.md)zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="95e85-103">Contains values that describe a portable executable (PE) file, as returned from a call to [IMetaDataImport2::GetPEKind](imetadataimport2-getpekind-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95e85-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="95e85-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="95e85-105">Member</span><span class="sxs-lookup"><span data-stu-id="95e85-105">Members</span></span>  
  
|<span data-ttu-id="95e85-106">Member</span><span class="sxs-lookup"><span data-stu-id="95e85-106">Member</span></span>|<span data-ttu-id="95e85-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="95e85-107">Description</span></span>|  
|------------|-----------------|  
|`peNot`|<span data-ttu-id="95e85-108">Gibt an, dass es sich nicht um eine PE-Datei handelt.</span><span class="sxs-lookup"><span data-stu-id="95e85-108">Indicates that this is not a PE file.</span></span>|  
|`peILOnly`|<span data-ttu-id="95e85-109">Gibt an, dass diese PE-Datei nur verwalteten Code enthält.</span><span class="sxs-lookup"><span data-stu-id="95e85-109">Indicates that this PE file contains only managed code.</span></span>|  
|`pe32BitRequired`|<span data-ttu-id="95e85-110">Gibt an, dass diese PE-Datei Win32-Aufrufe ausführt.</span><span class="sxs-lookup"><span data-stu-id="95e85-110">Indicates that this PE file makes Win32 calls.</span></span>|  
|`pe32Plus`|<span data-ttu-id="95e85-111">Gibt an, dass diese PE-Datei auf einer 64-Bit-Plattform ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="95e85-111">Indicates that this PE file runs on a 64-bit platform.</span></span>|  
|`pe32Unmanaged`|<span data-ttu-id="95e85-112">Gibt an, dass diese PE-Datei nativer Code ist.</span><span class="sxs-lookup"><span data-stu-id="95e85-112">Indicates that this PE file is native code.</span></span>|  
|<span data-ttu-id="95e85-113">pe32BitPreferred</span><span class="sxs-lookup"><span data-stu-id="95e85-113">pe32BitPreferred</span></span>|<span data-ttu-id="95e85-114">Gibt an, dass diese PE-Datei Platt Form neutral ist und bevorzugt in eine 32-Bit-Umgebung geladen wird.</span><span class="sxs-lookup"><span data-stu-id="95e85-114">Indicates that this PE file is platform-neutral and prefers to be loaded in a 32-bit environment.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95e85-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="95e85-115">Remarks</span></span>  

 <span data-ttu-id="95e85-116">Diese Werte können in bitweisen Kombinationen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="95e85-116">These values can be used in bitwise combinations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95e85-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="95e85-117">Requirements</span></span>  

 <span data-ttu-id="95e85-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95e85-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95e85-119">**Header:** Corhdr. h</span><span class="sxs-lookup"><span data-stu-id="95e85-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="95e85-120">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95e85-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95e85-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="95e85-121">See also</span></span>

- [<span data-ttu-id="95e85-122">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="95e85-122">Metadata Enumerations</span></span>](metadata-enumerations.md)
