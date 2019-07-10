---
title: StrongNameTokenFromAssembly-Funktion
ms.date: 03/30/2017
api_name:
- StrongNameTokenFromAssembly
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameTokenFromAssembly
helpviewer_keywords:
- StrongNameTokenFromAssembly function [.NET Framework strong naming]
ms.assetid: 0a4b47ee-02f6-4a98-864e-a6f11ca3f2d9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 484dacd4d9803139edf3fd5bad22c164d50de3dc
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67757237"
---
# <a name="strongnametokenfromassembly-function"></a><span data-ttu-id="33cdd-102">StrongNameTokenFromAssembly-Funktion</span><span class="sxs-lookup"><span data-stu-id="33cdd-102">StrongNameTokenFromAssembly Function</span></span>
<span data-ttu-id="33cdd-103">Erstellt ein Token mit starkem Namen aus der angegebenen Assemblydatei.</span><span class="sxs-lookup"><span data-stu-id="33cdd-103">Creates a strong name token from the specified assembly file.</span></span>  
  
 <span data-ttu-id="33cdd-104">Diese Funktion wurde als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="33cdd-104">This function has been deprecated.</span></span> <span data-ttu-id="33cdd-105">Verwenden der [ICLRStrongName:: StrongNameTokenFromAssembly](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="33cdd-105">Use the [ICLRStrongName::StrongNameTokenFromAssembly](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33cdd-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="33cdd-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameTokenFromAssembly (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="33cdd-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="33cdd-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="33cdd-108">[in] Der Pfad zu der PE (portable Executable)-Datei für die Assembly.</span><span class="sxs-lookup"><span data-stu-id="33cdd-108">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="33cdd-109">[out] Das zurückgegebene strong Name-Token.</span><span class="sxs-lookup"><span data-stu-id="33cdd-109">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="33cdd-110">[out] Die Größe in Bytes, der das Token mit starkem Namen.</span><span class="sxs-lookup"><span data-stu-id="33cdd-110">[out] The size, in bytes, of the strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="33cdd-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="33cdd-111">Return Value</span></span>  
 <span data-ttu-id="33cdd-112">`true` Bei erfolgreichem Abschluss; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="33cdd-112">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="33cdd-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="33cdd-113">Remarks</span></span>  
 <span data-ttu-id="33cdd-114">Ein starker Name-Token ist die Kurzform für einen öffentlichen Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="33cdd-114">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="33cdd-115">Das Token ist ein 64-Bit-Hash, der aus dem öffentlichen Schlüssel zum Signieren der Assembly erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="33cdd-115">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="33cdd-116">Das Token ist ein Bestandteil des starken Namens für die Assembly, und Sie können aus den Metadaten der Assembly gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="33cdd-116">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="33cdd-117">Nachdem das Token erstellt wurde, sollten Sie rufen die [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) Funktion, um den belegten Arbeitsspeicher freizugeben.</span><span class="sxs-lookup"><span data-stu-id="33cdd-117">After the token is created, you should call the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="33cdd-118">Wenn die `StrongNameTokenFromAssembly` Funktion nicht erfolgreich abgeschlossen wurde, rufen Sie die [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) Funktion, um den letzten generierten Fehler abzurufen.</span><span class="sxs-lookup"><span data-stu-id="33cdd-118">If the `StrongNameTokenFromAssembly` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33cdd-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="33cdd-119">Requirements</span></span>  
 <span data-ttu-id="33cdd-120">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33cdd-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33cdd-121">**Header:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="33cdd-121">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="33cdd-122">**Bibliothek:** Als Ressource in mscoree.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="33cdd-122">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="33cdd-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33cdd-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33cdd-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="33cdd-124">See also</span></span>

- [<span data-ttu-id="33cdd-125">StrongNameTokenFromAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="33cdd-125">StrongNameTokenFromAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md)
- [<span data-ttu-id="33cdd-126">StrongNameTokenFromAssemblyEx-Methode</span><span class="sxs-lookup"><span data-stu-id="33cdd-126">StrongNameTokenFromAssemblyEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)
- [<span data-ttu-id="33cdd-127">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="33cdd-127">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
