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
ms.openlocfilehash: fbc9ea6aab9f0c3d9be95e6affcd04342ce4c5cc
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901072"
---
# <a name="iclrstrongnamestrongnamesignatureverificationex-method"></a><span data-ttu-id="5b82f-102">ICLRStrongName::StrongNameSignatureVerificationEx-Methode</span><span class="sxs-lookup"><span data-stu-id="5b82f-102">ICLRStrongName::StrongNameSignatureVerificationEx Method</span></span>
<span data-ttu-id="5b82f-103">Ruft einen Wert ab, der angibt, ob das Assemblymanifest im angegebenen Pfad eine Signatur mit starkem Namen enthält.</span><span class="sxs-lookup"><span data-stu-id="5b82f-103">Gets a value that indicates whether the assembly manifest at the supplied path contains a strong name signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b82f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5b82f-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b82f-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="5b82f-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="5b82f-106">in Der Pfad zur portablen ausführbaren Datei (exe-oder DLL-Datei) für die zu überprüfende Assembly.</span><span class="sxs-lookup"><span data-stu-id="5b82f-106">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="5b82f-107">[in] `true`, um die Überprüfung auszuführen, auch wenn es erforderlich ist, Registrierungs Einstellungen zu überschreiben. Andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="5b82f-107">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="5b82f-108">[out] `true`, wenn die Signatur des starken Namens überprüft wurde. Andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="5b82f-108">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="5b82f-109">`pfWasVerified` ist auch auf `false` festgelegt, wenn die Überprüfung aufgrund von Registrierungs Einstellungen erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="5b82f-109">`pfWasVerified` is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5b82f-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5b82f-110">Return Value</span></span>  
 <span data-ttu-id="5b82f-111">`S_OK`, wenn die Überprüfung erfolgreich war. andernfalls ein HRESULT-Wert, der einen Fehler angibt (siehe [Allgemeine HRESULT-Werte](/windows/win32/seccrypto/common-hresult-values) für eine Liste).</span><span class="sxs-lookup"><span data-stu-id="5b82f-111">`S_OK` if the verification was successful; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5b82f-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5b82f-112">Remarks</span></span>  
 <span data-ttu-id="5b82f-113">Die [ICLRStrongName:: StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) -Methode bietet eine ähnliche Funktion wie die [ICLRStrongName:: StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="5b82f-113">The [ICLRStrongName::StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) method provides a capability similar to the [ICLRStrongName::StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md) method.</span></span> <span data-ttu-id="5b82f-114">Der zweite Eingabeparameter und der Output-Parameter für [ICLRStrongName:: StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) sind jedoch vom Typ `BOOLEAN` anstatt `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="5b82f-114">However, the second input parameter and the output parameter for [ICLRStrongName::StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) are of type `BOOLEAN` instead of `DWORD`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b82f-115">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5b82f-115">Requirements</span></span>  
 <span data-ttu-id="5b82f-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b82f-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b82f-117">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="5b82f-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="5b82f-118">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="5b82f-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5b82f-119">**.NET Framework Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b82f-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b82f-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5b82f-120">See also</span></span>

- [<span data-ttu-id="5b82f-121">StrongNameSignatureVerification-Methode</span><span class="sxs-lookup"><span data-stu-id="5b82f-121">StrongNameSignatureVerification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="5b82f-122">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5b82f-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
