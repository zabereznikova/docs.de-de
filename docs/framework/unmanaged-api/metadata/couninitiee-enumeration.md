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
ms.openlocfilehash: 0cf1bfa03fd14d6324af60781003a8072a267a7e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62045057"
---
# <a name="couninitiee-enumeration"></a><span data-ttu-id="3d61e-102">COUNINITIEE-Enumeration</span><span class="sxs-lookup"><span data-stu-id="3d61e-102">COUNINITIEE Enumeration</span></span>
<span data-ttu-id="3d61e-103">Gibt Konstanten an, die von verwendet [CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md) beim Initialisieren der common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="3d61e-103">Specifies constants used by [CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d61e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3d61e-104">Syntax</span></span>  
  
```  
typedef enum tagCOUNINITEE  
{  
    COUNINITEE_DEFAULT  = 0x0,   
    COUNINITEE_DLL      = 0x1  
} COUNINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="3d61e-105">Member</span><span class="sxs-lookup"><span data-stu-id="3d61e-105">Members</span></span>  
  
|<span data-ttu-id="3d61e-106">Member</span><span class="sxs-lookup"><span data-stu-id="3d61e-106">Member</span></span>|<span data-ttu-id="3d61e-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3d61e-107">Description</span></span>|  
|------------|-----------------|  
|`COUNINITEE_DEFAULT`|<span data-ttu-id="3d61e-108">Gibt die Initialisierung der Standardmodus an.</span><span class="sxs-lookup"><span data-stu-id="3d61e-108">Indicates default uninitialization mode.</span></span>|  
|`COUNINITEE_DLL`|<span data-ttu-id="3d61e-109">Gibt die Initialisierung im Modus für das Entladen einer Assemblys an.</span><span class="sxs-lookup"><span data-stu-id="3d61e-109">Indicates uninitialization mode for unloading an assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3d61e-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3d61e-110">Requirements</span></span>  
 <span data-ttu-id="3d61e-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d61e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d61e-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3d61e-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3d61e-113">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="3d61e-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3d61e-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d61e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d61e-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3d61e-115">See also</span></span>

- [<span data-ttu-id="3d61e-116">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="3d61e-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
