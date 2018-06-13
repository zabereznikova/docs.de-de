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
ms.openlocfilehash: dcd7dc7c51caa94308760c0086384c8eea184ee9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443596"
---
# <a name="couninitiee-enumeration"></a><span data-ttu-id="acc46-102">COUNINITIEE-Enumeration</span><span class="sxs-lookup"><span data-stu-id="acc46-102">COUNINITIEE Enumeration</span></span>
<span data-ttu-id="acc46-103">Gibt Konstanten verwendet [CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md) beim Initialisieren der common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="acc46-103">Specifies constants used by [CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acc46-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="acc46-104">Syntax</span></span>  
  
```  
typedef enum tagCOUNINITEE  
{  
    COUNINITEE_DEFAULT  = 0x0,   
    COUNINITEE_DLL      = 0x1  
} COUNINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="acc46-105">Member</span><span class="sxs-lookup"><span data-stu-id="acc46-105">Members</span></span>  
  
|<span data-ttu-id="acc46-106">Member</span><span class="sxs-lookup"><span data-stu-id="acc46-106">Member</span></span>|<span data-ttu-id="acc46-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="acc46-107">Description</span></span>|  
|------------|-----------------|  
|`COUNINITEE_DEFAULT`|<span data-ttu-id="acc46-108">Gibt an, zur Aufhebung der Standardmodus.</span><span class="sxs-lookup"><span data-stu-id="acc46-108">Indicates default uninitialization mode.</span></span>|  
|`COUNINITEE_DLL`|<span data-ttu-id="acc46-109">Gibt die zur Aufhebung der Modus zum Entladen einer Assemblys an.</span><span class="sxs-lookup"><span data-stu-id="acc46-109">Indicates uninitialization mode for unloading an assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="acc46-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="acc46-110">Requirements</span></span>  
 <span data-ttu-id="acc46-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="acc46-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="acc46-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="acc46-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="acc46-113">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="acc46-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="acc46-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="acc46-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acc46-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="acc46-115">See Also</span></span>  
 [<span data-ttu-id="acc46-116">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="acc46-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
