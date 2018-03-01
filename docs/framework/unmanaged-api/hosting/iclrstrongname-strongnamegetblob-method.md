---
title: ICLRStrongName::StrongNameGetBlob-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRStrongName.StrongNameGetBlob
- ICLRStrongName.StrongNameGetBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameGetBlob
helpviewer_keywords:
- ICLRStrongName::StrongNameGetBlob method [.NET Framework hosting]
- StrongNameGetBlob method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: a24218f8-7196-44be-b7a2-ee9cdd7a85c4
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f1882936723667b616ff930af00ee899f446521e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongnamestrongnamegetblob-method"></a><span data-ttu-id="d65b4-102">ICLRStrongName::StrongNameGetBlob-Methode</span><span class="sxs-lookup"><span data-stu-id="d65b4-102">ICLRStrongName::StrongNameGetBlob Method</span></span>
<span data-ttu-id="d65b4-103">Füllt den angegebenen Puffer mit der binären Darstellung der ausführbaren Datei an der angegebenen Adresse an.</span><span class="sxs-lookup"><span data-stu-id="d65b4-103">Fills the specified buffer with the binary representation of the executable file at the specified address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d65b4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d65b4-104">Syntax</span></span>  
  
```  
HRESULT StrongNameGetBlob (  
    [in]  LPCWSTR    wszFilePath,  
    [in]  BYTE       *pbBlob,  
    [in, out] DWORD  *pcbBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d65b4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d65b4-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="d65b4-106">[in] Einen gültigen Pfad zur ausführbaren Datei geladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="d65b4-106">[in] A valid path to the executable file to be loaded.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="d65b4-107">[in] Der Puffer, in dem die ausführbare Datei geladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="d65b4-107">[in] The buffer into which to load the executable file.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="d65b4-108">[in, out] Die maximale Größe in Bytes, des angeforderten `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="d65b4-108">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="d65b4-109">Nach der Rückgabe der tatsächlichen Größe in Bytes, der `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="d65b4-109">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d65b4-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d65b4-110">Return Value</span></span>  
 <span data-ttu-id="d65b4-111">`S_OK`Wenn die Methode erfolgreich abgeschlossen. andernfalls ein HRESULT-Wert, der Fehler weist darauf hin (finden Sie unter [häufig auftretende HRESULT-Werte](http://go.microsoft.com/fwlink/?LinkId=213878) eine Liste).</span><span class="sxs-lookup"><span data-stu-id="d65b4-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d65b4-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d65b4-112">Requirements</span></span>  
 <span data-ttu-id="d65b4-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d65b4-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d65b4-114">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="d65b4-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="d65b4-115">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d65b4-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d65b4-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d65b4-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d65b4-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d65b4-117">See Also</span></span>  
 [<span data-ttu-id="d65b4-118">StrongNameGetBlobFromImage-Methode</span><span class="sxs-lookup"><span data-stu-id="d65b4-118">StrongNameGetBlobFromImage Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md)  
 [<span data-ttu-id="d65b4-119">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d65b4-119">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
