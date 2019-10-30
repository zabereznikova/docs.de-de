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
ms.openlocfilehash: ca428d680df1710d8e74441d9945d4c3545b0482
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121143"
---
# <a name="strongnamesignatureverificationex-function"></a><span data-ttu-id="05295-102">StrongNameSignatureVerificationEx-Funktion</span><span class="sxs-lookup"><span data-stu-id="05295-102">StrongNameSignatureVerificationEx Function</span></span>
<span data-ttu-id="05295-103">Ruft einen Wert ab, der angibt, ob das Assemblymanifest im angegebenen Pfad eine Signatur mit starkem Namen enthält.</span><span class="sxs-lookup"><span data-stu-id="05295-103">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature.</span></span>  
  
 <span data-ttu-id="05295-104">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="05295-104">This function has been deprecated.</span></span> <span data-ttu-id="05295-105">Verwenden Sie stattdessen die [ICLRStrongName:: StrongNameSignatureVerificationEx](../hosting/iclrstrongname-strongnamesignatureverificationex-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="05295-105">Use the [ICLRStrongName::StrongNameSignatureVerificationEx](../hosting/iclrstrongname-strongnamesignatureverificationex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05295-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="05295-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="05295-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="05295-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="05295-108">in Der Pfad zur portablen ausführbaren Datei (exe-oder DLL-Datei) für die zu überprüfende Assembly.</span><span class="sxs-lookup"><span data-stu-id="05295-108">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="05295-109">[in] `true`, um die Überprüfung auszuführen, auch wenn es erforderlich ist, Registrierungs Einstellungen zu überschreiben. Andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="05295-109">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="05295-110">[out] `true`, wenn die Signatur des starken Namens überprüft wurde. Andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="05295-110">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="05295-111">`pfWasVerified` ist auch auf `false` festgelegt, wenn die Überprüfung aufgrund von Registrierungs Einstellungen erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="05295-111">`pfWasVerified` is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="05295-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="05295-112">Return Value</span></span>  
 <span data-ttu-id="05295-113">`true`, wenn die Überprüfung erfolgreich war. Andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="05295-113">`true` if the verification was successful; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="05295-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="05295-114">Remarks</span></span>  
 <span data-ttu-id="05295-115">`StrongNameSignatureVerificationEx` bietet eine ähnliche Funktion wie die [StrongNameSignatureVerification](strongnamesignatureverification-function.md) -Funktion.</span><span class="sxs-lookup"><span data-stu-id="05295-115">`StrongNameSignatureVerificationEx` provides a capability similar to the [StrongNameSignatureVerification](strongnamesignatureverification-function.md) function.</span></span> <span data-ttu-id="05295-116">Der zweite Eingabeparameter und der Output-Parameter für `StrongNameSignatureVerificationEx` sind jedoch vom Typ `BOOLEAN` anstelle von `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="05295-116">However, the second input parameter and the output parameter for `StrongNameSignatureVerificationEx` are of type `BOOLEAN` instead of `DWORD`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05295-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="05295-117">Requirements</span></span>  
 <span data-ttu-id="05295-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05295-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05295-119">**Header:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="05295-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="05295-120">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="05295-120">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="05295-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05295-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05295-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="05295-122">See also</span></span>

- [<span data-ttu-id="05295-123">StrongNameSignatureVerificationEx-Methode</span><span class="sxs-lookup"><span data-stu-id="05295-123">StrongNameSignatureVerificationEx Method</span></span>](../hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [<span data-ttu-id="05295-124">StrongNameSignatureVerification-Methode</span><span class="sxs-lookup"><span data-stu-id="05295-124">StrongNameSignatureVerification Method</span></span>](../hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="05295-125">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="05295-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
