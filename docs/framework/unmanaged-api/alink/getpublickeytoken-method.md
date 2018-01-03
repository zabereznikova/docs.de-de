---
title: GetPublicKeyToken-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink2.GetPublicKeyToken
api_location: alink.dll
api_type: COM
f1_keywords: GetPublicKeyToken
helpviewer_keywords: GetPublicKeyToken method
ms.assetid: 4a16374c-94b0-47b0-9fed-88c2b0cdccd4
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 230c98e85bd0aa3bd2f368965b6f7ac028e43df4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="getpublickeytoken-method"></a><span data-ttu-id="20ce1-102">GetPublicKeyToken-Methode</span><span class="sxs-lookup"><span data-stu-id="20ce1-102">GetPublicKeyToken Method</span></span>
<span data-ttu-id="20ce1-103">Ruft das Token des öffentlichen Schlüssels für eine angegebene Schlüsseldatei oder eines Schlüsselcontainers ab.</span><span class="sxs-lookup"><span data-stu-id="20ce1-103">Retrieves the public key token for a given keyfile or key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20ce1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="20ce1-104">Syntax</span></span>  
  
```  
HRESULT GetPublicKeyToken(  
    LPCWSTR pszKeyFile,  
    LPCWSTR pszKeyContainer,  
    void* pvPublicKeyToken,  
    DWORD* pcbPublicKeyToken  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="20ce1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="20ce1-105">Parameters</span></span>  
 `pszKeyFile`  
 <span data-ttu-id="20ce1-106">Der Dateiname des Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="20ce1-106">Filename of the key.</span></span>  
  
 `pszKeyContainer`  
 <span data-ttu-id="20ce1-107">Der Name des Schlüsselcontainers.</span><span class="sxs-lookup"><span data-stu-id="20ce1-107">Name of the key container.</span></span>  
  
 `pvPublicKeyToken`  
 <span data-ttu-id="20ce1-108">Adresse des Standorts Schlüsseltoken gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="20ce1-108">Address where key token is to be stored.</span></span>  
  
 `pcbPublicKeyToken`  
 <span data-ttu-id="20ce1-109">Gibt die Größe in Bytes, des Puffers erkennbar `pvPublicKeyToken`.</span><span class="sxs-lookup"><span data-stu-id="20ce1-109">Specifies the size, in bytes, of the buffer indicated by `pvPublicKeyToken`.</span></span> <span data-ttu-id="20ce1-110">Enthält bei der Rückgabe die tatsächliche Anzahl von Bytes verwendet.</span><span class="sxs-lookup"><span data-stu-id="20ce1-110">Upon return, contains actual number of bytes used.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="20ce1-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="20ce1-111">Return Value</span></span>  
 <span data-ttu-id="20ce1-112">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="20ce1-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20ce1-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="20ce1-113">Requirements</span></span>  
 <span data-ttu-id="20ce1-114">Erfordert alink.h.</span><span class="sxs-lookup"><span data-stu-id="20ce1-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20ce1-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="20ce1-115">See Also</span></span>  
 [<span data-ttu-id="20ce1-116">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="20ce1-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="20ce1-117">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="20ce1-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="20ce1-118">Alink-API</span><span class="sxs-lookup"><span data-stu-id="20ce1-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
