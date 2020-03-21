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
ms.openlocfilehash: 919c1321f18ca163481d27fa204c78f38af1e456
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176317"
---
# <a name="iclrstrongnamestrongnametokenfrompublickey-method"></a><span data-ttu-id="66820-102">ICLRStrongName::StrongNameTokenFromPublicKey-Methode</span><span class="sxs-lookup"><span data-stu-id="66820-102">ICLRStrongName::StrongNameTokenFromPublicKey Method</span></span>
<span data-ttu-id="66820-103">Ruft ein Token ab, das einen öffentlichen Schlüssel darstellt.</span><span class="sxs-lookup"><span data-stu-id="66820-103">Gets a token that represents a public key.</span></span> <span data-ttu-id="66820-104">Ein Token mit starkem Namen ist die verkürzte Form eines öffentlichen Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="66820-104">A strong name token is the shortened form of a public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66820-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="66820-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameTokenFromPublicKey (
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="66820-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="66820-106">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="66820-107">[in] Eine Struktur vom Typ [PublicKeyBlob,](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) die den öffentlichen Teil des Schlüsselpaars enthält, der zum Generieren der Signatur mit starkem Namen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="66820-107">[in] A structure of type [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="66820-108">[in] Die Größe von in `pbPublicKeyBlob`Bytes von .</span><span class="sxs-lookup"><span data-stu-id="66820-108">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="66820-109">[out] Das Token mit starkem Namen, das dem in `pbPublicKeyBlob`übergebenen Schlüssel entspricht.</span><span class="sxs-lookup"><span data-stu-id="66820-109">[out] The strong name token corresponding to the key passed in `pbPublicKeyBlob`.</span></span> <span data-ttu-id="66820-110">Die Common Language Runtime weist den Speicher zu, in dem das Token zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="66820-110">The common language runtime allocates the memory in which to return the token.</span></span> <span data-ttu-id="66820-111">Der Aufrufer muss diesen Speicher mithilfe der [ICLRStrongName::StrongNameFreeBuffer-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) freizugeben.</span><span class="sxs-lookup"><span data-stu-id="66820-111">The caller must free this memory by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="66820-112">[out] Die Größe des zurückgegebenen Tokens für starken Namen in Bytes.</span><span class="sxs-lookup"><span data-stu-id="66820-112">[out] The size, in bytes, of the returned strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="66820-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="66820-113">Return Value</span></span>  
 <span data-ttu-id="66820-114">`S_OK`wenn die Methode erfolgreich abgeschlossen wurde; Andernfalls ein HRESULT-Wert, der auf einen Fehler hinweist (siehe [Allgemeine HRESULT-Werte](/windows/win32/seccrypto/common-hresult-values) für eine Liste).</span><span class="sxs-lookup"><span data-stu-id="66820-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="66820-115">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="66820-115">Remarks</span></span>  
 <span data-ttu-id="66820-116">Ein Token mit starkem Namen ist die verkürzte Form eines öffentlichen Schlüssels, der zum Speichern von Schlüsselinformationen in Metadaten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="66820-116">A strong name token is the shortened form of a public key that is used to save space when storing key information in metadata.</span></span> <span data-ttu-id="66820-117">Insbesondere werden Token mit starkem Namen in Assemblyverweisen verwendet, um auf die abhängige Assembly zu verweisen.</span><span class="sxs-lookup"><span data-stu-id="66820-117">Specifically, strong name tokens are used in assembly references to refer to the dependent assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66820-118">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="66820-118">Requirements</span></span>  
 <span data-ttu-id="66820-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66820-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66820-120">**Kopfzeile:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="66820-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="66820-121">**Bibliothek:** Als Ressource in mscoree.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="66820-121">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="66820-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66820-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66820-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="66820-123">See also</span></span>

- [<span data-ttu-id="66820-124">StrongNameGetPublicKey-Methode</span><span class="sxs-lookup"><span data-stu-id="66820-124">StrongNameGetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="66820-125">PublicKeyBlob-Struktur</span><span class="sxs-lookup"><span data-stu-id="66820-125">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
- [<span data-ttu-id="66820-126">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="66820-126">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
