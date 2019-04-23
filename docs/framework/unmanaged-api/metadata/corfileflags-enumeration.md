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
ms.openlocfilehash: 076d5de3e9d1925e3a030fee4a06a89862105897
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59159613"
---
# <a name="corfileflags-enumeration"></a><span data-ttu-id="ea696-102">CorFileFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="ea696-102">CorFileFlags Enumeration</span></span>
<span data-ttu-id="ea696-103">Enthält Werte, die beschreiben, den Typ der Datei, die definiert, die in einem Aufruf von [IMetaDataAssemblyEmit:: DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="ea696-103">Contains values that describe the type of file defined in a call to [IMetaDataAssemblyEmit::DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea696-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ea696-104">Syntax</span></span>  
  
```  
typedef enum CorFileFlags {  
  
    ffContainsMetaData      =   0x0000,  
    ffContainsNoMetaData    =   0x0001  
  
} CorFileFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="ea696-105">Member</span><span class="sxs-lookup"><span data-stu-id="ea696-105">Members</span></span>  
  
|<span data-ttu-id="ea696-106">Member</span><span class="sxs-lookup"><span data-stu-id="ea696-106">Member</span></span>|<span data-ttu-id="ea696-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ea696-107">Description</span></span>|  
|------------|-----------------|  
|`ffContainsMetaData`|<span data-ttu-id="ea696-108">Gibt an, dass die Datei keiner Ressourcendatei gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="ea696-108">Indicates that the file is not a resource file.</span></span>|  
|`ffContainsNoMetaData`|<span data-ttu-id="ea696-109">Gibt an, dass die Datei, die möglicherweise eine Ressourcendatei, die Metadaten nicht enthält.</span><span class="sxs-lookup"><span data-stu-id="ea696-109">Indicates that the file, possibly a resource file, does not contain metadata.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ea696-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ea696-110">Requirements</span></span>  
 <span data-ttu-id="ea696-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea696-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea696-112">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="ea696-112">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="ea696-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea696-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea696-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ea696-114">See also</span></span>

- [<span data-ttu-id="ea696-115">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="ea696-115">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
