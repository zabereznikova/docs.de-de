---
title: CorFileFlags-Enumeration
ms.date: 03/30/2017
api_name:
- CorFileFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorFileFlags
helpviewer_keywords:
- CorFileFlags enumeration [.NET Framework metadata]
ms.assetid: d16703fd-518f-412e-92cb-74433d11032e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5c6ac7dabd2dfcc7829fd42389c0a6c261fe456d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781867"
---
# <a name="corfileflags-enumeration"></a><span data-ttu-id="eeda0-102">CorFileFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="eeda0-102">CorFileFlags Enumeration</span></span>
<span data-ttu-id="eeda0-103">Enthält Werte, die beschreiben, den Typ der Datei, die definiert, die in einem Aufruf von [IMetaDataAssemblyEmit:: DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="eeda0-103">Contains values that describe the type of file defined in a call to [IMetaDataAssemblyEmit::DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eeda0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="eeda0-104">Syntax</span></span>  
  
```cpp  
typedef enum CorFileFlags {  
  
    ffContainsMetaData      =   0x0000,  
    ffContainsNoMetaData    =   0x0001  
  
} CorFileFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="eeda0-105">Member</span><span class="sxs-lookup"><span data-stu-id="eeda0-105">Members</span></span>  
  
|<span data-ttu-id="eeda0-106">Member</span><span class="sxs-lookup"><span data-stu-id="eeda0-106">Member</span></span>|<span data-ttu-id="eeda0-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eeda0-107">Description</span></span>|  
|------------|-----------------|  
|`ffContainsMetaData`|<span data-ttu-id="eeda0-108">Gibt an, dass die Datei keiner Ressourcendatei gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="eeda0-108">Indicates that the file is not a resource file.</span></span>|  
|`ffContainsNoMetaData`|<span data-ttu-id="eeda0-109">Gibt an, dass die Datei, die möglicherweise eine Ressourcendatei, die Metadaten nicht enthält.</span><span class="sxs-lookup"><span data-stu-id="eeda0-109">Indicates that the file, possibly a resource file, does not contain metadata.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="eeda0-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="eeda0-110">Requirements</span></span>  
 <span data-ttu-id="eeda0-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eeda0-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eeda0-112">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="eeda0-112">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="eeda0-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eeda0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eeda0-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eeda0-114">See also</span></span>

- [<span data-ttu-id="eeda0-115">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="eeda0-115">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
