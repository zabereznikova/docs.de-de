---
title: ICLRStrongName::StrongNameKeyInstall-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.StrongNameKeyInstall
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::StrongNameKeyInstall
helpviewer_keywords:
- ICLRStrongName::StrongNameKeyInstall method [.NET Framework hosting]
- StrongNameKeyInstall method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 5c15cf3b-164c-49d1-8e57-e42949d55acf
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: df1bdb5d6d6018855cb76b48d58e557a61288a51
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongnamestrongnamekeyinstall-method"></a><span data-ttu-id="c8983-102">ICLRStrongName::StrongNameKeyInstall-Methode</span><span class="sxs-lookup"><span data-stu-id="c8983-102">ICLRStrongName::StrongNameKeyInstall Method</span></span>
<span data-ttu-id="c8983-103">Importiert ein öffentliches/privates Schlüsselpaar in einen Container.</span><span class="sxs-lookup"><span data-stu-id="c8983-103">Imports a public/private key pair into a container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8983-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c8983-104">Syntax</span></span>  
  
```  
HRESULT StrongNameKeyInstall (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c8983-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c8983-105">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="c8983-106">[in] Der Name des Schlüsselcontainers.</span><span class="sxs-lookup"><span data-stu-id="c8983-106">[in] The name of the key container.</span></span> <span data-ttu-id="c8983-107">`wszKeyContainer`eine nicht leere Zeichenfolge muss sein.</span><span class="sxs-lookup"><span data-stu-id="c8983-107">`wszKeyContainer` must be a non-empty string.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="c8983-108">[in] Das binäre Schlüsselpaar.</span><span class="sxs-lookup"><span data-stu-id="c8983-108">[in] The binary key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="c8983-109">[in] Die Größe in Bytes, der `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="c8983-109">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c8983-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c8983-110">Return Value</span></span>  
 <span data-ttu-id="c8983-111">`S_OK`Wenn die Methode erfolgreich abgeschlossen. andernfalls ein HRESULT-Wert, der Fehler weist darauf hin (finden Sie unter [häufig auftretende HRESULT-Werte](http://go.microsoft.com/fwlink/?LinkId=213878) eine Liste).</span><span class="sxs-lookup"><span data-stu-id="c8983-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c8983-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c8983-112">Remarks</span></span>  
 <span data-ttu-id="c8983-113">Verwenden der [ICLRStrongName:: StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md) Methode, um den Schlüsselcontainer zu löschen.</span><span class="sxs-lookup"><span data-stu-id="c8983-113">Use the [ICLRStrongName::StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md) method to delete the key container.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8983-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c8983-114">Requirements</span></span>  
 <span data-ttu-id="c8983-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8983-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8983-116">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="c8983-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="c8983-117">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c8983-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c8983-118">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8983-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8983-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c8983-119">See Also</span></span>  
 [<span data-ttu-id="c8983-120">StrongNameKeyDelete-Methode</span><span class="sxs-lookup"><span data-stu-id="c8983-120">StrongNameKeyDelete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md)  
 [<span data-ttu-id="c8983-121">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c8983-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
