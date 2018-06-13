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
ms.openlocfilehash: de120516655c1a0578e88ecc2890701ed9fc2f6d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443699"
---
# <a name="assemblyrefflags-enumeration"></a><span data-ttu-id="c0198-102">AssemblyRefFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="c0198-102">AssemblyRefFlags Enumeration</span></span>
<span data-ttu-id="c0198-103">Enthält Werte, die Features eines Assemblyverweises beschreiben.</span><span class="sxs-lookup"><span data-stu-id="c0198-103">Contains values that describe features of an assembly reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0198-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c0198-104">Syntax</span></span>  
  
```  
typedef enum {  
    arfFullOriginator = 0x0001  
} AssemblyRefFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="c0198-105">Member</span><span class="sxs-lookup"><span data-stu-id="c0198-105">Members</span></span>  
  
|<span data-ttu-id="c0198-106">Member</span><span class="sxs-lookup"><span data-stu-id="c0198-106">Member</span></span>|<span data-ttu-id="c0198-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c0198-107">Description</span></span>|  
|------------|-----------------|  
|`arfFullOriginator`|<span data-ttu-id="c0198-108">Gibt an, dass der Assemblyverweis vollständige, nicht gehashte Informationen über den Herausgeber der Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="c0198-108">Specifies that the assembly reference contains full, unhashed information about the publisher of the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c0198-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c0198-109">Requirements</span></span>  
 <span data-ttu-id="c0198-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0198-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0198-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c0198-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c0198-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0198-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0198-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c0198-113">See Also</span></span>  
 [<span data-ttu-id="c0198-114">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="c0198-114">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)  
 [<span data-ttu-id="c0198-115">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c0198-115">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)  
 [<span data-ttu-id="c0198-116">DefineAssemblyRef-Methode</span><span class="sxs-lookup"><span data-stu-id="c0198-116">DefineAssemblyRef Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)
