---
title: CorRegFlags-Enumeration
ms.date: 03/30/2017
api_name:
- CorRegFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorRegFlags
helpviewer_keywords:
- CorRegFlags enumeration [.NET Framework metadata]
ms.assetid: 8d3080ee-39fe-4c57-8950-51323632d045
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 52b59a4e52d3e0cda7353ec1b39c5307bd7b218e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54532265"
---
# <a name="corregflags-enumeration"></a><span data-ttu-id="ce08a-102">CorRegFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="ce08a-102">CorRegFlags Enumeration</span></span>
<span data-ttu-id="ce08a-103">Enthält Flagwerte, die für die Registrierung verwendet werden, wenn Sie ein Modul oder ein zusammengesetztes Bild zu installieren.</span><span class="sxs-lookup"><span data-stu-id="ce08a-103">Provides flag values used for registration when installing a module or composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce08a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ce08a-104">Syntax</span></span>  
  
```  
typedef enum   
{  
    regNoCopy  = 0x00000001,  
    regConfig  = 0x00000002,  
    regHasRefs = 0x00000004  
} CorRegFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="ce08a-105">Member</span><span class="sxs-lookup"><span data-stu-id="ce08a-105">Members</span></span>  
  
|<span data-ttu-id="ce08a-106">Member</span><span class="sxs-lookup"><span data-stu-id="ce08a-106">Member</span></span>|<span data-ttu-id="ce08a-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ce08a-107">Description</span></span>|  
|------------|-----------------|  
|`regNoCopy`|<span data-ttu-id="ce08a-108">Gibt an, dass Dateien nicht in das Ziel kopiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ce08a-108">Specifies that files should not be copied into the destination.</span></span>|  
|`regConfig`|<span data-ttu-id="ce08a-109">Gibt an, dass das Modul oder die Zusammensetzung einer Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="ce08a-109">Specifies that the module or composite is a configuration.</span></span>|  
|`regHasRefs`|<span data-ttu-id="ce08a-110">Gibt an, dass das Modul oder die zusammengesetzten Klasse verweisen.</span><span class="sxs-lookup"><span data-stu-id="ce08a-110">Specifies that the module or composite has class references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ce08a-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ce08a-111">Requirements</span></span>  
 <span data-ttu-id="ce08a-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce08a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce08a-113">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ce08a-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ce08a-114">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="ce08a-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ce08a-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce08a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce08a-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ce08a-116">See also</span></span>
- [<span data-ttu-id="ce08a-117">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="ce08a-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
