---
title: IGCHost2-Schnittstelle
ms.date: 03/30/2017
api_name:
- IGCHost2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCHost2
helpviewer_keywords:
- IGCHost2 interface [.NET Framework hosting]
ms.assetid: e5323fa4-18ac-424d-859d-a65a550d08d9
topic_type:
- apiref
ms.openlocfilehash: 976673a0caab4e041cc80e5536544c195fcf692a
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2020
ms.locfileid: "83805181"
---
# <a name="igchost2-interface"></a><span data-ttu-id="94565-102">IGCHost2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="94565-102">IGCHost2 Interface</span></span>
<span data-ttu-id="94565-103">Bietet Methoden zum Abrufen von Informationen über das Garbage Collection System und zum Steuern einiger Aspekte von Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="94565-103">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="94565-104">Für eine neue Entwicklung empfiehlt es sich, stattdessen die [ICLRGCManager2](iclrgcmanager2-interface.md) -Schnittstelle zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="94565-104">For new development, we recommend that you use the [ICLRGCManager2](iclrgcmanager2-interface.md) interface instead.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="94565-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="94565-105">Methods</span></span>  
  
|<span data-ttu-id="94565-106">Methode</span><span class="sxs-lookup"><span data-stu-id="94565-106">Method</span></span>|<span data-ttu-id="94565-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="94565-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="94565-108">SetGCStartupLimitsEx-Methode</span><span class="sxs-lookup"><span data-stu-id="94565-108">SetGCStartupLimitsEx Method</span></span>](igchost2-setgcstartuplimitsex-method.md)|<span data-ttu-id="94565-109">Legt die Segmentgröße und die maximale Größe für die Generation 0 fest.</span><span class="sxs-lookup"><span data-stu-id="94565-109">Sets the segment size and the maximum size for generation 0.</span></span> <span data-ttu-id="94565-110">Aktiviert die Generation 0 und die Segment Größen größer als `DWORD` .</span><span class="sxs-lookup"><span data-stu-id="94565-110">Enables generation 0 and segment sizes larger than `DWORD`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="94565-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="94565-111">Requirements</span></span>  
 <span data-ttu-id="94565-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94565-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94565-113">**Header:** Gchost. idl, gchost. h</span><span class="sxs-lookup"><span data-stu-id="94565-113">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="94565-114">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="94565-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="94565-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94565-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94565-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="94565-116">See also</span></span>

- [<span data-ttu-id="94565-117">Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="94565-117">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="94565-118">CLR-Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="94565-118">CLR Hosting Interfaces</span></span>](clr-hosting-interfaces.md)
- [<span data-ttu-id="94565-119">CorRuntimeHost-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="94565-119">CorRuntimeHost Coclass</span></span>](corruntimehost-coclass.md)
