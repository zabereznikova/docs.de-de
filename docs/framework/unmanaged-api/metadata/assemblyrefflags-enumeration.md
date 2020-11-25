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
ms.openlocfilehash: 0a99d2f79645bdc46ff4db86d7280614eeb1faf5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732761"
---
# <a name="assemblyrefflags-enumeration"></a><span data-ttu-id="572b3-102">AssemblyRefFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="572b3-102">AssemblyRefFlags Enumeration</span></span>

<span data-ttu-id="572b3-103">Enthält Werte, die Funktionen eines Assemblyverweises beschreiben.</span><span class="sxs-lookup"><span data-stu-id="572b3-103">Contains values that describe features of an assembly reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="572b3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="572b3-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    arfFullOriginator = 0x0001  
} AssemblyRefFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="572b3-105">Member</span><span class="sxs-lookup"><span data-stu-id="572b3-105">Members</span></span>  
  
|<span data-ttu-id="572b3-106">Member</span><span class="sxs-lookup"><span data-stu-id="572b3-106">Member</span></span>|<span data-ttu-id="572b3-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="572b3-107">Description</span></span>|  
|------------|-----------------|  
|`arfFullOriginator`|<span data-ttu-id="572b3-108">Gibt an, dass der Assemblyverweis vollständige, unverschlüsselte Informationen zum Verleger der Assembly enthält.</span><span class="sxs-lookup"><span data-stu-id="572b3-108">Specifies that the assembly reference contains full, unhashed information about the publisher of the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="572b3-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="572b3-109">Requirements</span></span>  

 <span data-ttu-id="572b3-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="572b3-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="572b3-111">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="572b3-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="572b3-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="572b3-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="572b3-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="572b3-113">See also</span></span>

- [<span data-ttu-id="572b3-114">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="572b3-114">Metadata Enumerations</span></span>](metadata-enumerations.md)
- [<span data-ttu-id="572b3-115">IMetaDataAssemblyEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="572b3-115">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
- [<span data-ttu-id="572b3-116">DefineAssemblyRef-Methode</span><span class="sxs-lookup"><span data-stu-id="572b3-116">DefineAssemblyRef Method</span></span>](imetadataassemblyemit-defineassemblyref-method.md)
