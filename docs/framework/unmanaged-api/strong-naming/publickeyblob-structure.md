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
ms.openlocfilehash: 3b00bf8295a635871bd7263928ff21c97053cc39
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176954"
---
# <a name="publickeyblob-structure"></a><span data-ttu-id="f7949-102">PublicKeyBlob-Struktur</span><span class="sxs-lookup"><span data-stu-id="f7949-102">PublicKeyBlob Structure</span></span>
<span data-ttu-id="f7949-103">Stellt im Binärformat den öffentlichen Schlüssel eines öffentlichen/privaten Schlüsselpaars dar.</span><span class="sxs-lookup"><span data-stu-id="f7949-103">Represents, in binary format, the public key of a public/private key pair.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7949-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f7949-104">Syntax</span></span>  
  
```cpp  
typedef struct {  
    unsigned int SigAlgId;  
    unsigned int HashAlgId;  
    ULONG cbPublicKey;  
    BYTE PublicKey[1]  
} PublicKeyBlob;
```  
  
## <a name="members"></a><span data-ttu-id="f7949-105">Members</span><span class="sxs-lookup"><span data-stu-id="f7949-105">Members</span></span>  
  
|<span data-ttu-id="f7949-106">Member</span><span class="sxs-lookup"><span data-stu-id="f7949-106">Member</span></span>|<span data-ttu-id="f7949-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f7949-107">Description</span></span>|  
|------------|-----------------|  
|`SigAlgId`|<span data-ttu-id="f7949-108">Der Bezeichner für den `ALG_ID`Signaturalgorithmus (vom Typ , wie in WinCrypt.h definiert) des öffentlichen Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="f7949-108">The identifier for the signature algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`HashAlgId`|<span data-ttu-id="f7949-109">Der Bezeichner für den `ALG_ID`Hashalgorithmus (vom Typ , wie in WinCrypt.h definiert) des öffentlichen Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="f7949-109">The identifier for the hash algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`cbPublicKey`|<span data-ttu-id="f7949-110">Die Länge des Schlüssels in Bytes.</span><span class="sxs-lookup"><span data-stu-id="f7949-110">The length of the key in bytes.</span></span>|  
|`PublicKey`|<span data-ttu-id="f7949-111">Ein Bytearray variabler Länge, das den Schlüsselwert in dem von der CryptoAPI zurückgegebenen Format enthält.</span><span class="sxs-lookup"><span data-stu-id="f7949-111">A variable-length byte array that contains the key value in the format returned by the CryptoAPI.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f7949-112">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="f7949-112">Remarks</span></span>  
 <span data-ttu-id="f7949-113">Die `PublicKeyBlob` Struktur wird von [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md)und anderen Funktionen mit starkem Namen verwendet, um den öffentlichen Schlüssel eines öffentlichen/privaten Schlüsselpaars darzustellen.</span><span class="sxs-lookup"><span data-stu-id="f7949-113">The `PublicKeyBlob` structure is used by [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md), and other strong name functions to represent the public key of a public/private key pair.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7949-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f7949-114">Requirements</span></span>  
 <span data-ttu-id="f7949-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7949-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7949-116">**Kopfzeile:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="f7949-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="f7949-117">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f7949-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f7949-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7949-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7949-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f7949-119">See also</span></span>

- [<span data-ttu-id="f7949-120">StrongNameGetPublicKey-Funktion</span><span class="sxs-lookup"><span data-stu-id="f7949-120">StrongNameGetPublicKey Function</span></span>](strongnamegetpublickey-function.md)
- [<span data-ttu-id="f7949-121">StrongNameSignatureGeneration-Funktion</span><span class="sxs-lookup"><span data-stu-id="f7949-121">StrongNameSignatureGeneration Function</span></span>](strongnamesignaturegeneration-function.md)
