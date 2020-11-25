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
ms.openlocfilehash: 27417c379411e242c48d6d9b0c99de833f7ede8a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719267"
---
# <a name="strongnamesignatureverificationex-function"></a><span data-ttu-id="2c441-102">StrongNameSignatureVerificationEx-Funktion</span><span class="sxs-lookup"><span data-stu-id="2c441-102">StrongNameSignatureVerificationEx Function</span></span>

<span data-ttu-id="2c441-103">Ruft einen Wert ab, der angibt, ob das Assemblymanifest im angegebenen Pfad eine Signatur mit starkem Namen enthält.</span><span class="sxs-lookup"><span data-stu-id="2c441-103">Gets a value indicating whether the assembly manifest at the supplied path contains a strong name signature.</span></span>  
  
 <span data-ttu-id="2c441-104">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="2c441-104">This function has been deprecated.</span></span> <span data-ttu-id="2c441-105">Verwenden Sie stattdessen die [ICLRStrongName:: StrongNameSignatureVerificationEx](../hosting/iclrstrongname-strongnamesignatureverificationex-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="2c441-105">Use the [ICLRStrongName::StrongNameSignatureVerificationEx](../hosting/iclrstrongname-strongnamesignatureverificationex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c441-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="2c441-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c441-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="2c441-107">Parameters</span></span>  

 `wszFilePath`  
 <span data-ttu-id="2c441-108">in Der Pfad zur portablen ausführbaren Datei (exe-oder DLL-Datei) für die zu überprüfende Assembly.</span><span class="sxs-lookup"><span data-stu-id="2c441-108">[in] The path to the portable executable (.exe or .dll) file for the assembly to be verified.</span></span>  
  
 `fForceVerification`  
 <span data-ttu-id="2c441-109">[in] `true` zum Durchführen der Überprüfung, auch wenn es erforderlich ist, Registrierungs Einstellungen außer Kraft zu setzen. andernfalls `false` .</span><span class="sxs-lookup"><span data-stu-id="2c441-109">[in] `true` to perform verification, even if it is necessary to override registry settings; otherwise, `false`.</span></span>  
  
 `pfWasVerified`  
 <span data-ttu-id="2c441-110">[out] `true` , wenn die Signatur des starken Namens überprüft wurde. andernfalls `false` .</span><span class="sxs-lookup"><span data-stu-id="2c441-110">[out] `true` if the strong name signature was verified; otherwise, `false`.</span></span> <span data-ttu-id="2c441-111">`pfWasVerified` wird auch auf festgelegt, `false` Wenn die Überprüfung aufgrund von Registrierungs Einstellungen erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="2c441-111">`pfWasVerified` is also set to `false` if the verification was successful due to registry settings.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2c441-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2c441-112">Return Value</span></span>  

 <span data-ttu-id="2c441-113">`true` , wenn die Überprüfung erfolgreich war. andernfalls `false` .</span><span class="sxs-lookup"><span data-stu-id="2c441-113">`true` if the verification was successful; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2c441-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2c441-114">Remarks</span></span>  

 <span data-ttu-id="2c441-115">`StrongNameSignatureVerificationEx` bietet eine ähnliche Funktion wie die [StrongNameSignatureVerification](strongnamesignatureverification-function.md) -Funktion.</span><span class="sxs-lookup"><span data-stu-id="2c441-115">`StrongNameSignatureVerificationEx` provides a capability similar to the [StrongNameSignatureVerification](strongnamesignatureverification-function.md) function.</span></span> <span data-ttu-id="2c441-116">Der zweite Eingabeparameter und der Output-Parameter für `StrongNameSignatureVerificationEx` sind jedoch vom Typ `BOOLEAN` anstelle von `DWORD` .</span><span class="sxs-lookup"><span data-stu-id="2c441-116">However, the second input parameter and the output parameter for `StrongNameSignatureVerificationEx` are of type `BOOLEAN` instead of `DWORD`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c441-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2c441-117">Requirements</span></span>  

 <span data-ttu-id="2c441-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c441-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c441-119">**Header:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="2c441-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="2c441-120">**Bibliothek:** Als Ressource in mscoree.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="2c441-120">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="2c441-121">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c441-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c441-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2c441-122">See also</span></span>

- [<span data-ttu-id="2c441-123">StrongNameSignatureVerificationEx-Methode</span><span class="sxs-lookup"><span data-stu-id="2c441-123">StrongNameSignatureVerificationEx Method</span></span>](../hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [<span data-ttu-id="2c441-124">StrongNameSignatureVerification-Methode</span><span class="sxs-lookup"><span data-stu-id="2c441-124">StrongNameSignatureVerification Method</span></span>](../hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [<span data-ttu-id="2c441-125">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2c441-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
