---
title: COINITIEE-Enumeration
ms.date: 03/30/2017
api_name:
- COINITIEE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COINITIEE
helpviewer_keywords:
- COINITIEE enumeration [.NET Framework metadata]
ms.assetid: 64264238-3b68-4bac-a887-36b552426a6c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 23f5a2b6b0970f3cb64ee339e6a1a409354a60e5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780951"
---
# <a name="coinitiee-enumeration"></a><span data-ttu-id="9b31a-102">COINITIEE-Enumeration</span><span class="sxs-lookup"><span data-stu-id="9b31a-102">COINITIEE Enumeration</span></span>
<span data-ttu-id="9b31a-103">Gibt Konstanten an, die von verwendet [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) beim Initialisieren der common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="9b31a-103">Specifies constants used by [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b31a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9b31a-104">Syntax</span></span>  
  
```cpp  
typedef enum tagCOINITEE {  
   COINITEE_DEFAULT = 0x0,  
   COINITEE_DLL     = 0x1,  
   COINITEE_MAIN    = 0x2  
} COINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="9b31a-105">Member</span><span class="sxs-lookup"><span data-stu-id="9b31a-105">Members</span></span>  
  
|<span data-ttu-id="9b31a-106">Member</span><span class="sxs-lookup"><span data-stu-id="9b31a-106">Member</span></span>|<span data-ttu-id="9b31a-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9b31a-107">Description</span></span>|  
|------------|-----------------|  
|`COINITEE_DEFAULT`|<span data-ttu-id="9b31a-108">Initialisierung-Standardmodus.</span><span class="sxs-lookup"><span data-stu-id="9b31a-108">Default initialization mode.</span></span> <span data-ttu-id="9b31a-109">Initialisiert die Laufzeit und erstellt die <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="9b31a-109">This initializes the runtime and creates the default <xref:System.AppDomain>.</span></span>|  
|`COINITEE_DLL`|<span data-ttu-id="9b31a-110">Führen Sie eine verwaltete DLL initialisiert.</span><span class="sxs-lookup"><span data-stu-id="9b31a-110">Initializes to run a managed DLL.</span></span>|  
|`COINITEE_MAIN`|<span data-ttu-id="9b31a-111">Führen Sie eine verwaltete EXE-Datei initialisiert.</span><span class="sxs-lookup"><span data-stu-id="9b31a-111">Initializes to run a managed EXE.</span></span> <span data-ttu-id="9b31a-112">Dies initialisiert die Laufzeit jedoch nicht die Standardeinstellung erstellt <xref:System.AppDomain>, das nach dem Eingeben der Hauptroutine der EXE-Datei erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="9b31a-112">This initializes the runtime but does not create the default <xref:System.AppDomain>, which is created after entering the main routine of the EXE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9b31a-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9b31a-113">Requirements</span></span>  
 <span data-ttu-id="9b31a-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b31a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b31a-115">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9b31a-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9b31a-116">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="9b31a-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9b31a-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b31a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b31a-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9b31a-118">See also</span></span>

- [<span data-ttu-id="9b31a-119">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="9b31a-119">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
