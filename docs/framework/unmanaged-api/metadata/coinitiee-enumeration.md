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
ms.openlocfilehash: 673450bb8209abede15e3cb65dd764b418073bc2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724194"
---
# <a name="coinitiee-enumeration"></a><span data-ttu-id="492b0-102">COINITIEE-Enumeration</span><span class="sxs-lookup"><span data-stu-id="492b0-102">COINITIEE Enumeration</span></span>

<span data-ttu-id="492b0-103">Gibt Konstanten an, die von [CoInitializeEE](../hosting/coinitializeee-function.md) beim Initialisieren der Common Language Runtime verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="492b0-103">Specifies constants used by [CoInitializeEE](../hosting/coinitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="492b0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="492b0-104">Syntax</span></span>  
  
```cpp  
typedef enum tagCOINITEE {  
   COINITEE_DEFAULT = 0x0,  
   COINITEE_DLL     = 0x1,  
   COINITEE_MAIN    = 0x2  
} COINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="492b0-105">Member</span><span class="sxs-lookup"><span data-stu-id="492b0-105">Members</span></span>  
  
|<span data-ttu-id="492b0-106">Member</span><span class="sxs-lookup"><span data-stu-id="492b0-106">Member</span></span>|<span data-ttu-id="492b0-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="492b0-107">Description</span></span>|  
|------------|-----------------|  
|`COINITEE_DEFAULT`|<span data-ttu-id="492b0-108">Standard Initialisierungs Modus.</span><span class="sxs-lookup"><span data-stu-id="492b0-108">Default initialization mode.</span></span> <span data-ttu-id="492b0-109">Dadurch wird die Laufzeit initialisiert und der Standardwert erstellt <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="492b0-109">This initializes the runtime and creates the default <xref:System.AppDomain>.</span></span>|  
|`COINITEE_DLL`|<span data-ttu-id="492b0-110">Initialisiert, um eine verwaltete DLL auszuführen.</span><span class="sxs-lookup"><span data-stu-id="492b0-110">Initializes to run a managed DLL.</span></span>|  
|`COINITEE_MAIN`|<span data-ttu-id="492b0-111">Initialisiert, um eine verwaltete exe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="492b0-111">Initializes to run a managed EXE.</span></span> <span data-ttu-id="492b0-112">Dies initialisiert die Laufzeit, erstellt jedoch nicht den Standardwert <xref:System.AppDomain> , der nach der Eingabe der Haupt Routine der exe-Datei erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="492b0-112">This initializes the runtime but does not create the default <xref:System.AppDomain>, which is created after entering the main routine of the EXE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="492b0-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="492b0-113">Requirements</span></span>  

 <span data-ttu-id="492b0-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="492b0-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="492b0-115">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="492b0-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="492b0-116">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="492b0-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="492b0-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="492b0-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="492b0-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="492b0-118">See also</span></span>

- [<span data-ttu-id="492b0-119">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="492b0-119">Metadata Enumerations</span></span>](metadata-enumerations.md)
