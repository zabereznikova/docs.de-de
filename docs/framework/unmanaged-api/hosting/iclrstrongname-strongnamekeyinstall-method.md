---
title: ICLRStrongName::StrongNameKeyInstall-Methode
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameKeyInstall
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameKeyInstall
helpviewer_keywords:
- ICLRStrongName::StrongNameKeyInstall method [.NET Framework hosting]
- StrongNameKeyInstall method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 5c15cf3b-164c-49d1-8e57-e42949d55acf
topic_type:
- apiref
ms.openlocfilehash: 693a5831934647256ac48c8f3a2d30325dee4349
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73135037"
---
# <a name="iclrstrongnamestrongnamekeyinstall-method"></a><span data-ttu-id="edae0-102">ICLRStrongName::StrongNameKeyInstall-Methode</span><span class="sxs-lookup"><span data-stu-id="edae0-102">ICLRStrongName::StrongNameKeyInstall Method</span></span>
<span data-ttu-id="edae0-103">Importiert ein öffentliches/privates Schlüsselpaar in einen Container.</span><span class="sxs-lookup"><span data-stu-id="edae0-103">Imports a public/private key pair into a container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edae0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="edae0-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameKeyInstall (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="edae0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="edae0-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="edae0-106">in Der Name des Schlüssel Containers.</span><span class="sxs-lookup"><span data-stu-id="edae0-106">[in] The name of the key container.</span></span> <span data-ttu-id="edae0-107">`wszKeyContainer` muss eine nicht leere Zeichenfolge sein.</span><span class="sxs-lookup"><span data-stu-id="edae0-107">`wszKeyContainer` must be a non-empty string.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="edae0-108">in Das binäre Schlüsselpaar.</span><span class="sxs-lookup"><span data-stu-id="edae0-108">[in] The binary key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="edae0-109">in Die Größe `pbKeyBlob`in Byte.</span><span class="sxs-lookup"><span data-stu-id="edae0-109">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="edae0-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="edae0-110">Return Value</span></span>  
 <span data-ttu-id="edae0-111">`S_OK`, wenn die Methode erfolgreich abgeschlossen wurde. andernfalls ein HRESULT-Wert, der einen Fehler angibt (siehe [Allgemeine HRESULT-Werte](https://go.microsoft.com/fwlink/?LinkId=213878) für eine Liste).</span><span class="sxs-lookup"><span data-stu-id="edae0-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="edae0-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="edae0-112">Remarks</span></span>  
 <span data-ttu-id="edae0-113">Verwenden Sie die [ICLRStrongName:: StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md) -Methode, um den Schlüssel Container zu löschen.</span><span class="sxs-lookup"><span data-stu-id="edae0-113">Use the [ICLRStrongName::StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md) method to delete the key container.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="edae0-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="edae0-114">Requirements</span></span>  
 <span data-ttu-id="edae0-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="edae0-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="edae0-116">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="edae0-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="edae0-117">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="edae0-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="edae0-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="edae0-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edae0-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="edae0-119">See also</span></span>

- [<span data-ttu-id="edae0-120">StrongNameKeyDelete-Methode</span><span class="sxs-lookup"><span data-stu-id="edae0-120">StrongNameKeyDelete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="edae0-121">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="edae0-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
