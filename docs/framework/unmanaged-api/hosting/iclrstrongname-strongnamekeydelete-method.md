---
title: ICLRStrongName::StrongNameKeyDelete-Methode
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameKeyDelete
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameKeyDelete
helpviewer_keywords:
- StrongNameKeyDelete method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameKeyDelete method [.NET Framework hosting]
ms.assetid: 0163412f-f617-4428-89e0-03992fec31e8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 412aa8fd30294ac9681a5edd02bb4bdfe25b3fab
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59143987"
---
# <a name="iclrstrongnamestrongnamekeydelete-method"></a><span data-ttu-id="c1c30-102">ICLRStrongName::StrongNameKeyDelete-Methode</span><span class="sxs-lookup"><span data-stu-id="c1c30-102">ICLRStrongName::StrongNameKeyDelete Method</span></span>
<span data-ttu-id="c1c30-103">Löscht den angegebenen Schlüsselcontainer.</span><span class="sxs-lookup"><span data-stu-id="c1c30-103">Deletes the specified key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1c30-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c1c30-104">Syntax</span></span>  
  
```  
HRESULT StrongNameKeyDelete (  
    [in]  LPCWSTR   wszKeyContainer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c1c30-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c1c30-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="c1c30-106">[in] Der Name des Containers mit dem Schlüssel zu löschen.</span><span class="sxs-lookup"><span data-stu-id="c1c30-106">[in] The name of the key container to delete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c1c30-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c1c30-107">Return Value</span></span>  
 <span data-ttu-id="c1c30-108">`S_OK` Wenn die Methode erfolgreich abgeschlossen. andernfalls ein HRESULT-Wert, der Fehler weist darauf hin (finden Sie unter [Allgemeine HRESULT-Werte](https://go.microsoft.com/fwlink/?LinkId=213878) eine Liste).</span><span class="sxs-lookup"><span data-stu-id="c1c30-108">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c1c30-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c1c30-109">Remarks</span></span>  
 <span data-ttu-id="c1c30-110">Verwenden der [ICLRStrongName:: StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md) Methode, um ein öffentliches/privates Schlüsselpaar in einem Container zu importieren.</span><span class="sxs-lookup"><span data-stu-id="c1c30-110">Use the [ICLRStrongName::StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md) method to import a public/private key pair into a container.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1c30-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c1c30-111">Requirements</span></span>  
 <span data-ttu-id="c1c30-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1c30-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1c30-113">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="c1c30-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="c1c30-114">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c1c30-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c1c30-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1c30-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1c30-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c1c30-116">See also</span></span>

- [<span data-ttu-id="c1c30-117">StrongNameKeyInstall-Methode</span><span class="sxs-lookup"><span data-stu-id="c1c30-117">StrongNameKeyInstall Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="c1c30-118">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c1c30-118">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
