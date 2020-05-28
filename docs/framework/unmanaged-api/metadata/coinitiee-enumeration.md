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
ms.openlocfilehash: f4d1c2f105abb64bf196d0dd8371c2788c97336e
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84005907"
---
# <a name="coinitiee-enumeration"></a><span data-ttu-id="61243-102">COINITIEE-Enumeration</span><span class="sxs-lookup"><span data-stu-id="61243-102">COINITIEE Enumeration</span></span>
<span data-ttu-id="61243-103">Gibt Konstanten an, die von [CoInitializeEE](../hosting/coinitializeee-function.md) beim Initialisieren der Common Language Runtime verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="61243-103">Specifies constants used by [CoInitializeEE](../hosting/coinitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61243-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="61243-104">Syntax</span></span>  
  
```cpp  
typedef enum tagCOINITEE {  
   COINITEE_DEFAULT = 0x0,  
   COINITEE_DLL     = 0x1,  
   COINITEE_MAIN    = 0x2  
} COINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="61243-105">Member</span><span class="sxs-lookup"><span data-stu-id="61243-105">Members</span></span>  
  
|<span data-ttu-id="61243-106">Member</span><span class="sxs-lookup"><span data-stu-id="61243-106">Member</span></span>|<span data-ttu-id="61243-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="61243-107">Description</span></span>|  
|------------|-----------------|  
|`COINITEE_DEFAULT`|<span data-ttu-id="61243-108">Standard Initialisierungs Modus.</span><span class="sxs-lookup"><span data-stu-id="61243-108">Default initialization mode.</span></span> <span data-ttu-id="61243-109">Dadurch wird die Laufzeit initialisiert und der Standardwert erstellt <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="61243-109">This initializes the runtime and creates the default <xref:System.AppDomain>.</span></span>|  
|`COINITEE_DLL`|<span data-ttu-id="61243-110">Initialisiert, um eine verwaltete DLL auszuführen.</span><span class="sxs-lookup"><span data-stu-id="61243-110">Initializes to run a managed DLL.</span></span>|  
|`COINITEE_MAIN`|<span data-ttu-id="61243-111">Initialisiert, um eine verwaltete exe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="61243-111">Initializes to run a managed EXE.</span></span> <span data-ttu-id="61243-112">Dies initialisiert die Laufzeit, erstellt jedoch nicht den Standardwert <xref:System.AppDomain> , der nach der Eingabe der Haupt Routine der exe-Datei erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="61243-112">This initializes the runtime but does not create the default <xref:System.AppDomain>, which is created after entering the main routine of the EXE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="61243-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="61243-113">Requirements</span></span>  
 <span data-ttu-id="61243-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="61243-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61243-115">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="61243-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="61243-116">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="61243-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="61243-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61243-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61243-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="61243-118">See also</span></span>

- [<span data-ttu-id="61243-119">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="61243-119">Metadata Enumerations</span></span>](metadata-enumerations.md)
