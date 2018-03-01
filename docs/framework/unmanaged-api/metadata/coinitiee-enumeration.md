---
title: COINITIEE-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ad117c3efd31cc176281e571b7fde11229c097e9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="coinitiee-enumeration"></a><span data-ttu-id="3ab63-102">COINITIEE-Enumeration</span><span class="sxs-lookup"><span data-stu-id="3ab63-102">COINITIEE Enumeration</span></span>
<span data-ttu-id="3ab63-103">Gibt Konstanten verwendet [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) beim Initialisieren der common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="3ab63-103">Specifies constants used by [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ab63-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3ab63-104">Syntax</span></span>  
  
```  
typedef enum tagCOINITEE {  
   COINITEE_DEFAULT = 0x0,  
   COINITEE_DLL     = 0x1,  
   COINITEE_MAIN    = 0x2  
} COINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="3ab63-105">Member</span><span class="sxs-lookup"><span data-stu-id="3ab63-105">Members</span></span>  
  
|<span data-ttu-id="3ab63-106">Member</span><span class="sxs-lookup"><span data-stu-id="3ab63-106">Member</span></span>|<span data-ttu-id="3ab63-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3ab63-107">Description</span></span>|  
|------------|-----------------|  
|`COINITEE_DEFAULT`|<span data-ttu-id="3ab63-108">Initialisierung-Standardmodus.</span><span class="sxs-lookup"><span data-stu-id="3ab63-108">Default initialization mode.</span></span> <span data-ttu-id="3ab63-109">Initialisiert die Laufzeit und erstellt die Standardeinstellung <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="3ab63-109">This initializes the runtime and creates the default <xref:System.AppDomain>.</span></span>|  
|`COINITEE_DLL`|<span data-ttu-id="3ab63-110">Führen Sie eine verwaltete DLL initialisiert.</span><span class="sxs-lookup"><span data-stu-id="3ab63-110">Initializes to run a managed DLL.</span></span>|  
|`COINITEE_MAIN`|<span data-ttu-id="3ab63-111">Führen Sie eine verwaltete EXE-Datei initialisiert.</span><span class="sxs-lookup"><span data-stu-id="3ab63-111">Initializes to run a managed EXE.</span></span> <span data-ttu-id="3ab63-112">Dies initialisiert die Laufzeit, jedoch nicht die Standardeinstellung erstellt <xref:System.AppDomain>, die nach der Eingabe der Hauptroutine der EXE-Datei erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="3ab63-112">This initializes the runtime but does not create the default <xref:System.AppDomain>, which is created after entering the main routine of the EXE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3ab63-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3ab63-113">Requirements</span></span>  
 <span data-ttu-id="3ab63-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ab63-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ab63-115">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3ab63-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3ab63-116">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="3ab63-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3ab63-117">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ab63-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ab63-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3ab63-118">See Also</span></span>  
 [<span data-ttu-id="3ab63-119">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="3ab63-119">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
