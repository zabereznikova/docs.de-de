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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d8f830ca7e273b65dc9ec77566a02df6c32cd464
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62045538"
---
# <a name="corpekind-enumeration"></a><span data-ttu-id="18b46-102">CorPEKind-Enumeration</span><span class="sxs-lookup"><span data-stu-id="18b46-102">CorPEKind Enumeration</span></span>
<span data-ttu-id="18b46-103">Enthält Werte, die beschreiben, eine Datei (portable Executable)-Datei von einem Aufruf zurückgegeben [IMetaDataImport2:: GetPEKind](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md).</span><span class="sxs-lookup"><span data-stu-id="18b46-103">Contains values that describe a portable executable (PE) file, as returned from a call to [IMetaDataImport2::GetPEKind](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18b46-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="18b46-104">Syntax</span></span>  
  
```  
typedef enum CorPEKind {  
  
    peNot           = 0x00000000,  
    peILonly        = 0x00000001,  
    pe32BitRequired = 0x00000002,  
    pe32Plus        = 0x00000004,  
    pe32Unmanaged   = 0x00000008,  
    pe32BitPreferred= 0x00000010  
  
} CorPEKind;  
```  
  
## <a name="members"></a><span data-ttu-id="18b46-105">Member</span><span class="sxs-lookup"><span data-stu-id="18b46-105">Members</span></span>  
  
|<span data-ttu-id="18b46-106">Member</span><span class="sxs-lookup"><span data-stu-id="18b46-106">Member</span></span>|<span data-ttu-id="18b46-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="18b46-107">Description</span></span>|  
|------------|-----------------|  
|`peNot`|<span data-ttu-id="18b46-108">Gibt an, dass es sich nicht um eine PE-Datei handelt.</span><span class="sxs-lookup"><span data-stu-id="18b46-108">Indicates that this is not a PE file.</span></span>|  
|`peILOnly`|<span data-ttu-id="18b46-109">Gibt an, dass diese PE-Datei enthält nur verwalteten Code.</span><span class="sxs-lookup"><span data-stu-id="18b46-109">Indicates that this PE file contains only managed code.</span></span>|  
|`pe32BitRequired`|<span data-ttu-id="18b46-110">Gibt an, dass diese PE-Datei mit Win32-Aufrufe ausführt.</span><span class="sxs-lookup"><span data-stu-id="18b46-110">Indicates that this PE file makes Win32 calls.</span></span>|  
|`pe32Plus`|<span data-ttu-id="18b46-111">Gibt an, dass diese PE-Datei auf einer 64-Bit-Plattform ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="18b46-111">Indicates that this PE file runs on a 64-bit platform.</span></span>|  
|`pe32Unmanaged`|<span data-ttu-id="18b46-112">Gibt an, dass diese PE-Datei mit systemeigenem Code ist.</span><span class="sxs-lookup"><span data-stu-id="18b46-112">Indicates that this PE file is native code.</span></span>|  
|<span data-ttu-id="18b46-113">pe32BitPreferred</span><span class="sxs-lookup"><span data-stu-id="18b46-113">pe32BitPreferred</span></span>|<span data-ttu-id="18b46-114">Gibt an, dass diese PE-Datei plattformunabhängig ist und zieht es vor, die in einer 32-Bit-Umgebung geladen werden.</span><span class="sxs-lookup"><span data-stu-id="18b46-114">Indicates that this PE file is platform-neutral and prefers to be loaded in a 32-bit environment.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="18b46-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="18b46-115">Remarks</span></span>  
 <span data-ttu-id="18b46-116">Diese Werte können in bitweise Kombinationen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="18b46-116">These values can be used in bitwise combinations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18b46-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="18b46-117">Requirements</span></span>  
 <span data-ttu-id="18b46-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="18b46-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18b46-119">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="18b46-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="18b46-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18b46-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18b46-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="18b46-121">See also</span></span>

- [<span data-ttu-id="18b46-122">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="18b46-122">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
