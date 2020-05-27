---
title: COUNINITIEE-Enumeration
ms.date: 03/30/2017
api_name:
- COUNINITIEE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COUNINITIEE
helpviewer_keywords:
- COUNINITIEE enumeration [.NET Framework metadata]
ms.assetid: c42baa79-f469-4330-95a2-baf7f021c2fc
topic_type:
- apiref
ms.openlocfilehash: 14942680a79c4d1fcc69092a4f752738db1fb0b0
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008915"
---
# <a name="couninitiee-enumeration"></a><span data-ttu-id="efe85-102">COUNINITIEE-Enumeration</span><span class="sxs-lookup"><span data-stu-id="efe85-102">COUNINITIEE Enumeration</span></span>
<span data-ttu-id="efe85-103">Gibt die Konstanten an, die von " [zählinitializeee](../hosting/couninitializeee-function.md) " beim Initialisieren der Common Language Runtime verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="efe85-103">Specifies constants used by [CoUninitializeEE](../hosting/couninitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efe85-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="efe85-104">Syntax</span></span>  
  
```cpp  
typedef enum tagCOUNINITEE  
{  
    COUNINITEE_DEFAULT  = 0x0,
    COUNINITEE_DLL      = 0x1  
} COUNINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="efe85-105">Member</span><span class="sxs-lookup"><span data-stu-id="efe85-105">Members</span></span>  
  
|<span data-ttu-id="efe85-106">Member</span><span class="sxs-lookup"><span data-stu-id="efe85-106">Member</span></span>|<span data-ttu-id="efe85-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="efe85-107">Description</span></span>|  
|------------|-----------------|  
|`COUNINITEE_DEFAULT`|<span data-ttu-id="efe85-108">Gibt den Standardmodus für die nicht Initialisierung an.</span><span class="sxs-lookup"><span data-stu-id="efe85-108">Indicates default uninitialization mode.</span></span>|  
|`COUNINITEE_DLL`|<span data-ttu-id="efe85-109">Gibt den nicht Initialisierungs Modus zum Entladen einer Assembly an.</span><span class="sxs-lookup"><span data-stu-id="efe85-109">Indicates uninitialization mode for unloading an assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="efe85-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="efe85-110">Requirements</span></span>  
 <span data-ttu-id="efe85-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="efe85-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="efe85-112">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="efe85-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="efe85-113">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="efe85-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="efe85-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="efe85-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efe85-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="efe85-115">See also</span></span>

- [<span data-ttu-id="efe85-116">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="efe85-116">Metadata Enumerations</span></span>](metadata-enumerations.md)
