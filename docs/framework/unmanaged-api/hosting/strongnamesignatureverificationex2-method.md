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
ms.openlocfilehash: 5e6f77b9b5da061a75d23d7f3f7b673754b62afd
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006362"
---
# <a name="strongnamesignatureverificationex2-method"></a><span data-ttu-id="3f855-102">StrongNameSignatureVerificationEx2-Method</span><span class="sxs-lookup"><span data-stu-id="3f855-102">StrongNameSignatureVerificationEx2 Method</span></span>
<span data-ttu-id="3f855-103">Überprüft die Signatur einer Assembly mit starkem Namen und stellt eine Zuordnung zwischen dem ECMA-Schlüssel und einem echten Schlüssel bereit.</span><span class="sxs-lookup"><span data-stu-id="3f855-103">Verifies the signature of a strongly named assembly, and provides a mapping from the ECMA key to a real key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f855-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3f855-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,    [in]  BYTE      *pbEcmaPublicKey,  
    [in]  DWORD     cbEcmaPublicKey,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f855-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3f855-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="3f855-106">in Der Pfad zur portablen ausführbaren Datei (exe-oder DLL-Datei) für die zu überprüfende Assembly.</span><span class="sxs-lookup"><span data-stu-id="3f855-106">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="3f855-107">[in] `true` zum Durchführen der Überprüfung, auch wenn es erforderlich ist, Registrierungs Einstellungen außer Kraft zu setzen. andernfalls `false` .</span><span class="sxs-lookup"><span data-stu-id="3f855-107">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pbEcmaPublicKey`  
 <span data-ttu-id="3f855-108">in Ein Zeiger auf die Zuordnung vom öffentlichen ECMA-Schlüssel zu dem Schlüssel, der für die Überprüfung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3f855-108">[in] A pointer to the mapping from the ECMA public key to the real key used for verification.</span></span>  
  
 `cbEcmaPublicKey`  
 <span data-ttu-id="3f855-109">in Die Länge des echten öffentlichen ECMA-Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="3f855-109">[in] The length of the real ECMA public key.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="3f855-110">[out] `true` , wenn die Signatur des starken Namens überprüft wurde. andernfalls `false` .</span><span class="sxs-lookup"><span data-stu-id="3f855-110">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="3f855-111">Dieser Parameter wird auch auf festgelegt, `false` Wenn die Überprüfung aufgrund von Registrierungs Einstellungen erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="3f855-111">This parameter is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3f855-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3f855-112">Return Value</span></span>  
 <span data-ttu-id="3f855-113">`S_OK`, wenn die Überprüfung erfolgreich war. andernfalls ein HRESULT-Wert, der einen Fehler angibt (siehe [Allgemeine HRESULT-Werte](/windows/win32/seccrypto/common-hresult-values) für eine Liste).</span><span class="sxs-lookup"><span data-stu-id="3f855-113">`S_OK` if the verification was successful; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f855-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="3f855-114">Requirements</span></span>  
 <span data-ttu-id="3f855-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f855-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f855-116">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="3f855-116">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="3f855-117">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="3f855-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3f855-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f855-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f855-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3f855-119">See also</span></span>

- [<span data-ttu-id="3f855-120">StrongNameSignatureVerification-Methode</span><span class="sxs-lookup"><span data-stu-id="3f855-120">StrongNameSignatureVerification Method</span></span>](iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="3f855-121">StrongNameSignatureVerificationEx-Methode</span><span class="sxs-lookup"><span data-stu-id="3f855-121">StrongNameSignatureVerificationEx Method</span></span>](iclrstrongname-strongnamesignatureverificationex-method.md)
- [<span data-ttu-id="3f855-122">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3f855-122">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
