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
ms.openlocfilehash: 8fe6216e11a64ea182d796247d888b862b1e8377
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177928"
---
# <a name="corregflags-enumeration"></a><span data-ttu-id="5df91-102">CorRegFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="5df91-102">CorRegFlags Enumeration</span></span>
<span data-ttu-id="5df91-103">Stellt Flagwerte bereit, die für die Registrierung bei der Installation eines Moduls oder zusammengesetzten Abbilds verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5df91-103">Provides flag values used for registration when installing a module or composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5df91-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5df91-104">Syntax</span></span>  
  
```cpp  
typedef enum
{  
    regNoCopy  = 0x00000001,  
    regConfig  = 0x00000002,  
    regHasRefs = 0x00000004  
} CorRegFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="5df91-105">Members</span><span class="sxs-lookup"><span data-stu-id="5df91-105">Members</span></span>  
  
|<span data-ttu-id="5df91-106">Member</span><span class="sxs-lookup"><span data-stu-id="5df91-106">Member</span></span>|<span data-ttu-id="5df91-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5df91-107">Description</span></span>|  
|------------|-----------------|  
|`regNoCopy`|<span data-ttu-id="5df91-108">Gibt an, dass Dateien nicht in das Ziel kopiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="5df91-108">Specifies that files should not be copied into the destination.</span></span>|  
|`regConfig`|<span data-ttu-id="5df91-109">Gibt an, dass es sich bei dem Modul oder Verbundumbau um eine Konfiguration handelt.</span><span class="sxs-lookup"><span data-stu-id="5df91-109">Specifies that the module or composite is a configuration.</span></span>|  
|`regHasRefs`|<span data-ttu-id="5df91-110">Gibt an, dass das Modul oder komposit klassenreferenziert ist.</span><span class="sxs-lookup"><span data-stu-id="5df91-110">Specifies that the module or composite has class references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5df91-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="5df91-111">Requirements</span></span>  
 <span data-ttu-id="5df91-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5df91-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5df91-113">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5df91-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5df91-114">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="5df91-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5df91-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5df91-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5df91-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5df91-116">See also</span></span>

- [<span data-ttu-id="5df91-117">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="5df91-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
