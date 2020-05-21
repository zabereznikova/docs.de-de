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
ms.openlocfilehash: 9715369f4cf1b2a7078be14a2fc597f735ab6fd3
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2020
ms.locfileid: "83763162"
---
# <a name="iclrstrongname2-interface"></a><span data-ttu-id="ce886-102">ICLRStrongName2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ce886-102">ICLRStrongName2 Interface</span></span>
<span data-ttu-id="ce886-103">Bietet die Möglichkeit, starke Namen mithilfe der SHA-2-Gruppe von sicheren Hash Algorithmen (SHA-256, SHA-384 und SHA-512) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ce886-103">Provides the ability to create strong names using the SHA-2 group of Secure Hash Algorithms (SHA-256, SHA-384, and SHA-512).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ce886-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="ce886-104">Methods</span></span>  
  
|<span data-ttu-id="ce886-105">Methode</span><span class="sxs-lookup"><span data-stu-id="ce886-105">Method</span></span>|<span data-ttu-id="ce886-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ce886-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ce886-107">StrongNameGetPublicKeyEx-Methode</span><span class="sxs-lookup"><span data-stu-id="ce886-107">StrongNameGetPublicKeyEx Method</span></span>](strongnamegetpublickeyex-method.md)|<span data-ttu-id="ce886-108">Ruft den öffentlichen Schlüssel aus einem Paar aus öffentlichem und privatem Schlüssel ab und gibt einen Hash Algorithmus und einen Signatur Algorithmus an.</span><span class="sxs-lookup"><span data-stu-id="ce886-108">Gets the public key from a public/private key pair, and specifies a hash algorithm and a signature algorithm.</span></span>|  
|[<span data-ttu-id="ce886-109">StrongNameSignatureVerificationEx2-Method</span><span class="sxs-lookup"><span data-stu-id="ce886-109">StrongNameSignatureVerificationEx2 Method</span></span>](strongnamesignatureverificationex2-method.md)|<span data-ttu-id="ce886-110">Überprüft die Signatur einer Assembly mit starkem Namen und stellt eine Zuordnung zwischen dem ECMA-Schlüssel und einem echten Schlüssel bereit.</span><span class="sxs-lookup"><span data-stu-id="ce886-110">Verifies the signature of a strongly named assembly, and provides a mapping from the ECMA key to a real key.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ce886-111">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ce886-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce886-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ce886-112">Requirements</span></span>  
 <span data-ttu-id="ce886-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce886-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce886-114">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="ce886-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="ce886-115">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="ce886-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ce886-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce886-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>
