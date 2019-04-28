---
title: ICLRStrongName2-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRStrongName2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName2
helpviewer_keywords:
- ICLRStrongName2 interface [.NET Framework hosting]
ms.assetid: 9f098a74-201e-4628-a468-8dee9ab99b4a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6bf9e3d2df8f507e118b393007c3958358a830cc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763723"
---
# <a name="iclrstrongname2-interface"></a><span data-ttu-id="d1fb0-102">ICLRStrongName2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d1fb0-102">ICLRStrongName2 Interface</span></span>
<span data-ttu-id="d1fb0-103">Bietet die Möglichkeit zum Erstellen von starken Namen unter Verwendung der SHA-2-Gruppe der Hashalgorithmen (SHA-256, SHA-384 und SHA-512) sichern.</span><span class="sxs-lookup"><span data-stu-id="d1fb0-103">Provides the ability to create strong names using the SHA-2 group of Secure Hash Algorithms (SHA-256, SHA-384, and SHA-512).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d1fb0-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="d1fb0-104">Methods</span></span>  
  
|<span data-ttu-id="d1fb0-105">Methode</span><span class="sxs-lookup"><span data-stu-id="d1fb0-105">Method</span></span>|<span data-ttu-id="d1fb0-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d1fb0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d1fb0-107">StrongNameGetPublicKeyEx-Methode</span><span class="sxs-lookup"><span data-stu-id="d1fb0-107">StrongNameGetPublicKeyEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/strongnamegetpublickeyex-method.md)|<span data-ttu-id="d1fb0-108">Ruft den öffentlichen Schlüssel aus einem öffentlichen/privaten Schlüsselpaar und ein Hash-Algorithmus und eines Signaturalgorithmus angibt.</span><span class="sxs-lookup"><span data-stu-id="d1fb0-108">Gets the public key from a public/private key pair, and specifies a hash algorithm and a signature algorithm.</span></span>|  
|[<span data-ttu-id="d1fb0-109">StrongNameSignatureVerificationEx2-Method</span><span class="sxs-lookup"><span data-stu-id="d1fb0-109">StrongNameSignatureVerificationEx2 Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/strongnamesignatureverificationex2-method.md)|<span data-ttu-id="d1fb0-110">Überprüft die Signatur einer Assembly mit starkem Namen, und stellt eine Zuordnung zwischen den ECMA-Schlüssel zu einem echten Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="d1fb0-110">Verifies the signature of a strongly named assembly, and provides a mapping from the ECMA key to a real key.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d1fb0-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d1fb0-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1fb0-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d1fb0-112">Requirements</span></span>  
 <span data-ttu-id="d1fb0-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d1fb0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1fb0-114">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="d1fb0-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="d1fb0-115">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d1fb0-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d1fb0-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1fb0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>
