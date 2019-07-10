---
title: StrongNameSignatureVerificationEx2-Method
ms.date: 03/30/2017
api_name:
- ICLRStrongName2.StrongNameSignatureVerificationEx2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StrongNameSignatureVerificationEx2
helpviewer_keywords:
- StrongNameSignatureVerificationEx2 method, ICLRStrongName2 interface [.NET Framework hosting]
- ICLRStrongName2::StrongNameSignatureVerificationEx2 method [.NET Framework hosting]
ms.assetid: dfd4133f-a074-4db3-a7ee-4f250fe9ad3a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eb4e41f62f5f55969dadd47e80efc56e1c92c94f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67768267"
---
# <a name="strongnamesignatureverificationex2-method"></a><span data-ttu-id="db180-102">StrongNameSignatureVerificationEx2-Method</span><span class="sxs-lookup"><span data-stu-id="db180-102">StrongNameSignatureVerificationEx2 Method</span></span>
<span data-ttu-id="db180-103">Überprüft die Signatur einer Assembly mit starkem Namen, und stellt eine Zuordnung zwischen den ECMA-Schlüssel zu einem echten Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="db180-103">Verifies the signature of a strongly named assembly, and provides a mapping from the ECMA key to a real key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db180-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="db180-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,    [in]  BYTE      *pbEcmaPublicKey,  
    [in]  DWORD     cbEcmaPublicKey,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="db180-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="db180-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="db180-106">[in] Der Pfad der übertragbaren ausführbaren Datei (.exe oder .dll) Datei für die Assembly überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="db180-106">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="db180-107">[in] `true` Überprüfung ausführen, auch wenn es ist erforderlich, um registrierungseinstellungen außer Kraft zu setzen ist, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="db180-107">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pbEcmaPublicKey`  
 <span data-ttu-id="db180-108">[in] Ein Zeiger auf die Zuordnung aus dem öffentlichen Schlüssel der ECMA auf den tatsächlichen Schlüssel, die für die Überprüfung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="db180-108">[in] A pointer to the mapping from the ECMA public key to the real key used for verification.</span></span>  
  
 `cbEcmaPublicKey`  
 <span data-ttu-id="db180-109">[in] Die Länge des tatsächlichen ECMA öffentlichen Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="db180-109">[in] The length of the real ECMA public key.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="db180-110">[out] `true` war die starke Namenssignatur überprüft wird; anderenfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="db180-110">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="db180-111">Dieser Parameter wird auch festgelegt, um `false` , wenn die Überprüfung aufgrund der registrierungseinstellungen für die erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="db180-111">This parameter is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="db180-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="db180-112">Return Value</span></span>  
 <span data-ttu-id="db180-113">`S_OK` Wenn die Überprüfung erfolgreich war; andernfalls ein HRESULT-Wert, der Fehler weist darauf hin (finden Sie unter [Allgemeine HRESULT-Werte](https://go.microsoft.com/fwlink/?LinkId=213878) eine Liste).</span><span class="sxs-lookup"><span data-stu-id="db180-113">`S_OK` if the verification was successful; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db180-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="db180-114">Requirements</span></span>  
 <span data-ttu-id="db180-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db180-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db180-116">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="db180-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="db180-117">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="db180-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="db180-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db180-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db180-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="db180-119">See also</span></span>

- [<span data-ttu-id="db180-120">StrongNameSignatureVerification-Methode</span><span class="sxs-lookup"><span data-stu-id="db180-120">StrongNameSignatureVerification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="db180-121">StrongNameSignatureVerificationEx-Methode</span><span class="sxs-lookup"><span data-stu-id="db180-121">StrongNameSignatureVerificationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [<span data-ttu-id="db180-122">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="db180-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
