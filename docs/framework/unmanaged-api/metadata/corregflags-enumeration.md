---
title: CorRegFlags-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorRegFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: CorRegFlags
helpviewer_keywords: CorRegFlags enumeration [.NET Framework metadata]
ms.assetid: 8d3080ee-39fe-4c57-8950-51323632d045
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c8118de9f4fc6a4f2820b88685b9b87c498328b1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="corregflags-enumeration"></a><span data-ttu-id="a8187-102">CorRegFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="a8187-102">CorRegFlags Enumeration</span></span>
<span data-ttu-id="a8187-103">Enthält Flagwerte, die für die Registrierung verwendet wird, wenn Sie ein Modul oder einen zusammengesetzten Abbilds installieren.</span><span class="sxs-lookup"><span data-stu-id="a8187-103">Provides flag values used for registration when installing a module or composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8187-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a8187-104">Syntax</span></span>  
  
```  
typedef enum   
{  
    regNoCopy  = 0x00000001,  
    regConfig  = 0x00000002,  
    regHasRefs = 0x00000004  
} CorRegFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="a8187-105">Member</span><span class="sxs-lookup"><span data-stu-id="a8187-105">Members</span></span>  
  
|<span data-ttu-id="a8187-106">Member</span><span class="sxs-lookup"><span data-stu-id="a8187-106">Member</span></span>|<span data-ttu-id="a8187-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a8187-107">Description</span></span>|  
|------------|-----------------|  
|`regNoCopy`|<span data-ttu-id="a8187-108">Gibt an, dass Dateien nicht in das Ziel kopiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a8187-108">Specifies that files should not be copied into the destination.</span></span>|  
|`regConfig`|<span data-ttu-id="a8187-109">Gibt an, dass das Modul oder eines zusammengesetzten Moduls eine Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="a8187-109">Specifies that the module or composite is a configuration.</span></span>|  
|`regHasRefs`|<span data-ttu-id="a8187-110">Gibt an, dass die Moduls oder eines zusammengesetzten Klasse verweisen.</span><span class="sxs-lookup"><span data-stu-id="a8187-110">Specifies that the module or composite has class references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a8187-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a8187-111">Requirements</span></span>  
 <span data-ttu-id="a8187-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a8187-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8187-113">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a8187-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a8187-114">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="a8187-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a8187-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8187-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8187-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a8187-116">See Also</span></span>  
 [<span data-ttu-id="a8187-117">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="a8187-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
