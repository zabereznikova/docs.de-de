---
title: ICLRStrongName::StrongNameSignatureVerificationEx-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.StrongNameSignatureVerificationEx
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::StrongNameSignatureVerificationEx
helpviewer_keywords:
- StrongNameSignatureVerificationEx method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameSignatureVerificationEx method [.NET Framework hosting]
ms.assetid: dbd2f662-208b-4174-b301-5c99af91040f
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 047bc2212e1552a52f0eabf86cc0e86a6945ba39
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongnamestrongnamesignatureverificationex-method"></a><span data-ttu-id="128b0-102">ICLRStrongName::StrongNameSignatureVerificationEx-Methode</span><span class="sxs-lookup"><span data-stu-id="128b0-102">ICLRStrongName::StrongNameSignatureVerificationEx Method</span></span>
<span data-ttu-id="128b0-103">Ruft einen Wert, der angibt, ob das Assemblymanifest im angegebenen Pfad eine starke Namenssignatur enthält.</span><span class="sxs-lookup"><span data-stu-id="128b0-103">Gets a value that indicates whether the assembly manifest at the supplied path contains a strong name signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="128b0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="128b0-104">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="128b0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="128b0-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="128b0-106">[in] Der Pfad zur portable ausführbare (.exe oder .dll)-Datei für die Assembly überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="128b0-106">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="128b0-107">[in] `true` Überprüfung ausführen, auch wenn es zum Überschreiben der registrierungseinstellungen für die erforderlich ist, andernfalls ist `false`.</span><span class="sxs-lookup"><span data-stu-id="128b0-107">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="128b0-108">[out] `true` war die starke Namenssignatur überprüft wurde, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="128b0-108">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="128b0-109">`pfWasVerified`auch `false` , wenn die Überprüfung aufgrund der registrierungseinstellungen für die erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="128b0-109">`pfWasVerified` is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="128b0-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="128b0-110">Return Value</span></span>  
 <span data-ttu-id="128b0-111">`S_OK`Wenn die Überprüfung erfolgreich war; andernfalls ein HRESULT-Wert, der Fehler weist darauf hin (finden Sie unter [häufig auftretende HRESULT-Werte](http://go.microsoft.com/fwlink/?LinkId=213878) eine Liste).</span><span class="sxs-lookup"><span data-stu-id="128b0-111">`S_OK` if the verification was successful; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](http://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="128b0-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="128b0-112">Remarks</span></span>  
 <span data-ttu-id="128b0-113">Die [ICLRStrongName:: StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) Methode bietet eine Funktionalität, die ähnlich wie die [ICLRStrongName:: StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="128b0-113">The [ICLRStrongName::StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) method provides a capability similar to the [ICLRStrongName::StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md) method.</span></span> <span data-ttu-id="128b0-114">Allerdings der zweite Eingabeparameter, und der Ausgabeparameter für [ICLRStrongName:: StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) sind vom Typ `BOOLEAN` anstelle von `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="128b0-114">However, the second input parameter and the output parameter for [ICLRStrongName::StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) are of type `BOOLEAN` instead of `DWORD`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="128b0-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="128b0-115">Requirements</span></span>  
 <span data-ttu-id="128b0-116">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="128b0-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="128b0-117">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="128b0-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="128b0-118">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="128b0-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="128b0-119">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="128b0-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="128b0-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="128b0-120">See Also</span></span>  
 [<span data-ttu-id="128b0-121">StrongNameSignatureVerification-Methode</span><span class="sxs-lookup"><span data-stu-id="128b0-121">StrongNameSignatureVerification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)  
 [<span data-ttu-id="128b0-122">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="128b0-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
