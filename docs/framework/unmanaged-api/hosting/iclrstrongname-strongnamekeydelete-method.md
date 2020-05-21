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
ms.openlocfilehash: 8f6f2445d88d608d51be4e6fe1e064efbb58325d
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2020
ms.locfileid: "83763097"
---
# <a name="iclrstrongnamestrongnamekeydelete-method"></a><span data-ttu-id="264b1-102">ICLRStrongName::StrongNameKeyDelete-Methode</span><span class="sxs-lookup"><span data-stu-id="264b1-102">ICLRStrongName::StrongNameKeyDelete Method</span></span>
<span data-ttu-id="264b1-103">Löscht den angegebenen Schlüsselcontainer.</span><span class="sxs-lookup"><span data-stu-id="264b1-103">Deletes the specified key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="264b1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="264b1-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyDelete (  
    [in]  LPCWSTR   wszKeyContainer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="264b1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="264b1-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="264b1-106">in Der Name des zu löschenden Schlüssel Containers.</span><span class="sxs-lookup"><span data-stu-id="264b1-106">[in] The name of the key container to delete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="264b1-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="264b1-107">Return Value</span></span>  
 <span data-ttu-id="264b1-108">`S_OK`, wenn die Methode erfolgreich abgeschlossen wurde. andernfalls ein HRESULT-Wert, der einen Fehler angibt (siehe [Allgemeine HRESULT-Werte](/windows/win32/seccrypto/common-hresult-values) für eine Liste).</span><span class="sxs-lookup"><span data-stu-id="264b1-108">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="264b1-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="264b1-109">Remarks</span></span>  
 <span data-ttu-id="264b1-110">Verwenden Sie die [ICLRStrongName:: StrongNameKeyInstall](iclrstrongname-strongnamekeyinstall-method.md) -Methode, um ein öffentliches/privates Schlüsselpaar in einen Container zu importieren.</span><span class="sxs-lookup"><span data-stu-id="264b1-110">Use the [ICLRStrongName::StrongNameKeyInstall](iclrstrongname-strongnamekeyinstall-method.md) method to import a public/private key pair into a container.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="264b1-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="264b1-111">Requirements</span></span>  
 <span data-ttu-id="264b1-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="264b1-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="264b1-113">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="264b1-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="264b1-114">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="264b1-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="264b1-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="264b1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="264b1-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="264b1-116">See also</span></span>

- [<span data-ttu-id="264b1-117">StrongNameKeyInstall-Methode</span><span class="sxs-lookup"><span data-stu-id="264b1-117">StrongNameKeyInstall Method</span></span>](iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="264b1-118">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="264b1-118">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
