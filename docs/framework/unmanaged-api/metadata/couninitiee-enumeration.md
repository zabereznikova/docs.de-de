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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 475ae98d2bf7ea5132c9ec4555070f8bb2999cde
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54744010"
---
# <a name="couninitiee-enumeration"></a><span data-ttu-id="153c4-102">COUNINITIEE-Enumeration</span><span class="sxs-lookup"><span data-stu-id="153c4-102">COUNINITIEE Enumeration</span></span>
<span data-ttu-id="153c4-103">Gibt Konstanten an, die von verwendet [CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md) beim Initialisieren der common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="153c4-103">Specifies constants used by [CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="153c4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="153c4-104">Syntax</span></span>  
  
```  
typedef enum tagCOUNINITEE  
{  
    COUNINITEE_DEFAULT  = 0x0,   
    COUNINITEE_DLL      = 0x1  
} COUNINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="153c4-105">Member</span><span class="sxs-lookup"><span data-stu-id="153c4-105">Members</span></span>  
  
|<span data-ttu-id="153c4-106">Member</span><span class="sxs-lookup"><span data-stu-id="153c4-106">Member</span></span>|<span data-ttu-id="153c4-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="153c4-107">Description</span></span>|  
|------------|-----------------|  
|`COUNINITEE_DEFAULT`|<span data-ttu-id="153c4-108">Gibt die Initialisierung der Standardmodus an.</span><span class="sxs-lookup"><span data-stu-id="153c4-108">Indicates default uninitialization mode.</span></span>|  
|`COUNINITEE_DLL`|<span data-ttu-id="153c4-109">Gibt die Initialisierung im Modus für das Entladen einer Assemblys an.</span><span class="sxs-lookup"><span data-stu-id="153c4-109">Indicates uninitialization mode for unloading an assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="153c4-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="153c4-110">Requirements</span></span>  
 <span data-ttu-id="153c4-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="153c4-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="153c4-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="153c4-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="153c4-113">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="153c4-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="153c4-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="153c4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="153c4-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="153c4-115">See also</span></span>
- [<span data-ttu-id="153c4-116">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="153c4-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
