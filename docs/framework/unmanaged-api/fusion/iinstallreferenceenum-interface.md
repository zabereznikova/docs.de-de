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
ms.openlocfilehash: f56a9049cd4b503124abe9dd4866dc91779e268e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721061"
---
# <a name="iinstallreferenceenum-interface"></a><span data-ttu-id="91b48-102">IInstallReferenceEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="91b48-102">IInstallReferenceEnum Interface</span></span>

<span data-ttu-id="91b48-103">Stellt einen Enumerator für die Assemblys dar, auf die im globalen Assemblycache installiert ist.</span><span class="sxs-lookup"><span data-stu-id="91b48-103">Represents an enumerator for the referenced assemblies installed in the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91b48-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="91b48-104">Syntax</span></span>  
  
```cpp  
interface IInstallReferenceEnum : IUnknown {  
    HRESULT GetNextInstallReferenceItem (  
        [out] IInstallReferenceItem **ppRefItem,  
        [in]  DWORD dwFlags,  
        [in]  LPVOID pvReserved  
    );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="91b48-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="91b48-105">Methods</span></span>  
  
|<span data-ttu-id="91b48-106">Methode</span><span class="sxs-lookup"><span data-stu-id="91b48-106">Method</span></span>|<span data-ttu-id="91b48-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="91b48-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="91b48-108">GetNextInstallReferenceItem-Methode</span><span class="sxs-lookup"><span data-stu-id="91b48-108">GetNextInstallReferenceItem Method</span></span>](iinstallreferenceenum-getnextinstallreferenceitem-method.md)|<span data-ttu-id="91b48-109">Ruft einen Zeiger auf den nächsten `IInstallReferenceItem` in diesem ab `IInstallReferenceEnum` .</span><span class="sxs-lookup"><span data-stu-id="91b48-109">Gets a pointer to the next `IInstallReferenceItem` contained in this `IInstallReferenceEnum`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="91b48-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="91b48-110">Requirements</span></span>  

 <span data-ttu-id="91b48-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91b48-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91b48-112">**Header:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="91b48-112">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="91b48-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91b48-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91b48-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="91b48-114">See also</span></span>

- [<span data-ttu-id="91b48-115">Fusion-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="91b48-115">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="91b48-116">IInstallReferenceItem-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="91b48-116">IInstallReferenceItem Interface</span></span>](iinstallreferenceitem-interface.md)
