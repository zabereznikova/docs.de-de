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
ms.openlocfilehash: 5f41c8088f095802cf35239afab279d6324adb55
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="getpublickeytoken-method"></a><span data-ttu-id="99644-102">GetPublicKeyToken-Methode</span><span class="sxs-lookup"><span data-stu-id="99644-102">GetPublicKeyToken Method</span></span>
<span data-ttu-id="99644-103">Ruft das Token des öffentlichen Schlüssels für eine angegebene Schlüsseldatei oder eines Schlüsselcontainers ab.</span><span class="sxs-lookup"><span data-stu-id="99644-103">Retrieves the public key token for a given keyfile or key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99644-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="99644-104">Syntax</span></span>  
  
```  
HRESULT GetPublicKeyToken(  
    LPCWSTR pszKeyFile,  
    LPCWSTR pszKeyContainer,  
    void* pvPublicKeyToken,  
    DWORD* pcbPublicKeyToken  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="99644-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="99644-105">Parameters</span></span>  
 `pszKeyFile`  
 <span data-ttu-id="99644-106">Der Dateiname des Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="99644-106">Filename of the key.</span></span>  
  
 `pszKeyContainer`  
 <span data-ttu-id="99644-107">Der Name des Schlüsselcontainers.</span><span class="sxs-lookup"><span data-stu-id="99644-107">Name of the key container.</span></span>  
  
 `pvPublicKeyToken`  
 <span data-ttu-id="99644-108">Adresse des Standorts Schlüsseltoken gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="99644-108">Address where key token is to be stored.</span></span>  
  
 `pcbPublicKeyToken`  
 <span data-ttu-id="99644-109">Gibt die Größe in Bytes, des Puffers erkennbar `pvPublicKeyToken`.</span><span class="sxs-lookup"><span data-stu-id="99644-109">Specifies the size, in bytes, of the buffer indicated by `pvPublicKeyToken`.</span></span> <span data-ttu-id="99644-110">Enthält bei der Rückgabe die tatsächliche Anzahl von Bytes verwendet.</span><span class="sxs-lookup"><span data-stu-id="99644-110">Upon return, contains actual number of bytes used.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="99644-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="99644-111">Return Value</span></span>  
 <span data-ttu-id="99644-112">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="99644-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99644-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="99644-113">Requirements</span></span>  
 <span data-ttu-id="99644-114">Erfordert alink.h.</span><span class="sxs-lookup"><span data-stu-id="99644-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99644-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="99644-115">See Also</span></span>  
 [<span data-ttu-id="99644-116">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="99644-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="99644-117">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="99644-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="99644-118">ALink-API</span><span class="sxs-lookup"><span data-stu-id="99644-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
