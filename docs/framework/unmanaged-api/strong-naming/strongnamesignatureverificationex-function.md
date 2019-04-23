---
title: StrongNameSignatureVerificationEx-Funktion
ms.date: 03/30/2017
api_name:
- StrongNameSignatureVerificationEx
api_location:
- mscoree.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureVerificationEx
helpviewer_keywords:
- StrongNameSignatureVerificationEx function [.NET Framework strong naming]
ms.assetid: cfe4b634-18bf-44b8-9773-d94fb7e8a480
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 049b7b11473a05d74dc311ca6ee79947039b0dd1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59112904"
---
# <a name="strongnamesignatureverificationex-function"></a><span data-ttu-id="2bfb0-102">StrongNameSignatureVerificationEx-Funktion</span><span class="sxs-lookup"><span data-stu-id="2bfb0-102">StrongNameSignatureVerificationEx Function</span></span>
<span data-ttu-id="2bfb0-103">Ruft einen Wert ab, der angibt, ob das Assemblymanifest im angegebenen Pfad eine Signatur mit starkem Namen enthält.</span><span class="sxs-lookup"><span data-stu-id="2bfb0-103">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature.</span></span>  
  
 <span data-ttu-id="2bfb0-104">Diese Funktion wurde als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="2bfb0-104">This function has been deprecated.</span></span> <span data-ttu-id="2bfb0-105">Verwenden der [ICLRStrongName:: StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="2bfb0-105">Use the [ICLRStrongName::StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bfb0-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="2bfb0-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2bfb0-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="2bfb0-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="2bfb0-108">[in] Der Pfad der übertragbaren ausführbaren Datei (.exe oder .dll) Datei für die Assembly überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="2bfb0-108">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="2bfb0-109">[in] `true` Überprüfung ausführen, auch wenn es ist erforderlich, um registrierungseinstellungen außer Kraft zu setzen ist, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="2bfb0-109">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="2bfb0-110">[out] `true` war die starke Namenssignatur überprüft wird; anderenfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="2bfb0-110">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="2bfb0-111">`pfWasVerified` wird ebenfalls für festgelegt `false` , wenn die Überprüfung aufgrund der registrierungseinstellungen für die erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="2bfb0-111">`pfWasVerified` is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2bfb0-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2bfb0-112">Return Value</span></span>  
 <span data-ttu-id="2bfb0-113">`true` Wenn die Überprüfung erfolgreich war; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="2bfb0-113">`true` if the verification was successful; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2bfb0-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2bfb0-114">Remarks</span></span>  
 <span data-ttu-id="2bfb0-115">`StrongNameSignatureVerificationEx` bietet eine Funktionalität, die ähnlich wie die [StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverification-function.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="2bfb0-115">`StrongNameSignatureVerificationEx` provides a capability similar to the [StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverification-function.md) function.</span></span> <span data-ttu-id="2bfb0-116">Aber die zweite Eingabe, Parameter und der Ausgabeparameter für `StrongNameSignatureVerificationEx` sind vom Typ `BOOLEAN` anstelle von `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="2bfb0-116">However, the second input parameter and the output parameter for `StrongNameSignatureVerificationEx` are of type `BOOLEAN` instead of `DWORD`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2bfb0-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2bfb0-117">Requirements</span></span>  
 <span data-ttu-id="2bfb0-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2bfb0-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2bfb0-119">**Header:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="2bfb0-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="2bfb0-120">**Bibliothek:** Als Ressource in mscoree.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="2bfb0-120">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="2bfb0-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2bfb0-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bfb0-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2bfb0-122">See also</span></span>

- [<span data-ttu-id="2bfb0-123">StrongNameSignatureVerificationEx-Methode</span><span class="sxs-lookup"><span data-stu-id="2bfb0-123">StrongNameSignatureVerificationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [<span data-ttu-id="2bfb0-124">StrongNameSignatureVerification-Methode</span><span class="sxs-lookup"><span data-stu-id="2bfb0-124">StrongNameSignatureVerification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="2bfb0-125">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2bfb0-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
