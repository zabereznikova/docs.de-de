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
ms.openlocfilehash: e66196e2bd2cb326ca3f5badc67bcf8d81e5fc3c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799165"
---
# <a name="publickeyblob-structure"></a><span data-ttu-id="5f05c-102">PublicKeyBlob-Struktur</span><span class="sxs-lookup"><span data-stu-id="5f05c-102">PublicKeyBlob Structure</span></span>
<span data-ttu-id="5f05c-103">Stellt den öffentlichen Schlüssel eines öffentlichen/privaten Schlüssel Paars im Binärformat dar.</span><span class="sxs-lookup"><span data-stu-id="5f05c-103">Represents, in binary format, the public key of a public/private key pair.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f05c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5f05c-104">Syntax</span></span>  
  
```cpp  
typedef struct {  
    unsigned int SigAlgId;  
    unsigned int HashAlgId;  
    ULONG cbPublicKey;  
    BYTE PublicKey[1]  
} PublicKeyBlob;   
```  
  
## <a name="members"></a><span data-ttu-id="5f05c-105">Member</span><span class="sxs-lookup"><span data-stu-id="5f05c-105">Members</span></span>  
  
|<span data-ttu-id="5f05c-106">Member</span><span class="sxs-lookup"><span data-stu-id="5f05c-106">Member</span></span>|<span data-ttu-id="5f05c-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5f05c-107">Description</span></span>|  
|------------|-----------------|  
|`SigAlgId`|<span data-ttu-id="5f05c-108">Der Bezeichner für den Signatur Algorithmus (vom `ALG_ID`Typ, wie in Wincrypt. h definiert) des öffentlichen Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="5f05c-108">The identifier for the signature algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`HashAlgId`|<span data-ttu-id="5f05c-109">Der Bezeichner für den Hash Algorithmus (vom `ALG_ID`Typ, wie in Wincrypt. h definiert) des öffentlichen Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="5f05c-109">The identifier for the hash algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`cbPublicKey`|<span data-ttu-id="5f05c-110">Die Länge des Schlüssels in Bytes.</span><span class="sxs-lookup"><span data-stu-id="5f05c-110">The length of the key in bytes.</span></span>|  
|`PublicKey`|<span data-ttu-id="5f05c-111">Ein Bytearray variabler Länge, das den Schlüsselwert in dem Format enthält, das von der CryptoAPI zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="5f05c-111">A variable-length byte array that contains the key value in the format returned by the CryptoAPI.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5f05c-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5f05c-112">Remarks</span></span>  
 <span data-ttu-id="5f05c-113">Die `PublicKeyBlob` Struktur wird von [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md)und anderen starken Namens Funktionen verwendet, um den öffentlichen Schlüssel eines öffentlichen/privaten Schlüssel Paars darzustellen.</span><span class="sxs-lookup"><span data-stu-id="5f05c-113">The `PublicKeyBlob` structure is used by [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md), and other strong name functions to represent the public key of a public/private key pair.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f05c-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5f05c-114">Requirements</span></span>  
 <span data-ttu-id="5f05c-115">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f05c-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f05c-116">**Header:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="5f05c-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="5f05c-117">**Fern** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="5f05c-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5f05c-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f05c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f05c-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5f05c-119">See also</span></span>

- [<span data-ttu-id="5f05c-120">StrongNameGetPublicKey-Funktion</span><span class="sxs-lookup"><span data-stu-id="5f05c-120">StrongNameGetPublicKey Function</span></span>](strongnamegetpublickey-function.md)
- [<span data-ttu-id="5f05c-121">StrongNameSignatureGeneration-Funktion</span><span class="sxs-lookup"><span data-stu-id="5f05c-121">StrongNameSignatureGeneration Function</span></span>](strongnamesignaturegeneration-function.md)
