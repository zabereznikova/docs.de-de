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
ms.openlocfilehash: 9caeb72c57260012ae2b459950bf19d907da1d98
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671550"
---
# <a name="iclrstrongnamestrongnamesignatureverificationex-method"></a><span data-ttu-id="6b6e3-102">ICLRStrongName::StrongNameSignatureVerificationEx-Methode</span><span class="sxs-lookup"><span data-stu-id="6b6e3-102">ICLRStrongName::StrongNameSignatureVerificationEx Method</span></span>

<span data-ttu-id="6b6e3-103">Ruft einen Wert ab, der angibt, ob das Assemblymanifest im angegebenen Pfad eine Signatur mit starkem Namen enthält.</span><span class="sxs-lookup"><span data-stu-id="6b6e3-103">Gets a value that indicates whether the assembly manifest at the supplied path contains a strong name signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b6e3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6b6e3-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6b6e3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6b6e3-105">Parameters</span></span>  

 `wszFilePath`  
 <span data-ttu-id="6b6e3-106">in Der Pfad zur portablen ausführbaren Datei (exe-oder DLL-Datei) für die zu überprüfende Assembly.</span><span class="sxs-lookup"><span data-stu-id="6b6e3-106">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="6b6e3-107">[in] `true` zum Durchführen der Überprüfung, auch wenn es erforderlich ist, Registrierungs Einstellungen außer Kraft zu setzen. andernfalls `false` .</span><span class="sxs-lookup"><span data-stu-id="6b6e3-107">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="6b6e3-108">[out] `true` , wenn die Signatur des starken Namens überprüft wurde. andernfalls `false` .</span><span class="sxs-lookup"><span data-stu-id="6b6e3-108">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="6b6e3-109">`pfWasVerified` wird auch auf festgelegt, `false` Wenn die Überprüfung aufgrund von Registrierungs Einstellungen erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="6b6e3-109">`pfWasVerified` is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6b6e3-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6b6e3-110">Return Value</span></span>  

 <span data-ttu-id="6b6e3-111">`S_OK` , wenn die Überprüfung erfolgreich war. andernfalls ein HRESULT-Wert, der einen Fehler angibt (siehe [Allgemeine HRESULT-Werte](/windows/win32/seccrypto/common-hresult-values) für eine Liste).</span><span class="sxs-lookup"><span data-stu-id="6b6e3-111">`S_OK` if the verification was successful; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6b6e3-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6b6e3-112">Remarks</span></span>  

 <span data-ttu-id="6b6e3-113">Die [ICLRStrongName:: StrongNameSignatureVerificationEx](iclrstrongname-strongnamesignatureverificationex-method.md) -Methode bietet eine ähnliche Funktion wie die [ICLRStrongName:: StrongNameSignatureVerification](iclrstrongname-strongnamesignatureverification-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="6b6e3-113">The [ICLRStrongName::StrongNameSignatureVerificationEx](iclrstrongname-strongnamesignatureverificationex-method.md) method provides a capability similar to the [ICLRStrongName::StrongNameSignatureVerification](iclrstrongname-strongnamesignatureverification-method.md) method.</span></span> <span data-ttu-id="6b6e3-114">Der zweite Eingabeparameter und der Output-Parameter für [ICLRStrongName:: StrongNameSignatureVerificationEx](iclrstrongname-strongnamesignatureverificationex-method.md) sind jedoch vom Typ `BOOLEAN` anstelle von `DWORD` .</span><span class="sxs-lookup"><span data-stu-id="6b6e3-114">However, the second input parameter and the output parameter for [ICLRStrongName::StrongNameSignatureVerificationEx](iclrstrongname-strongnamesignatureverificationex-method.md) are of type `BOOLEAN` instead of `DWORD`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b6e3-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="6b6e3-115">Requirements</span></span>  

 <span data-ttu-id="6b6e3-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6b6e3-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b6e3-117">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="6b6e3-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="6b6e3-118">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="6b6e3-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6b6e3-119">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b6e3-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b6e3-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6b6e3-120">See also</span></span>

- [<span data-ttu-id="6b6e3-121">StrongNameSignatureVerification-Methode</span><span class="sxs-lookup"><span data-stu-id="6b6e3-121">StrongNameSignatureVerification Method</span></span>](iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="6b6e3-122">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6b6e3-122">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
