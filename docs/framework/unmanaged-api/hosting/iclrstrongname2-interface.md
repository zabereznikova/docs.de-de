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
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33432972"
---
# <a name="iclrstrongname2-interface"></a><span data-ttu-id="fa2e5-102">ICLRStrongName2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fa2e5-102">ICLRStrongName2 Interface</span></span>
<span data-ttu-id="fa2e5-103">Bietet die Möglichkeit zum Erstellen von starken Namen unter Verwendung der SHA-2-Gruppe des Secure Hash-Algorithmus (SHA-256, SHA-384 und SHA-512).</span><span class="sxs-lookup"><span data-stu-id="fa2e5-103">Provides the ability to create strong names using the SHA-2 group of Secure Hash Algorithms (SHA-256, SHA-384, and SHA-512).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fa2e5-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="fa2e5-104">Methods</span></span>  
  
|<span data-ttu-id="fa2e5-105">Methode</span><span class="sxs-lookup"><span data-stu-id="fa2e5-105">Method</span></span>|<span data-ttu-id="fa2e5-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fa2e5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fa2e5-107">StrongNameGetPublicKeyEx-Methode</span><span class="sxs-lookup"><span data-stu-id="fa2e5-107">StrongNameGetPublicKeyEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/strongnamegetpublickeyex-method.md)|<span data-ttu-id="fa2e5-108">Ruft den öffentlichen Schlüssel aus einem öffentlichen/privaten Schlüsselpaar und gibt einen Hashalgorithmus und eines Signaturalgorithmus.</span><span class="sxs-lookup"><span data-stu-id="fa2e5-108">Gets the public key from a public/private key pair, and specifies a hash algorithm and a signature algorithm.</span></span>|  
|[<span data-ttu-id="fa2e5-109">StrongNameSignatureVerificationEx2-Method</span><span class="sxs-lookup"><span data-stu-id="fa2e5-109">StrongNameSignatureVerificationEx2 Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/strongnamesignatureverificationex2-method.md)|<span data-ttu-id="fa2e5-110">Überprüft die Signatur einer Assembly mit starkem Namen, und stellt eine Zuordnung aus dem ECMA-Schlüssel, um eine tatsächliche Taste bereit.</span><span class="sxs-lookup"><span data-stu-id="fa2e5-110">Verifies the signature of a strongly named assembly, and provides a mapping from the ECMA key to a real key.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa2e5-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fa2e5-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa2e5-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fa2e5-112">Requirements</span></span>  
 <span data-ttu-id="fa2e5-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa2e5-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa2e5-114">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="fa2e5-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="fa2e5-115">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="fa2e5-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fa2e5-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa2e5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>
