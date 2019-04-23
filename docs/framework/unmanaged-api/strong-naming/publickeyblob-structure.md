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
ms.openlocfilehash: 1a361e04b6f8f39ec0083471d8cb47d5a29376c5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59214818"
---
# <a name="publickeyblob-structure"></a><span data-ttu-id="490a6-102">PublicKeyBlob-Struktur</span><span class="sxs-lookup"><span data-stu-id="490a6-102">PublicKeyBlob Structure</span></span>
<span data-ttu-id="490a6-103">Stellt den öffentlichen Schlüssel eines öffentlichen/privaten Schlüsselpaars im binären Format dar.</span><span class="sxs-lookup"><span data-stu-id="490a6-103">Represents, in binary format, the public key of a public/private key pair.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="490a6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="490a6-104">Syntax</span></span>  
  
```  
typedef struct {  
    unsigned int SigAlgId;  
    unsigned int HashAlgId;  
    ULONG cbPublicKey;  
    BYTE PublicKey[1]  
} PublicKeyBlob;   
```  
  
## <a name="members"></a><span data-ttu-id="490a6-105">Member</span><span class="sxs-lookup"><span data-stu-id="490a6-105">Members</span></span>  
  
|<span data-ttu-id="490a6-106">Member</span><span class="sxs-lookup"><span data-stu-id="490a6-106">Member</span></span>|<span data-ttu-id="490a6-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="490a6-107">Description</span></span>|  
|------------|-----------------|  
|`SigAlgId`|<span data-ttu-id="490a6-108">Der Bezeichner für den Signaturalgorithmus (des Typs `ALG_ID`gemäß WinCrypt.h) des öffentlichen Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="490a6-108">The identifier for the signature algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`HashAlgId`|<span data-ttu-id="490a6-109">Der Bezeichner für den Hashalgorithmus (des Typs `ALG_ID`gemäß WinCrypt.h) des öffentlichen Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="490a6-109">The identifier for the hash algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`cbPublicKey`|<span data-ttu-id="490a6-110">Die Länge des Schlüssels in Bytes.</span><span class="sxs-lookup"><span data-stu-id="490a6-110">The length of the key in bytes.</span></span>|  
|`PublicKey`|<span data-ttu-id="490a6-111">Ein variabler Länge Bytearray, das den Schlüsselwert in der von der CryptoAPI zurückgegebenen Format enthält.</span><span class="sxs-lookup"><span data-stu-id="490a6-111">A variable-length byte array that contains the key value in the format returned by the CryptoAPI.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="490a6-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="490a6-112">Remarks</span></span>  
 <span data-ttu-id="490a6-113">Die `PublicKeyBlob` Struktur dient der [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md), und andere Funktionen zur Darstellung des öffentlichen Schlüssels eines öffentlichen/privaten Schlüsselpaars mit starkem Namen.</span><span class="sxs-lookup"><span data-stu-id="490a6-113">The `PublicKeyBlob` structure is used by [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md), and other strong name functions to represent the public key of a public/private key pair.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="490a6-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="490a6-114">Requirements</span></span>  
 <span data-ttu-id="490a6-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="490a6-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="490a6-116">**Header:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="490a6-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="490a6-117">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="490a6-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="490a6-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="490a6-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="490a6-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="490a6-119">See also</span></span>

- [<span data-ttu-id="490a6-120">StrongNameGetPublicKey-Funktion</span><span class="sxs-lookup"><span data-stu-id="490a6-120">StrongNameGetPublicKey Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md)
- [<span data-ttu-id="490a6-121">StrongNameSignatureGeneration-Funktion</span><span class="sxs-lookup"><span data-stu-id="490a6-121">StrongNameSignatureGeneration Function</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)
