---
title: PublicKeyBlob-Struktur
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: PublicKeyBlob
api_location: mscoree.dll
api_type: COM
f1_keywords: PublicKeyBlob
helpviewer_keywords: PublicKeyBlob structure [.NET Framework strong naming]
ms.assetid: b9240712-829c-4c8d-9a09-a6e7aa63f63a
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6b70ab9ee04ff2a060f3c66173a3628032afc0b6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="publickeyblob-structure"></a><span data-ttu-id="4ba1a-102">PublicKeyBlob-Struktur</span><span class="sxs-lookup"><span data-stu-id="4ba1a-102">PublicKeyBlob Structure</span></span>
<span data-ttu-id="4ba1a-103">Stellt den öffentlichen Schlüssel eines öffentlichen/privaten Schlüsselpaars im binären Format dar.</span><span class="sxs-lookup"><span data-stu-id="4ba1a-103">Represents, in binary format, the public key of a public/private key pair.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ba1a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4ba1a-104">Syntax</span></span>  
  
```  
typedef struct {  
    unsigned int SigAlgId;  
    unsigned int HashAlgId;  
    ULONG cbPublicKey;  
    BYTE PublicKey[1]  
} PublicKeyBlob;   
```  
  
## <a name="members"></a><span data-ttu-id="4ba1a-105">Member</span><span class="sxs-lookup"><span data-stu-id="4ba1a-105">Members</span></span>  
  
|<span data-ttu-id="4ba1a-106">Member</span><span class="sxs-lookup"><span data-stu-id="4ba1a-106">Member</span></span>|<span data-ttu-id="4ba1a-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4ba1a-107">Description</span></span>|  
|------------|-----------------|  
|`SigAlgId`|<span data-ttu-id="4ba1a-108">Der Bezeichner für den Signaturalgorithmus (vom Typ `ALG_ID`, wie in WinCrypt.h definiert) des öffentlichen Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="4ba1a-108">The identifier for the signature algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`HashAlgId`|<span data-ttu-id="4ba1a-109">Der Bezeichner für die Hash-Algorithmus (des Typs `ALG_ID`, wie in WinCrypt.h definiert) des öffentlichen Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="4ba1a-109">The identifier for the hash algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`cbPublicKey`|<span data-ttu-id="4ba1a-110">Die Länge des Schlüssels in Bytes.</span><span class="sxs-lookup"><span data-stu-id="4ba1a-110">The length of the key in bytes.</span></span>|  
|`PublicKey`|<span data-ttu-id="4ba1a-111">Ein variabler Länge Bytearray, das den Schlüsselwert in der von der Crypto-API zurückgegebenen Format enthält.</span><span class="sxs-lookup"><span data-stu-id="4ba1a-111">A variable-length byte array that contains the key value in the format returned by the CryptoAPI.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4ba1a-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4ba1a-112">Remarks</span></span>  
 <span data-ttu-id="4ba1a-113">Die `PublicKeyBlob` Struktur dient der [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md), und anderen Funktionen zur Darstellung des öffentlichen Schlüssels des ein öffentliches/privates Schlüsselpaar mit starkem Namen.</span><span class="sxs-lookup"><span data-stu-id="4ba1a-113">The `PublicKeyBlob` structure is used by [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md), and other strong name functions to represent the public key of a public/private key pair.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ba1a-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4ba1a-114">Requirements</span></span>  
 <span data-ttu-id="4ba1a-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ba1a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ba1a-116">**Header:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="4ba1a-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="4ba1a-117">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="4ba1a-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4ba1a-118">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ba1a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ba1a-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4ba1a-119">See Also</span></span>  
 [<span data-ttu-id="4ba1a-120">StrongNameGetPublicKey-Funktion</span><span class="sxs-lookup"><span data-stu-id="4ba1a-120">StrongNameGetPublicKey Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md)  
 [<span data-ttu-id="4ba1a-121">StrongNameSignatureGeneration-Funktion</span><span class="sxs-lookup"><span data-stu-id="4ba1a-121">StrongNameSignatureGeneration Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)  
 [<span data-ttu-id="4ba1a-122">Strukturen für starke Namen</span><span class="sxs-lookup"><span data-stu-id="4ba1a-122">Strong Naming Structures</span></span>](http://msdn.microsoft.com/en-us/4b041a2f-fd12-4b91-aacd-bc3b34a5124d)
