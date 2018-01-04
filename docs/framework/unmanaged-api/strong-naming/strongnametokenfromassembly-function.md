---
title: StrongNameTokenFromAssembly-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameTokenFromAssembly
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: StrongNameTokenFromAssembly
helpviewer_keywords: StrongNameTokenFromAssembly function [.NET Framework strong naming]
ms.assetid: 0a4b47ee-02f6-4a98-864e-a6f11ca3f2d9
topic_type: apiref
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 29414522eb2586b00ba3158d79155675cb468815
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="strongnametokenfromassembly-function"></a><span data-ttu-id="b34c1-102">StrongNameTokenFromAssembly-Funktion</span><span class="sxs-lookup"><span data-stu-id="b34c1-102">StrongNameTokenFromAssembly Function</span></span>
<span data-ttu-id="b34c1-103">Erstellt ein Token mit starkem Namen aus der angegebenen Assemblydatei an.</span><span class="sxs-lookup"><span data-stu-id="b34c1-103">Creates a strong name token from the specified assembly file.</span></span>  
  
 <span data-ttu-id="b34c1-104">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="b34c1-104">This function has been deprecated.</span></span> <span data-ttu-id="b34c1-105">Verwenden der [ICLRStrongName:: StrongNameTokenFromAssembly](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="b34c1-105">Use the [ICLRStrongName::StrongNameTokenFromAssembly](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b34c1-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="b34c1-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameTokenFromAssembly (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b34c1-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="b34c1-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="b34c1-108">[in] Der Pfad zur Datei (portable Executable)-Datei für die Assembly.</span><span class="sxs-lookup"><span data-stu-id="b34c1-108">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="b34c1-109">[out] Das zurückgegebene strong Name-Token.</span><span class="sxs-lookup"><span data-stu-id="b34c1-109">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="b34c1-110">[out] Die Größe in Bytes, der das Token mit starkem Namen.</span><span class="sxs-lookup"><span data-stu-id="b34c1-110">[out] The size, in bytes, of the strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b34c1-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b34c1-111">Return Value</span></span>  
 <span data-ttu-id="b34c1-112">`true`Bei erfolgreichem Abschluss; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="b34c1-112">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b34c1-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b34c1-113">Remarks</span></span>  
 <span data-ttu-id="b34c1-114">Ein starker Name-Token ist die Kurzform eines öffentlichen Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="b34c1-114">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="b34c1-115">Das Token ist ein 64-Bit-Hash, der aus dem öffentlichen Schlüssel zum Signieren der Assembly erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="b34c1-115">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="b34c1-116">Das Token ist ein Teil des starken Namens für die Assembly und kann aus den Metadaten der Assembly gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="b34c1-116">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="b34c1-117">Nachdem das Token erstellt wurde, sollten Sie rufen die [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) Funktion, um den belegten Speicher freizugeben.</span><span class="sxs-lookup"><span data-stu-id="b34c1-117">After the token is created, you should call the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="b34c1-118">Wenn die `StrongNameTokenFromAssembly` Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) Funktion, um den letzten generierten Fehler abzurufen.</span><span class="sxs-lookup"><span data-stu-id="b34c1-118">If the `StrongNameTokenFromAssembly` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b34c1-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b34c1-119">Requirements</span></span>  
 <span data-ttu-id="b34c1-120">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b34c1-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b34c1-121">**Header:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="b34c1-121">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="b34c1-122">**Bibliothek:** als Ressource in mscoree.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="b34c1-122">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="b34c1-123">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b34c1-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b34c1-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b34c1-124">See Also</span></span>  
 [<span data-ttu-id="b34c1-125">StrongNameTokenFromAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="b34c1-125">StrongNameTokenFromAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md)  
 [<span data-ttu-id="b34c1-126">StrongNameTokenFromAssemblyEx-Methode</span><span class="sxs-lookup"><span data-stu-id="b34c1-126">StrongNameTokenFromAssemblyEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)  
 [<span data-ttu-id="b34c1-127">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b34c1-127">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
