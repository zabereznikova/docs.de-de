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
ms.openlocfilehash: 80df33e9064d9843873c67272bac7a34dbe734cc
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67751614"
---
# <a name="strongnamesignatureverificationex-function"></a><span data-ttu-id="377fb-102">StrongNameSignatureVerificationEx-Funktion</span><span class="sxs-lookup"><span data-stu-id="377fb-102">StrongNameSignatureVerificationEx Function</span></span>
<span data-ttu-id="377fb-103">Ruft einen Wert ab, der angibt, ob das Assemblymanifest im angegebenen Pfad eine Signatur mit starkem Namen enthält.</span><span class="sxs-lookup"><span data-stu-id="377fb-103">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature.</span></span>  
  
 <span data-ttu-id="377fb-104">Diese Funktion wurde als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="377fb-104">This function has been deprecated.</span></span> <span data-ttu-id="377fb-105">Verwenden der [ICLRStrongName:: StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="377fb-105">Use the [ICLRStrongName::StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="377fb-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="377fb-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="377fb-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="377fb-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="377fb-108">[in] Der Pfad der übertragbaren ausführbaren Datei (.exe oder .dll) Datei für die Assembly überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="377fb-108">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="377fb-109">[in] `true` Überprüfung ausführen, auch wenn es ist erforderlich, um registrierungseinstellungen außer Kraft zu setzen ist, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="377fb-109">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="377fb-110">[out] `true` war die starke Namenssignatur überprüft wird; anderenfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="377fb-110">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="377fb-111">`pfWasVerified` wird ebenfalls für festgelegt `false` , wenn die Überprüfung aufgrund der registrierungseinstellungen für die erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="377fb-111">`pfWasVerified` is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="377fb-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="377fb-112">Return Value</span></span>  
 <span data-ttu-id="377fb-113">`true` Wenn die Überprüfung erfolgreich war; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="377fb-113">`true` if the verification was successful; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="377fb-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="377fb-114">Remarks</span></span>  
 <span data-ttu-id="377fb-115">`StrongNameSignatureVerificationEx` bietet eine Funktionalität, die ähnlich wie die [StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverification-function.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="377fb-115">`StrongNameSignatureVerificationEx` provides a capability similar to the [StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverification-function.md) function.</span></span> <span data-ttu-id="377fb-116">Aber die zweite Eingabe, Parameter und der Ausgabeparameter für `StrongNameSignatureVerificationEx` sind vom Typ `BOOLEAN` anstelle von `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="377fb-116">However, the second input parameter and the output parameter for `StrongNameSignatureVerificationEx` are of type `BOOLEAN` instead of `DWORD`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="377fb-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="377fb-117">Requirements</span></span>  
 <span data-ttu-id="377fb-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="377fb-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="377fb-119">**Header:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="377fb-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="377fb-120">**Bibliothek:** Als Ressource in mscoree.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="377fb-120">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="377fb-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="377fb-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="377fb-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="377fb-122">See also</span></span>

- [<span data-ttu-id="377fb-123">StrongNameSignatureVerificationEx-Methode</span><span class="sxs-lookup"><span data-stu-id="377fb-123">StrongNameSignatureVerificationEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [<span data-ttu-id="377fb-124">StrongNameSignatureVerification-Methode</span><span class="sxs-lookup"><span data-stu-id="377fb-124">StrongNameSignatureVerification Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="377fb-125">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="377fb-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
