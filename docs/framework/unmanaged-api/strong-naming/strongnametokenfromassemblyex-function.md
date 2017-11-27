---
title: StrongNameTokenFromAssemblyEx-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameTokenFromAssemblyEx
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: StrongNameTokenFromAssemblyEx
helpviewer_keywords: StrongNameTokenFromAssemblyEx function [.NET Framework strong naming]
ms.assetid: 67a8a9f2-dee3-44b2-a1c0-f307a3bdf90f
topic_type: apiref
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ef530595d92995124c590e70ac5ffc32a228c67a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="strongnametokenfromassemblyex-function"></a><span data-ttu-id="2347e-102">StrongNameTokenFromAssemblyEx-Funktion</span><span class="sxs-lookup"><span data-stu-id="2347e-102">StrongNameTokenFromAssemblyEx Function</span></span>
<span data-ttu-id="2347e-103">Erstellt ein Token mit starkem Namen aus der angegebenen Assemblydatei und gibt den öffentlichen Schlüssel, den das Token darstellt.</span><span class="sxs-lookup"><span data-stu-id="2347e-103">Creates a strong name token from the specified assembly file, and returns the public key that the token represents.</span></span>  
  
 <span data-ttu-id="2347e-104">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="2347e-104">This function has been deprecated.</span></span> <span data-ttu-id="2347e-105">Verwenden der [ICLRStrongName:: StrongNameTokenFromAssemblyEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="2347e-105">Use the [ICLRStrongName::StrongNameTokenFromAssemblyEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2347e-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="2347e-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameTokenFromAssemblyEx (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2347e-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="2347e-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="2347e-108">[in] Der Pfad zur Datei (portable Executable)-Datei für die Assembly.</span><span class="sxs-lookup"><span data-stu-id="2347e-108">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="2347e-109">[out] Das zurückgegebene strong Name-Token.</span><span class="sxs-lookup"><span data-stu-id="2347e-109">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="2347e-110">[out] Die Größe in Bytes, der das Token mit starkem Namen.</span><span class="sxs-lookup"><span data-stu-id="2347e-110">[out] The size, in bytes, of the strong name token.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="2347e-111">[out] Der zurückgegebene öffentliche Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="2347e-111">[out] The returned public key.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="2347e-112">[out] Die Größe in Bytes, des öffentlichen Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="2347e-112">[out] The size, in bytes, of the public key.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2347e-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2347e-113">Return Value</span></span>  
 <span data-ttu-id="2347e-114">`true`Bei erfolgreichem Abschluss; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="2347e-114">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2347e-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2347e-115">Remarks</span></span>  
 <span data-ttu-id="2347e-116">Ein starker Name-Token ist die Kurzform eines öffentlichen Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="2347e-116">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="2347e-117">Das Token ist ein 64-Bit-Hash, der aus dem öffentlichen Schlüssel zum Signieren der Assembly erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="2347e-117">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="2347e-118">Das Token ist ein Teil des starken Namens für die Assembly und kann aus den Metadaten der Assembly gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="2347e-118">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="2347e-119">Nachdem der Schlüssel abgerufen und das Token wird erstellt, Sie sollten Aufrufen der [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) Funktion, um den belegten Speicher freizugeben.</span><span class="sxs-lookup"><span data-stu-id="2347e-119">After the key is retrieved and the token is created, you should call the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="2347e-120">Wenn die `StrongNameTokenFromAssemblyEx` Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) Funktion, um den letzten generierten Fehler abzurufen.</span><span class="sxs-lookup"><span data-stu-id="2347e-120">If the `StrongNameTokenFromAssemblyEx` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2347e-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2347e-121">Requirements</span></span>  
 <span data-ttu-id="2347e-122">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2347e-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2347e-123">**Header:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="2347e-123">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="2347e-124">**Bibliothek:** als Ressource in mscoree.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="2347e-124">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="2347e-125">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2347e-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2347e-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2347e-126">See Also</span></span>  
 [<span data-ttu-id="2347e-127">StrongNameTokenFromAssemblyEx-Methode</span><span class="sxs-lookup"><span data-stu-id="2347e-127">StrongNameTokenFromAssemblyEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)  
 [<span data-ttu-id="2347e-128">StrongNameTokenFromAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="2347e-128">StrongNameTokenFromAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md)  
 [<span data-ttu-id="2347e-129">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2347e-129">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
