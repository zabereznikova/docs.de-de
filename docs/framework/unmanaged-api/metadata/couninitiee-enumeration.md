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
ms.openlocfilehash: e5cbd8c5b1bb048088fe137b1359d0bb9e29af20
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176122"
---
# <a name="couninitiee-enumeration"></a><span data-ttu-id="2c0ee-102">COUNINITIEE-Enumeration</span><span class="sxs-lookup"><span data-stu-id="2c0ee-102">COUNINITIEE Enumeration</span></span>
<span data-ttu-id="2c0ee-103">Gibt Konstanten an, die von [CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md) beim Initialisieren der Common Language Runtime verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2c0ee-103">Specifies constants used by [CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c0ee-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2c0ee-104">Syntax</span></span>  
  
```cpp  
typedef enum tagCOUNINITEE  
{  
    COUNINITEE_DEFAULT  = 0x0,
    COUNINITEE_DLL      = 0x1  
} COUNINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="2c0ee-105">Members</span><span class="sxs-lookup"><span data-stu-id="2c0ee-105">Members</span></span>  
  
|<span data-ttu-id="2c0ee-106">Member</span><span class="sxs-lookup"><span data-stu-id="2c0ee-106">Member</span></span>|<span data-ttu-id="2c0ee-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2c0ee-107">Description</span></span>|  
|------------|-----------------|  
|`COUNINITEE_DEFAULT`|<span data-ttu-id="2c0ee-108">Gibt den standardmäßigen Nichtinitialisierungsmodus an.</span><span class="sxs-lookup"><span data-stu-id="2c0ee-108">Indicates default uninitialization mode.</span></span>|  
|`COUNINITEE_DLL`|<span data-ttu-id="2c0ee-109">Gibt den Nichtinitialisierungsmodus zum Entladen einer Baugruppe an.</span><span class="sxs-lookup"><span data-stu-id="2c0ee-109">Indicates uninitialization mode for unloading an assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2c0ee-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2c0ee-110">Requirements</span></span>  
 <span data-ttu-id="2c0ee-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c0ee-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c0ee-112">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2c0ee-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2c0ee-113">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="2c0ee-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2c0ee-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c0ee-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c0ee-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2c0ee-115">See also</span></span>

- [<span data-ttu-id="2c0ee-116">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="2c0ee-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
