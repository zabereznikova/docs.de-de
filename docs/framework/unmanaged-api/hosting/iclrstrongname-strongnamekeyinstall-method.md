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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 415df9928572e095c529119bf2e726fa383577b0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59224948"
---
# <a name="iclrstrongnamestrongnamekeyinstall-method"></a><span data-ttu-id="5e817-102">ICLRStrongName::StrongNameKeyInstall-Methode</span><span class="sxs-lookup"><span data-stu-id="5e817-102">ICLRStrongName::StrongNameKeyInstall Method</span></span>
<span data-ttu-id="5e817-103">Importiert ein öffentliches/privates Schlüsselpaar in einen Container.</span><span class="sxs-lookup"><span data-stu-id="5e817-103">Imports a public/private key pair into a container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e817-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5e817-104">Syntax</span></span>  
  
```  
HRESULT StrongNameKeyInstall (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5e817-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5e817-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="5e817-106">[in] Der Name des Containers mit dem Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="5e817-106">[in] The name of the key container.</span></span> `wszKeyContainer` <span data-ttu-id="5e817-107">eine nicht leere Zeichenfolge muss sein.</span><span class="sxs-lookup"><span data-stu-id="5e817-107">must be a non-empty string.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="5e817-108">[in] Das binäre Schlüsselpaar.</span><span class="sxs-lookup"><span data-stu-id="5e817-108">[in] The binary key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="5e817-109">[in] Die Größe in Bytes, des `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="5e817-109">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5e817-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5e817-110">Return Value</span></span>  
 `S_OK` <span data-ttu-id="5e817-111">Wenn die Methode erfolgreich abgeschlossen. andernfalls ein HRESULT-Wert, der Fehler weist darauf hin (finden Sie unter [Allgemeine HRESULT-Werte](https://go.microsoft.com/fwlink/?LinkId=213878) eine Liste).</span><span class="sxs-lookup"><span data-stu-id="5e817-111">if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5e817-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5e817-112">Remarks</span></span>  
 <span data-ttu-id="5e817-113">Verwenden der [ICLRStrongName:: StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md) Methode, um den Schlüsselcontainer zu löschen.</span><span class="sxs-lookup"><span data-stu-id="5e817-113">Use the [ICLRStrongName::StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md) method to delete the key container.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e817-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5e817-114">Requirements</span></span>  
 <span data-ttu-id="5e817-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e817-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e817-116">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="5e817-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="5e817-117">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="5e817-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="5e817-118">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="5e817-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5e817-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5e817-119">See also</span></span>

- [<span data-ttu-id="5e817-120">StrongNameKeyDelete-Methode</span><span class="sxs-lookup"><span data-stu-id="5e817-120">StrongNameKeyDelete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="5e817-121">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5e817-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
