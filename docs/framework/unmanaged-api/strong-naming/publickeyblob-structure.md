---
title: PublicKeyBlob-Struktur
ms.date: 03/30/2017
api_name:
- PublicKeyBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- PublicKeyBlob
helpviewer_keywords:
- PublicKeyBlob structure [.NET Framework strong naming]
ms.assetid: b9240712-829c-4c8d-9a09-a6e7aa63f63a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d7577a24a023c38370f5ac1f8c471ce31409e75d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33459338"
---
# <a name="publickeyblob-structure"></a><span data-ttu-id="1bd6c-102">PublicKeyBlob-Struktur</span><span class="sxs-lookup"><span data-stu-id="1bd6c-102">PublicKeyBlob Structure</span></span>
<span data-ttu-id="1bd6c-103">Stellt den öffentlichen Schlüssel eines öffentlichen/privaten Schlüsselpaars im binären Format dar.</span><span class="sxs-lookup"><span data-stu-id="1bd6c-103">Represents, in binary format, the public key of a public/private key pair.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bd6c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1bd6c-104">Syntax</span></span>  
  
```  
typedef struct {  
    unsigned int SigAlgId;  
    unsigned int HashAlgId;  
    ULONG cbPublicKey;  
    BYTE PublicKey[1]  
} PublicKeyBlob;   
```  
  
## <a name="members"></a><span data-ttu-id="1bd6c-105">Member</span><span class="sxs-lookup"><span data-stu-id="1bd6c-105">Members</span></span>  
  
|<span data-ttu-id="1bd6c-106">Member</span><span class="sxs-lookup"><span data-stu-id="1bd6c-106">Member</span></span>|<span data-ttu-id="1bd6c-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1bd6c-107">Description</span></span>|  
|------------|-----------------|  
|`SigAlgId`|<span data-ttu-id="1bd6c-108">Der Bezeichner für den Signaturalgorithmus (vom Typ `ALG_ID`, wie in WinCrypt.h definiert) des öffentlichen Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="1bd6c-108">The identifier for the signature algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`HashAlgId`|<span data-ttu-id="1bd6c-109">Der Bezeichner für die Hash-Algorithmus (des Typs `ALG_ID`, wie in WinCrypt.h definiert) des öffentlichen Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="1bd6c-109">The identifier for the hash algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`cbPublicKey`|<span data-ttu-id="1bd6c-110">Die Länge des Schlüssels in Bytes.</span><span class="sxs-lookup"><span data-stu-id="1bd6c-110">The length of the key in bytes.</span></span>|  
|`PublicKey`|<span data-ttu-id="1bd6c-111">Ein variabler Länge Bytearray, das den Schlüsselwert in der von der Crypto-API zurückgegebenen Format enthält.</span><span class="sxs-lookup"><span data-stu-id="1bd6c-111">A variable-length byte array that contains the key value in the format returned by the CryptoAPI.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1bd6c-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1bd6c-112">Remarks</span></span>  
 <span data-ttu-id="1bd6c-113">Die `PublicKeyBlob` Struktur dient der [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md), und anderen Funktionen zur Darstellung des öffentlichen Schlüssels des ein öffentliches/privates Schlüsselpaar mit starkem Namen.</span><span class="sxs-lookup"><span data-stu-id="1bd6c-113">The `PublicKeyBlob` structure is used by [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md), and other strong name functions to represent the public key of a public/private key pair.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1bd6c-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1bd6c-114">Requirements</span></span>  
 <span data-ttu-id="1bd6c-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1bd6c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1bd6c-116">**Header:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="1bd6c-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="1bd6c-117">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="1bd6c-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1bd6c-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1bd6c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bd6c-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1bd6c-119">See Also</span></span>  
 [<span data-ttu-id="1bd6c-120">StrongNameGetPublicKey-Funktion</span><span class="sxs-lookup"><span data-stu-id="1bd6c-120">StrongNameGetPublicKey Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md)  
 [<span data-ttu-id="1bd6c-121">StrongNameSignatureGeneration-Funktion</span><span class="sxs-lookup"><span data-stu-id="1bd6c-121">StrongNameSignatureGeneration Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)  
 [<span data-ttu-id="1bd6c-122">Strukturen für starke Namen</span><span class="sxs-lookup"><span data-stu-id="1bd6c-122">Strong Naming Structures</span></span>](http://msdn.microsoft.com/library/4b041a2f-fd12-4b91-aacd-bc3b34a5124d)
