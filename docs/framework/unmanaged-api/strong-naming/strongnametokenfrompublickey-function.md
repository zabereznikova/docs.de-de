---
title: StrongNameTokenFromPublicKey-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameTokenFromPublicKey
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type: COM
f1_keywords: StrongNameTokenFromPublicKey
helpviewer_keywords: StrongNameTokenFromPublicKey function [.NET Framework strong naming]
ms.assetid: 997e9e57-abb2-4217-bf20-1df621a75add
topic_type: apiref
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0cb649f43bfea2e11c986aa3fff5a702e2b58c25
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="strongnametokenfrompublickey-function"></a><span data-ttu-id="2083a-102">StrongNameTokenFromPublicKey-Funktion</span><span class="sxs-lookup"><span data-stu-id="2083a-102">StrongNameTokenFromPublicKey Function</span></span>
<span data-ttu-id="2083a-103">Ruft ein Token, das einen öffentlichen Schlüssel darstellt.</span><span class="sxs-lookup"><span data-stu-id="2083a-103">Gets a token representing a public key.</span></span> <span data-ttu-id="2083a-104">Ein starker Name-Token ist die Kurzform eines öffentlichen Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="2083a-104">A strong name token is the shortened form of a public key.</span></span>  
  
 <span data-ttu-id="2083a-105">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="2083a-105">This function has been deprecated.</span></span> <span data-ttu-id="2083a-106">Verwenden der [ICLRStrongName:: StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="2083a-106">Use the [ICLRStrongName::StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2083a-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="2083a-107">Syntax</span></span>  
  
```  
BOOLEANStrongNameTokenFromPublicKey (   
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2083a-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="2083a-108">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="2083a-109">[in] Eine Struktur des Typs [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) , enthält den öffentlichen Teil des Schlüsselpaars verwendet, um die Signatur mit starkem Namen generieren.</span><span class="sxs-lookup"><span data-stu-id="2083a-109">[in] A structure of type [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="2083a-110">[in] Die Größe in Bytes, der `pbPublicKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="2083a-110">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="2083a-111">[out] Entspricht dem Schlüssel Token mit starkem Namen übergeben `pbPublicKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="2083a-111">[out] The strong name token corresponding to the key passed in `pbPublicKeyBlob`.</span></span> <span data-ttu-id="2083a-112">Die common Language Runtime ordnet den Arbeitsspeicher, in dem das Token zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2083a-112">The common language runtime allocates the memory in which to return the token.</span></span> <span data-ttu-id="2083a-113">Der Aufrufer muss diesen Arbeitsspeicher freigeben, mithilfe der [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="2083a-113">The caller must free this memory by using the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="2083a-114">[out] Die Größe in Bytes, des Tokens zurückgegebenen starken Namen.</span><span class="sxs-lookup"><span data-stu-id="2083a-114">[out] The size, in bytes, of the returned strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2083a-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2083a-115">Return Value</span></span>  
 <span data-ttu-id="2083a-116">`true`Bei erfolgreichem Abschluss; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="2083a-116">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2083a-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2083a-117">Remarks</span></span>  
 <span data-ttu-id="2083a-118">Ein starker Name-Token ist die Kurzform eines öffentlichen Schlüssels verwendet, um Platz zu sparen, wenn wichtige Informationen in den Metadaten gespeichert.</span><span class="sxs-lookup"><span data-stu-id="2083a-118">A strong name token is the shortened form of a public key used to save space when storing key information in metadata.</span></span> <span data-ttu-id="2083a-119">Insbesondere sind starken Namenstoken in Assemblyverweise verwendet, um auf die abhängige Assembly zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="2083a-119">Specifically, strong name tokens are used in assembly references to refer to the dependent assembly.</span></span>  
  
 <span data-ttu-id="2083a-120">Wenn die `StrongNameTokenFromPublicKey` Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) Funktion, um den letzten generierten Fehler abzurufen.</span><span class="sxs-lookup"><span data-stu-id="2083a-120">If the `StrongNameTokenFromPublicKey` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2083a-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2083a-121">Requirements</span></span>  
 <span data-ttu-id="2083a-122">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2083a-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2083a-123">**Header:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="2083a-123">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="2083a-124">**Bibliothek:** als Ressource in mscoree.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="2083a-124">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="2083a-125">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2083a-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2083a-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2083a-126">See Also</span></span>  
 [<span data-ttu-id="2083a-127">StrongNameTokenFromPublicKey-Methode</span><span class="sxs-lookup"><span data-stu-id="2083a-127">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)  
 [<span data-ttu-id="2083a-128">StrongNameGetPublicKey-Methode</span><span class="sxs-lookup"><span data-stu-id="2083a-128">StrongNameGetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)  
 [<span data-ttu-id="2083a-129">PublicKeyBlob-Struktur</span><span class="sxs-lookup"><span data-stu-id="2083a-129">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
