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
ms.openlocfilehash: 4a84fdfdba96c58671302c723b8a56848b70eb60
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59180016"
---
# <a name="coinitiee-enumeration"></a><span data-ttu-id="d9419-102">COINITIEE-Enumeration</span><span class="sxs-lookup"><span data-stu-id="d9419-102">COINITIEE Enumeration</span></span>
<span data-ttu-id="d9419-103">Gibt Konstanten an, die von verwendet [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) beim Initialisieren der common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="d9419-103">Specifies constants used by [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9419-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d9419-104">Syntax</span></span>  
  
```  
typedef enum tagCOINITEE {  
   COINITEE_DEFAULT = 0x0,  
   COINITEE_DLL     = 0x1,  
   COINITEE_MAIN    = 0x2  
} COINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="d9419-105">Member</span><span class="sxs-lookup"><span data-stu-id="d9419-105">Members</span></span>  
  
|<span data-ttu-id="d9419-106">Member</span><span class="sxs-lookup"><span data-stu-id="d9419-106">Member</span></span>|<span data-ttu-id="d9419-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d9419-107">Description</span></span>|  
|------------|-----------------|  
|`COINITEE_DEFAULT`|<span data-ttu-id="d9419-108">Initialisierung-Standardmodus.</span><span class="sxs-lookup"><span data-stu-id="d9419-108">Default initialization mode.</span></span> <span data-ttu-id="d9419-109">Initialisiert die Laufzeit und erstellt die <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="d9419-109">This initializes the runtime and creates the default <xref:System.AppDomain>.</span></span>|  
|`COINITEE_DLL`|<span data-ttu-id="d9419-110">Führen Sie eine verwaltete DLL initialisiert.</span><span class="sxs-lookup"><span data-stu-id="d9419-110">Initializes to run a managed DLL.</span></span>|  
|`COINITEE_MAIN`|<span data-ttu-id="d9419-111">Führen Sie eine verwaltete EXE-Datei initialisiert.</span><span class="sxs-lookup"><span data-stu-id="d9419-111">Initializes to run a managed EXE.</span></span> <span data-ttu-id="d9419-112">Dies initialisiert die Laufzeit jedoch nicht die Standardeinstellung erstellt <xref:System.AppDomain>, das nach dem Eingeben der Hauptroutine der EXE-Datei erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="d9419-112">This initializes the runtime but does not create the default <xref:System.AppDomain>, which is created after entering the main routine of the EXE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d9419-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d9419-113">Requirements</span></span>  
 <span data-ttu-id="d9419-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9419-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9419-115">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d9419-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d9419-116">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d9419-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d9419-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9419-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9419-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d9419-118">See also</span></span>

- [<span data-ttu-id="d9419-119">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="d9419-119">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
