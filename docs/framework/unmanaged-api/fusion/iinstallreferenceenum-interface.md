---
title: IInstallReferenceEnum-Schnittstelle
ms.date: 03/30/2017
api_name:
- IInstallReferenceEnum
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IInstallReferenceEnum
helpviewer_keywords:
- IInstallReferenceEnum interface [.NET Framework fusion]
ms.assetid: 2863b33b-a541-462c-bbe8-702a2832898e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0d29b9e2a9b9022f682065816a62734d6c5b2d62
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796404"
---
# <a name="iinstallreferenceenum-interface"></a><span data-ttu-id="13204-102">IInstallReferenceEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="13204-102">IInstallReferenceEnum Interface</span></span>
<span data-ttu-id="13204-103">Stellt einen Enumerator für die Assemblys dar, auf die im globalen Assemblycache installiert ist.</span><span class="sxs-lookup"><span data-stu-id="13204-103">Represents an enumerator for the referenced assemblies installed in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13204-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="13204-104">Syntax</span></span>  
  
```cpp  
interface IInstallReferenceEnum : IUnknown {  
    HRESULT GetNextInstallReferenceItem (  
        [out] IInstallReferenceItem **ppRefItem,  
        [in]  DWORD dwFlags,  
        [in]  LPVOID pvReserved  
    );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="13204-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="13204-105">Methods</span></span>  
  
|<span data-ttu-id="13204-106">Methode</span><span class="sxs-lookup"><span data-stu-id="13204-106">Method</span></span>|<span data-ttu-id="13204-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="13204-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="13204-108">GetNextInstallReferenceItem-Methode</span><span class="sxs-lookup"><span data-stu-id="13204-108">GetNextInstallReferenceItem Method</span></span>](iinstallreferenceenum-getnextinstallreferenceitem-method.md)|<span data-ttu-id="13204-109">Ruft einen Zeiger auf den nächsten `IInstallReferenceItem` in diesem `IInstallReferenceEnum`ab.</span><span class="sxs-lookup"><span data-stu-id="13204-109">Gets a pointer to the next `IInstallReferenceItem` contained in this `IInstallReferenceEnum`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="13204-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="13204-110">Requirements</span></span>  
 <span data-ttu-id="13204-111">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13204-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13204-112">**Header:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="13204-112">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="13204-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13204-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13204-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="13204-114">See also</span></span>

- [<span data-ttu-id="13204-115">Fusion-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="13204-115">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="13204-116">IInstallReferenceItem-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="13204-116">IInstallReferenceItem Interface</span></span>](iinstallreferenceitem-interface.md)
