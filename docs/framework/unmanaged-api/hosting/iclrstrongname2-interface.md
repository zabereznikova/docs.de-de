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
ms.openlocfilehash: bc871c29f53a9ea4451a0fc1c747939724b0da87
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73092242"
---
# <a name="iclrstrongname2-interface"></a><span data-ttu-id="52e3c-102">ICLRStrongName2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="52e3c-102">ICLRStrongName2 Interface</span></span>
<span data-ttu-id="52e3c-103">Bietet die Möglichkeit, starke Namen mithilfe der SHA-2-Gruppe von sicheren Hash Algorithmen (SHA-256, SHA-384 und SHA-512) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="52e3c-103">Provides the ability to create strong names using the SHA-2 group of Secure Hash Algorithms (SHA-256, SHA-384, and SHA-512).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="52e3c-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="52e3c-104">Methods</span></span>  
  
|<span data-ttu-id="52e3c-105">Methode</span><span class="sxs-lookup"><span data-stu-id="52e3c-105">Method</span></span>|<span data-ttu-id="52e3c-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="52e3c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="52e3c-107">StrongNameGetPublicKeyEx-Methode</span><span class="sxs-lookup"><span data-stu-id="52e3c-107">StrongNameGetPublicKeyEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/strongnamegetpublickeyex-method.md)|<span data-ttu-id="52e3c-108">Ruft den öffentlichen Schlüssel aus einem Paar aus öffentlichem und privatem Schlüssel ab und gibt einen Hash Algorithmus und einen Signatur Algorithmus an.</span><span class="sxs-lookup"><span data-stu-id="52e3c-108">Gets the public key from a public/private key pair, and specifies a hash algorithm and a signature algorithm.</span></span>|  
|[<span data-ttu-id="52e3c-109">StrongNameSignatureVerificationEx2-Method</span><span class="sxs-lookup"><span data-stu-id="52e3c-109">StrongNameSignatureVerificationEx2 Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/strongnamesignatureverificationex2-method.md)|<span data-ttu-id="52e3c-110">Überprüft die Signatur einer Assembly mit starkem Namen und stellt eine Zuordnung zwischen dem ECMA-Schlüssel und einem echten Schlüssel bereit.</span><span class="sxs-lookup"><span data-stu-id="52e3c-110">Verifies the signature of a strongly named assembly, and provides a mapping from the ECMA key to a real key.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="52e3c-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="52e3c-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52e3c-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="52e3c-112">Requirements</span></span>  
 <span data-ttu-id="52e3c-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52e3c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52e3c-114">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="52e3c-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="52e3c-115">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="52e3c-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="52e3c-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52e3c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>
