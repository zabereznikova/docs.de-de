---
title: AssemblyRefFlags-Enumeration
ms.date: 03/30/2017
api_name:
- AssemblyRefFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AssemblyRefFlags
helpviewer_keywords:
- AssemblyRefFlags enumeration [.NET Framework metadata]
ms.assetid: decd4f46-f3b2-466f-9501-e74f2b86b846
topic_type:
- apiref
ms.openlocfilehash: 23d293a87112c62cb2127b435faeca258a7de226
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444224"
---
# <a name="assemblyrefflags-enumeration"></a><span data-ttu-id="3e85a-102">AssemblyRefFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="3e85a-102">AssemblyRefFlags Enumeration</span></span>
<span data-ttu-id="3e85a-103">Contains values that describe features of an assembly reference.</span><span class="sxs-lookup"><span data-stu-id="3e85a-103">Contains values that describe features of an assembly reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e85a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3e85a-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    arfFullOriginator = 0x0001  
} AssemblyRefFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="3e85a-105">Member</span><span class="sxs-lookup"><span data-stu-id="3e85a-105">Members</span></span>  
  
|<span data-ttu-id="3e85a-106">Member</span><span class="sxs-lookup"><span data-stu-id="3e85a-106">Member</span></span>|<span data-ttu-id="3e85a-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3e85a-107">Description</span></span>|  
|------------|-----------------|  
|`arfFullOriginator`|<span data-ttu-id="3e85a-108">Specifies that the assembly reference contains full, unhashed information about the publisher of the assembly.</span><span class="sxs-lookup"><span data-stu-id="3e85a-108">Specifies that the assembly reference contains full, unhashed information about the publisher of the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3e85a-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3e85a-109">Requirements</span></span>  
 <span data-ttu-id="3e85a-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e85a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e85a-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3e85a-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3e85a-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e85a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e85a-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3e85a-113">See also</span></span>

- [<span data-ttu-id="3e85a-114">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="3e85a-114">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [<span data-ttu-id="3e85a-115">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3e85a-115">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="3e85a-116">DefineAssemblyRef-Methode</span><span class="sxs-lookup"><span data-stu-id="3e85a-116">DefineAssemblyRef Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)
