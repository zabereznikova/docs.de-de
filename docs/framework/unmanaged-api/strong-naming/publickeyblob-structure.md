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
ms.openlocfilehash: 42cd3cc22fbbb8eb3d5ac44544fce36650b6461f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705929"
---
# <a name="publickeyblob-structure"></a><span data-ttu-id="76d78-102">PublicKeyBlob-Struktur</span><span class="sxs-lookup"><span data-stu-id="76d78-102">PublicKeyBlob Structure</span></span>

<span data-ttu-id="76d78-103">Stellt den öffentlichen Schlüssel eines öffentlichen/privaten Schlüssel Paars im Binärformat dar.</span><span class="sxs-lookup"><span data-stu-id="76d78-103">Represents, in binary format, the public key of a public/private key pair.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76d78-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="76d78-104">Syntax</span></span>  
  
```cpp  
typedef struct {  
    unsigned int SigAlgId;  
    unsigned int HashAlgId;  
    ULONG cbPublicKey;  
    BYTE PublicKey[1]  
} PublicKeyBlob;
```  
  
## <a name="members"></a><span data-ttu-id="76d78-105">Member</span><span class="sxs-lookup"><span data-stu-id="76d78-105">Members</span></span>  
  
|<span data-ttu-id="76d78-106">Member</span><span class="sxs-lookup"><span data-stu-id="76d78-106">Member</span></span>|<span data-ttu-id="76d78-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="76d78-107">Description</span></span>|  
|------------|-----------------|  
|`SigAlgId`|<span data-ttu-id="76d78-108">Der Bezeichner für den Signatur Algorithmus (vom Typ `ALG_ID` , wie in Wincrypt. h definiert) des öffentlichen Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="76d78-108">The identifier for the signature algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`HashAlgId`|<span data-ttu-id="76d78-109">Der Bezeichner für den Hash Algorithmus (vom Typ `ALG_ID` , wie in Wincrypt. h definiert) des öffentlichen Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="76d78-109">The identifier for the hash algorithm (of type `ALG_ID`, as defined in WinCrypt.h) of the public key.</span></span>|  
|`cbPublicKey`|<span data-ttu-id="76d78-110">Die Länge des Schlüssels in Bytes.</span><span class="sxs-lookup"><span data-stu-id="76d78-110">The length of the key in bytes.</span></span>|  
|`PublicKey`|<span data-ttu-id="76d78-111">Ein Bytearray variabler Länge, das den Schlüsselwert in dem Format enthält, das von der CryptoAPI zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="76d78-111">A variable-length byte array that contains the key value in the format returned by the CryptoAPI.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="76d78-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="76d78-112">Remarks</span></span>  

 <span data-ttu-id="76d78-113">Die `PublicKeyBlob` Struktur wird von [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md)und anderen starken Namens Funktionen verwendet, um den öffentlichen Schlüssel eines öffentlichen/privaten Schlüssel Paars darzustellen.</span><span class="sxs-lookup"><span data-stu-id="76d78-113">The `PublicKeyBlob` structure is used by [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md), and other strong name functions to represent the public key of a public/private key pair.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76d78-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="76d78-114">Requirements</span></span>  

 <span data-ttu-id="76d78-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="76d78-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76d78-116">**Header:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="76d78-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="76d78-117">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="76d78-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="76d78-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76d78-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76d78-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="76d78-119">See also</span></span>

- [<span data-ttu-id="76d78-120">StrongNameGetPublicKey-Funktion</span><span class="sxs-lookup"><span data-stu-id="76d78-120">StrongNameGetPublicKey Function</span></span>](strongnamegetpublickey-function.md)
- [<span data-ttu-id="76d78-121">StrongNameSignatureGeneration-Funktion</span><span class="sxs-lookup"><span data-stu-id="76d78-121">StrongNameSignatureGeneration Function</span></span>](strongnamesignaturegeneration-function.md)
