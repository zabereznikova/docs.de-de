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
ms.openlocfilehash: 70d789f417700734b546cac6ff527ed5aa84fcf9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688626"
---
# <a name="corfileflags-enumeration"></a><span data-ttu-id="1a8e5-102">CorFileFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="1a8e5-102">CorFileFlags Enumeration</span></span>

<span data-ttu-id="1a8e5-103">Enthält Werte, die den in einem [IMetaDataAssemblyEmit::D efinefile](imetadataassemblyemit-definefile-method.md)-Befehl definierten Dateityp beschreiben.</span><span class="sxs-lookup"><span data-stu-id="1a8e5-103">Contains values that describe the type of file defined in a call to [IMetaDataAssemblyEmit::DefineFile](imetadataassemblyemit-definefile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a8e5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1a8e5-104">Syntax</span></span>  
  
```cpp  
typedef enum CorFileFlags {  
  
    ffContainsMetaData      =   0x0000,  
    ffContainsNoMetaData    =   0x0001  
  
} CorFileFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="1a8e5-105">Member</span><span class="sxs-lookup"><span data-stu-id="1a8e5-105">Members</span></span>  
  
|<span data-ttu-id="1a8e5-106">Member</span><span class="sxs-lookup"><span data-stu-id="1a8e5-106">Member</span></span>|<span data-ttu-id="1a8e5-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1a8e5-107">Description</span></span>|  
|------------|-----------------|  
|`ffContainsMetaData`|<span data-ttu-id="1a8e5-108">Gibt an, dass die Datei keine Ressourcen Datei ist.</span><span class="sxs-lookup"><span data-stu-id="1a8e5-108">Indicates that the file is not a resource file.</span></span>|  
|`ffContainsNoMetaData`|<span data-ttu-id="1a8e5-109">Gibt an, dass die Datei, möglicherweise eine Ressourcen Datei, keine Metadaten enthält.</span><span class="sxs-lookup"><span data-stu-id="1a8e5-109">Indicates that the file, possibly a resource file, does not contain metadata.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1a8e5-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="1a8e5-110">Requirements</span></span>  

 <span data-ttu-id="1a8e5-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1a8e5-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a8e5-112">**Header:** Corhdr. h</span><span class="sxs-lookup"><span data-stu-id="1a8e5-112">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="1a8e5-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a8e5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a8e5-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1a8e5-114">See also</span></span>

- [<span data-ttu-id="1a8e5-115">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="1a8e5-115">Metadata Enumerations</span></span>](metadata-enumerations.md)
