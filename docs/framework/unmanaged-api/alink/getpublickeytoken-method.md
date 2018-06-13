---
title: GetPublicKeyToken-Methode
ms.date: 03/30/2017
api_name:
- IALink2.GetPublicKeyToken
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetPublicKeyToken
helpviewer_keywords:
- GetPublicKeyToken method
ms.assetid: 4a16374c-94b0-47b0-9fed-88c2b0cdccd4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 94a473d00110c07615ccdfc98bb8944e40dc30e3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405472"
---
# <a name="getpublickeytoken-method"></a><span data-ttu-id="5a4ed-102">GetPublicKeyToken-Methode</span><span class="sxs-lookup"><span data-stu-id="5a4ed-102">GetPublicKeyToken Method</span></span>
<span data-ttu-id="5a4ed-103">Ruft das Token des öffentlichen Schlüssels für eine angegebene Schlüsseldatei oder eines Schlüsselcontainers ab.</span><span class="sxs-lookup"><span data-stu-id="5a4ed-103">Retrieves the public key token for a given keyfile or key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a4ed-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5a4ed-104">Syntax</span></span>  
  
```  
HRESULT GetPublicKeyToken(  
    LPCWSTR pszKeyFile,  
    LPCWSTR pszKeyContainer,  
    void* pvPublicKeyToken,  
    DWORD* pcbPublicKeyToken  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5a4ed-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5a4ed-105">Parameters</span></span>  
 `pszKeyFile`  
 <span data-ttu-id="5a4ed-106">Der Dateiname des Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="5a4ed-106">Filename of the key.</span></span>  
  
 `pszKeyContainer`  
 <span data-ttu-id="5a4ed-107">Der Name des Schlüsselcontainers.</span><span class="sxs-lookup"><span data-stu-id="5a4ed-107">Name of the key container.</span></span>  
  
 `pvPublicKeyToken`  
 <span data-ttu-id="5a4ed-108">Adresse des Standorts Schlüsseltoken gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="5a4ed-108">Address where key token is to be stored.</span></span>  
  
 `pcbPublicKeyToken`  
 <span data-ttu-id="5a4ed-109">Gibt die Größe in Bytes, des Puffers erkennbar `pvPublicKeyToken`.</span><span class="sxs-lookup"><span data-stu-id="5a4ed-109">Specifies the size, in bytes, of the buffer indicated by `pvPublicKeyToken`.</span></span> <span data-ttu-id="5a4ed-110">Enthält bei der Rückgabe die tatsächliche Anzahl von Bytes verwendet.</span><span class="sxs-lookup"><span data-stu-id="5a4ed-110">Upon return, contains actual number of bytes used.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5a4ed-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5a4ed-111">Return Value</span></span>  
 <span data-ttu-id="5a4ed-112">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5a4ed-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a4ed-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5a4ed-113">Requirements</span></span>  
 <span data-ttu-id="5a4ed-114">Erfordert alink.h.</span><span class="sxs-lookup"><span data-stu-id="5a4ed-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a4ed-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5a4ed-115">See Also</span></span>  
 [<span data-ttu-id="5a4ed-116">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5a4ed-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="5a4ed-117">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5a4ed-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="5a4ed-118">Alink-API</span><span class="sxs-lookup"><span data-stu-id="5a4ed-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
