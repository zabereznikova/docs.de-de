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
ms.openlocfilehash: b0f8c7e6d2acf4d4c080cc147bf6d42bf13cb51b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723830"
---
# <a name="couninitiee-enumeration"></a><span data-ttu-id="ccfe0-102">COUNINITIEE-Enumeration</span><span class="sxs-lookup"><span data-stu-id="ccfe0-102">COUNINITIEE Enumeration</span></span>

<span data-ttu-id="ccfe0-103">Gibt die Konstanten an, die von " [zählinitializeee](../hosting/couninitializeee-function.md) " beim Initialisieren der Common Language Runtime verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ccfe0-103">Specifies constants used by [CoUninitializeEE](../hosting/couninitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccfe0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ccfe0-104">Syntax</span></span>  
  
```cpp  
typedef enum tagCOUNINITEE  
{  
    COUNINITEE_DEFAULT  = 0x0,
    COUNINITEE_DLL      = 0x1  
} COUNINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="ccfe0-105">Member</span><span class="sxs-lookup"><span data-stu-id="ccfe0-105">Members</span></span>  
  
|<span data-ttu-id="ccfe0-106">Member</span><span class="sxs-lookup"><span data-stu-id="ccfe0-106">Member</span></span>|<span data-ttu-id="ccfe0-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ccfe0-107">Description</span></span>|  
|------------|-----------------|  
|`COUNINITEE_DEFAULT`|<span data-ttu-id="ccfe0-108">Gibt den Standardmodus für die nicht Initialisierung an.</span><span class="sxs-lookup"><span data-stu-id="ccfe0-108">Indicates default uninitialization mode.</span></span>|  
|`COUNINITEE_DLL`|<span data-ttu-id="ccfe0-109">Gibt den nicht Initialisierungs Modus zum Entladen einer Assembly an.</span><span class="sxs-lookup"><span data-stu-id="ccfe0-109">Indicates uninitialization mode for unloading an assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ccfe0-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ccfe0-110">Requirements</span></span>  

 <span data-ttu-id="ccfe0-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ccfe0-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ccfe0-112">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ccfe0-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ccfe0-113">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="ccfe0-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ccfe0-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ccfe0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccfe0-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ccfe0-115">See also</span></span>

- [<span data-ttu-id="ccfe0-116">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="ccfe0-116">Metadata Enumerations</span></span>](metadata-enumerations.md)
