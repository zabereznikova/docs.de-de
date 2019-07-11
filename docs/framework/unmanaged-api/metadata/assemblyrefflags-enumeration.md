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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c402dcda79f013b19b091c6309b3d71951018a18
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776368"
---
# <a name="assemblyrefflags-enumeration"></a><span data-ttu-id="576d5-102">AssemblyRefFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="576d5-102">AssemblyRefFlags Enumeration</span></span>
<span data-ttu-id="576d5-103">Enthält Werte, die Funktionen eines Assemblyverweises beschreiben.</span><span class="sxs-lookup"><span data-stu-id="576d5-103">Contains values that describe features of an assembly reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="576d5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="576d5-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    arfFullOriginator = 0x0001  
} AssemblyRefFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="576d5-105">Member</span><span class="sxs-lookup"><span data-stu-id="576d5-105">Members</span></span>  
  
|<span data-ttu-id="576d5-106">Member</span><span class="sxs-lookup"><span data-stu-id="576d5-106">Member</span></span>|<span data-ttu-id="576d5-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="576d5-107">Description</span></span>|  
|------------|-----------------|  
|`arfFullOriginator`|<span data-ttu-id="576d5-108">Gibt an, dass der Assemblyverweis vollständige, nicht gehashte Informationen über den Herausgeber der Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="576d5-108">Specifies that the assembly reference contains full, unhashed information about the publisher of the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="576d5-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="576d5-109">Requirements</span></span>  
 <span data-ttu-id="576d5-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="576d5-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="576d5-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="576d5-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="576d5-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="576d5-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="576d5-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="576d5-113">See also</span></span>

- [<span data-ttu-id="576d5-114">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="576d5-114">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
- [<span data-ttu-id="576d5-115">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="576d5-115">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="576d5-116">DefineAssemblyRef-Methode</span><span class="sxs-lookup"><span data-stu-id="576d5-116">DefineAssemblyRef Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)
