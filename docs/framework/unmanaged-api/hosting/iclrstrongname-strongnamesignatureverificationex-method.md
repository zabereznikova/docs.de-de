---
title: ICLRStrongName::StrongNameSignatureVerificationEx-Methode
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureVerificationEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureVerificationEx
helpviewer_keywords:
- StrongNameSignatureVerificationEx method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameSignatureVerificationEx method [.NET Framework hosting]
ms.assetid: dbd2f662-208b-4174-b301-5c99af91040f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ad25603f5acd32aa21192f86364976eb93d23540
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54717544"
---
# <a name="iclrstrongnamestrongnamesignatureverificationex-method"></a><span data-ttu-id="c2813-102">ICLRStrongName::StrongNameSignatureVerificationEx-Methode</span><span class="sxs-lookup"><span data-stu-id="c2813-102">ICLRStrongName::StrongNameSignatureVerificationEx Method</span></span>
<span data-ttu-id="c2813-103">Ruft einen Wert, der angibt, ob das Assemblymanifest im angegebenen Pfad eine Signatur mit starkem Namen enthält.</span><span class="sxs-lookup"><span data-stu-id="c2813-103">Gets a value that indicates whether the assembly manifest at the supplied path contains a strong name signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2813-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c2813-104">Syntax</span></span>  
  
```  
HRESULT StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c2813-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c2813-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="c2813-106">[in] Der Pfad der übertragbaren ausführbaren Datei (.exe oder .dll) Datei für die Assembly überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="c2813-106">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="c2813-107">[in] `true` Überprüfung ausführen, auch wenn es ist erforderlich, um registrierungseinstellungen außer Kraft zu setzen ist, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="c2813-107">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="c2813-108">[out] `true` war die starke Namenssignatur überprüft wird; anderenfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="c2813-108">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="c2813-109">`pfWasVerified` wird ebenfalls für festgelegt `false` , wenn die Überprüfung aufgrund der registrierungseinstellungen für die erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="c2813-109">`pfWasVerified` is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c2813-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c2813-110">Return Value</span></span>  
 <span data-ttu-id="c2813-111">`S_OK` Wenn die Überprüfung erfolgreich war; andernfalls ein HRESULT-Wert, der Fehler weist darauf hin (finden Sie unter [Allgemeine HRESULT-Werte](https://go.microsoft.com/fwlink/?LinkId=213878) eine Liste).</span><span class="sxs-lookup"><span data-stu-id="c2813-111">`S_OK` if the verification was successful; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c2813-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c2813-112">Remarks</span></span>  
 <span data-ttu-id="c2813-113">Die [ICLRStrongName:: StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) Methode bietet eine ähnliche Funktion der [ICLRStrongName:: StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="c2813-113">The [ICLRStrongName::StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) method provides a capability similar to the [ICLRStrongName::StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md) method.</span></span> <span data-ttu-id="c2813-114">Aber die zweite Eingabe, Parameter und der Ausgabeparameter für [ICLRStrongName:: StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) sind vom Typ `BOOLEAN` anstelle von `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="c2813-114">However, the second input parameter and the output parameter for [ICLRStrongName::StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) are of type `BOOLEAN` instead of `DWORD`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2813-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c2813-115">Requirements</span></span>  
 <span data-ttu-id="c2813-116">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2813-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2813-117">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="c2813-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="c2813-118">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c2813-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c2813-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2813-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2813-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c2813-120">See also</span></span>
- [<span data-ttu-id="c2813-121">StrongNameSignatureVerification-Methode</span><span class="sxs-lookup"><span data-stu-id="c2813-121">StrongNameSignatureVerification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="c2813-122">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c2813-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
