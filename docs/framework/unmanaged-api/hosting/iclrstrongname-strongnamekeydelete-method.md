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
ms.openlocfilehash: 46345ae570673c9c9c0c58fb6edea1464ba8dd91
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671693"
---
# <a name="iclrstrongnamestrongnamekeydelete-method"></a><span data-ttu-id="76e86-102">ICLRStrongName::StrongNameKeyDelete-Methode</span><span class="sxs-lookup"><span data-stu-id="76e86-102">ICLRStrongName::StrongNameKeyDelete Method</span></span>

<span data-ttu-id="76e86-103">Löscht den angegebenen Schlüsselcontainer.</span><span class="sxs-lookup"><span data-stu-id="76e86-103">Deletes the specified key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76e86-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="76e86-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyDelete (  
    [in]  LPCWSTR   wszKeyContainer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="76e86-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="76e86-105">Parameters</span></span>  

 `wszKeyContainer`  
 <span data-ttu-id="76e86-106">in Der Name des zu löschenden Schlüssel Containers.</span><span class="sxs-lookup"><span data-stu-id="76e86-106">[in] The name of the key container to delete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="76e86-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="76e86-107">Return Value</span></span>  

 <span data-ttu-id="76e86-108">`S_OK` , wenn die Methode erfolgreich abgeschlossen wurde. andernfalls ein HRESULT-Wert, der einen Fehler angibt (siehe [Allgemeine HRESULT-Werte](/windows/win32/seccrypto/common-hresult-values) für eine Liste).</span><span class="sxs-lookup"><span data-stu-id="76e86-108">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="76e86-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="76e86-109">Remarks</span></span>  

 <span data-ttu-id="76e86-110">Verwenden Sie die [ICLRStrongName:: StrongNameKeyInstall](iclrstrongname-strongnamekeyinstall-method.md) -Methode, um ein öffentliches/privates Schlüsselpaar in einen Container zu importieren.</span><span class="sxs-lookup"><span data-stu-id="76e86-110">Use the [ICLRStrongName::StrongNameKeyInstall](iclrstrongname-strongnamekeyinstall-method.md) method to import a public/private key pair into a container.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76e86-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="76e86-111">Requirements</span></span>  

 <span data-ttu-id="76e86-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="76e86-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76e86-113">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="76e86-113">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="76e86-114">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="76e86-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="76e86-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76e86-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76e86-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="76e86-116">See also</span></span>

- [<span data-ttu-id="76e86-117">StrongNameKeyInstall-Methode</span><span class="sxs-lookup"><span data-stu-id="76e86-117">StrongNameKeyInstall Method</span></span>](iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="76e86-118">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="76e86-118">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
