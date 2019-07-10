---
title: StrongNameTokenFromPublicKey-Funktion
ms.date: 03/30/2017
api_name:
- StrongNameTokenFromPublicKey
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- COM
f1_keywords:
- StrongNameTokenFromPublicKey
helpviewer_keywords:
- StrongNameTokenFromPublicKey function [.NET Framework strong naming]
ms.assetid: 997e9e57-abb2-4217-bf20-1df621a75add
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 68be16c559431de871dc9ddb1963897b0927d49a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67783167"
---
# <a name="strongnametokenfrompublickey-function"></a><span data-ttu-id="d2ae4-102">StrongNameTokenFromPublicKey-Funktion</span><span class="sxs-lookup"><span data-stu-id="d2ae4-102">StrongNameTokenFromPublicKey Function</span></span>
<span data-ttu-id="d2ae4-103">Ruft ein Token ab, das einen öffentlichen Schlüssel darstellt.</span><span class="sxs-lookup"><span data-stu-id="d2ae4-103">Gets a token representing a public key.</span></span> <span data-ttu-id="d2ae4-104">Ein starker Name-Token ist die Kurzform für einen öffentlichen Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="d2ae4-104">A strong name token is the shortened form of a public key.</span></span>  
  
 <span data-ttu-id="d2ae4-105">Diese Funktion wurde als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="d2ae4-105">This function has been deprecated.</span></span> <span data-ttu-id="d2ae4-106">Verwenden der [ICLRStrongName:: StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="d2ae4-106">Use the [ICLRStrongName::StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2ae4-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="d2ae4-107">Syntax</span></span>  
  
```cpp  
BOOLEANStrongNameTokenFromPublicKey (   
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2ae4-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="d2ae4-108">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="d2ae4-109">[in] Eine Struktur des Typs [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) , enthält den öffentlichen Teil des Schlüsselpaars verwendet, um die Signatur mit starkem Namen generieren.</span><span class="sxs-lookup"><span data-stu-id="d2ae4-109">[in] A structure of type [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="d2ae4-110">[in] Die Größe in Bytes, des `pbPublicKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="d2ae4-110">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="d2ae4-111">[out] Entspricht dem Schlüssel Token mit starkem Namen übergegebenen `pbPublicKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="d2ae4-111">[out] The strong name token corresponding to the key passed in `pbPublicKeyBlob`.</span></span> <span data-ttu-id="d2ae4-112">Die common Language Runtime ordnet den Speicher in den das Token zurückgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d2ae4-112">The common language runtime allocates the memory in which to return the token.</span></span> <span data-ttu-id="d2ae4-113">Der Aufrufer muss diesen Arbeitsspeicher freigeben, mithilfe der [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="d2ae4-113">The caller must free this memory by using the [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) function.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="d2ae4-114">[out] Die Größe in Bytes, der das zurückgegebene strong Name-Token.</span><span class="sxs-lookup"><span data-stu-id="d2ae4-114">[out] The size, in bytes, of the returned strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d2ae4-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d2ae4-115">Return Value</span></span>  
 <span data-ttu-id="d2ae4-116">`true` Bei erfolgreichem Abschluss; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="d2ae4-116">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d2ae4-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d2ae4-117">Remarks</span></span>  
 <span data-ttu-id="d2ae4-118">Ein starker Name-Token ist die Kurzform für einen öffentlichen Schlüssel verwendet, um Platz zu sparen, wenn wichtige Informationen in den Metadaten gespeichert.</span><span class="sxs-lookup"><span data-stu-id="d2ae4-118">A strong name token is the shortened form of a public key used to save space when storing key information in metadata.</span></span> <span data-ttu-id="d2ae4-119">Insbesondere werden Token mit starkem Namen in Assemblyverweise verwendet, um auf die abhängige Assembly zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="d2ae4-119">Specifically, strong name tokens are used in assembly references to refer to the dependent assembly.</span></span>  
  
 <span data-ttu-id="d2ae4-120">Wenn die `StrongNameTokenFromPublicKey` Funktion nicht erfolgreich abgeschlossen wurde, rufen Sie die [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) Funktion, um den letzten generierten Fehler abzurufen.</span><span class="sxs-lookup"><span data-stu-id="d2ae4-120">If the `StrongNameTokenFromPublicKey` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2ae4-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d2ae4-121">Requirements</span></span>  
 <span data-ttu-id="d2ae4-122">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2ae4-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2ae4-123">**Header:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="d2ae4-123">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="d2ae4-124">**Bibliothek:** Als Ressource in mscoree.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d2ae4-124">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="d2ae4-125">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2ae4-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2ae4-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d2ae4-126">See also</span></span>

- [<span data-ttu-id="d2ae4-127">StrongNameTokenFromPublicKey-Methode</span><span class="sxs-lookup"><span data-stu-id="d2ae4-127">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="d2ae4-128">StrongNameGetPublicKey-Methode</span><span class="sxs-lookup"><span data-stu-id="d2ae4-128">StrongNameGetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="d2ae4-129">PublicKeyBlob-Struktur</span><span class="sxs-lookup"><span data-stu-id="d2ae4-129">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
