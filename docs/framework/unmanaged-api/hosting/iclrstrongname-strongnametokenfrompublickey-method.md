---
title: ICLRStrongName::StrongNameTokenFromPublicKey-Methode
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameTokenFromPublicKey
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameTokenFromPublicKey
helpviewer_keywords:
- ICLRStrongName::StrongNameTokenFromPublicKey method [.NET Framework hosting]
- StrongNameTokenFromPublicKey method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 7962ce88-7e86-4a6f-8298-621b01ffc3c2
topic_type:
- apiref
ms.openlocfilehash: c727d4524bc40ab90eee90faf16788140a73ad9a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677660"
---
# <a name="iclrstrongnamestrongnametokenfrompublickey-method"></a><span data-ttu-id="3c915-102">ICLRStrongName::StrongNameTokenFromPublicKey-Methode</span><span class="sxs-lookup"><span data-stu-id="3c915-102">ICLRStrongName::StrongNameTokenFromPublicKey Method</span></span>

<span data-ttu-id="3c915-103">Ruft ein Token ab, das einen öffentlichen Schlüssel darstellt.</span><span class="sxs-lookup"><span data-stu-id="3c915-103">Gets a token that represents a public key.</span></span> <span data-ttu-id="3c915-104">Ein Token mit starkem Namen ist die verkürzte Form eines öffentlichen Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="3c915-104">A strong name token is the shortened form of a public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c915-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="3c915-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameTokenFromPublicKey (
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3c915-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="3c915-106">Parameters</span></span>  

 `pbPublicKeyBlob`  
 <span data-ttu-id="3c915-107">in Eine Struktur vom Typ [PublicKeyBlob](../strong-naming/publickeyblob-structure.md) , die den öffentlichen Teil des Schlüssel Paars enthält, das zum Generieren der starken Namens Signatur verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3c915-107">[in] A structure of type [PublicKeyBlob](../strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="3c915-108">in Die Größe von in Bytes `pbPublicKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="3c915-108">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="3c915-109">vorgenommen Das Token für den starken Namen, das dem übergebenen Schlüssel entspricht `pbPublicKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="3c915-109">[out] The strong name token corresponding to the key passed in `pbPublicKeyBlob`.</span></span> <span data-ttu-id="3c915-110">Der Common Language Runtime ordnet den Speicher zu, in den das Token zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="3c915-110">The common language runtime allocates the memory in which to return the token.</span></span> <span data-ttu-id="3c915-111">Der Aufrufer muss diesen Arbeitsspeicher mithilfe der [ICLRStrongName:: StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) -Methode freigeben.</span><span class="sxs-lookup"><span data-stu-id="3c915-111">The caller must free this memory by using the [ICLRStrongName::StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="3c915-112">vorgenommen Die Größe (in Bytes) des zurückgegebenen Token für den starken Namen.</span><span class="sxs-lookup"><span data-stu-id="3c915-112">[out] The size, in bytes, of the returned strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3c915-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3c915-113">Return Value</span></span>  

 <span data-ttu-id="3c915-114">`S_OK` , wenn die Methode erfolgreich abgeschlossen wurde. andernfalls ein HRESULT-Wert, der einen Fehler angibt (siehe [Allgemeine HRESULT-Werte](/windows/win32/seccrypto/common-hresult-values) für eine Liste).</span><span class="sxs-lookup"><span data-stu-id="3c915-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3c915-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3c915-115">Remarks</span></span>  

 <span data-ttu-id="3c915-116">Ein Token mit starkem Namen ist die verkürzte Form eines öffentlichen Schlüssels, mit dem Speicherplatz beim Speichern von Schlüsselinformationen in Metadaten eingespart wird.</span><span class="sxs-lookup"><span data-stu-id="3c915-116">A strong name token is the shortened form of a public key that is used to save space when storing key information in metadata.</span></span> <span data-ttu-id="3c915-117">Insbesondere werden starke namens Token in Assemblyverweisen verwendet, um auf die abhängige Assembly zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="3c915-117">Specifically, strong name tokens are used in assembly references to refer to the dependent assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c915-118">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="3c915-118">Requirements</span></span>  

 <span data-ttu-id="3c915-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c915-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c915-120">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="3c915-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="3c915-121">**Bibliothek:** Als Ressource in mscoree.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="3c915-121">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="3c915-122">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c915-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c915-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3c915-123">See also</span></span>

- [<span data-ttu-id="3c915-124">StrongNameGetPublicKey-Methode</span><span class="sxs-lookup"><span data-stu-id="3c915-124">StrongNameGetPublicKey Method</span></span>](iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="3c915-125">PublicKeyBlob-Struktur</span><span class="sxs-lookup"><span data-stu-id="3c915-125">PublicKeyBlob Structure</span></span>](../strong-naming/publickeyblob-structure.md)
- [<span data-ttu-id="3c915-126">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3c915-126">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
