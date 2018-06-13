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
ms.openlocfilehash: b5869eb16bd768d58a6f27a83f2d8d51914a8aed
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443114"
---
# <a name="corpekind-enumeration"></a><span data-ttu-id="b85c4-102">CorPEKind-Enumeration</span><span class="sxs-lookup"><span data-stu-id="b85c4-102">CorPEKind Enumeration</span></span>
<span data-ttu-id="b85c4-103">Enthält Werte, die eine PE (portable Executable)-Datei wird beschrieben, wie von einem Aufruf zurückgegebene [IMetaDataImport2:: GetPEKind](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md).</span><span class="sxs-lookup"><span data-stu-id="b85c4-103">Contains values that describe a portable executable (PE) file, as returned from a call to [IMetaDataImport2::GetPEKind](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b85c4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b85c4-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="b85c4-105">Member</span><span class="sxs-lookup"><span data-stu-id="b85c4-105">Members</span></span>  
  
|<span data-ttu-id="b85c4-106">Member</span><span class="sxs-lookup"><span data-stu-id="b85c4-106">Member</span></span>|<span data-ttu-id="b85c4-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b85c4-107">Description</span></span>|  
|------------|-----------------|  
|`peNot`|<span data-ttu-id="b85c4-108">Gibt an, dass dies keiner PE-Datei ist.</span><span class="sxs-lookup"><span data-stu-id="b85c4-108">Indicates that this is not a PE file.</span></span>|  
|`peILOnly`|<span data-ttu-id="b85c4-109">Gibt an, dass diese PE-Datei nur verwalteten Code enthält.</span><span class="sxs-lookup"><span data-stu-id="b85c4-109">Indicates that this PE file contains only managed code.</span></span>|  
|`pe32BitRequired`|<span data-ttu-id="b85c4-110">Gibt an, dass diese PE-Datei Win32 aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="b85c4-110">Indicates that this PE file makes Win32 calls.</span></span>|  
|`pe32Plus`|<span data-ttu-id="b85c4-111">Gibt an, dass diese PE-Datei auf einer 64-Bit-Plattform ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b85c4-111">Indicates that this PE file runs on a 64-bit platform.</span></span>|  
|`pe32Unmanaged`|<span data-ttu-id="b85c4-112">Gibt an, dass diese PE-Datei mit systemeigenem Code ist.</span><span class="sxs-lookup"><span data-stu-id="b85c4-112">Indicates that this PE file is native code.</span></span>|  
|<span data-ttu-id="b85c4-113">pe32BitPreferred</span><span class="sxs-lookup"><span data-stu-id="b85c4-113">pe32BitPreferred</span></span>|<span data-ttu-id="b85c4-114">Gibt an, dass diese PE-Datei plattformunabhängiges ist verwendet und ob in einer 32-Bit-Umgebung geladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="b85c4-114">Indicates that this PE file is platform-neutral and prefers to be loaded in a 32-bit environment.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b85c4-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b85c4-115">Remarks</span></span>  
 <span data-ttu-id="b85c4-116">Diese Werte können in bitweisen Kombinationen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b85c4-116">These values can be used in bitwise combinations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b85c4-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b85c4-117">Requirements</span></span>  
 <span data-ttu-id="b85c4-118">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b85c4-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b85c4-119">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="b85c4-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="b85c4-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b85c4-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b85c4-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b85c4-121">See Also</span></span>  
 [<span data-ttu-id="b85c4-122">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="b85c4-122">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
