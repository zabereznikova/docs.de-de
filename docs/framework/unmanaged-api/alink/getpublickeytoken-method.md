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
ms.openlocfilehash: ec2c357cd56670f4f2deed8023bed7842a7f4ed7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741882"
---
# <a name="getpublickeytoken-method"></a><span data-ttu-id="2e21d-102">GetPublicKeyToken-Methode</span><span class="sxs-lookup"><span data-stu-id="2e21d-102">GetPublicKeyToken Method</span></span>
<span data-ttu-id="2e21d-103">Ruft das Token des öffentlichen Schlüssels für eine angegebene Schlüsseldatei oder Schlüsselcontainer ab.</span><span class="sxs-lookup"><span data-stu-id="2e21d-103">Retrieves the public key token for a given keyfile or key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e21d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2e21d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPublicKeyToken(  
    LPCWSTR pszKeyFile,  
    LPCWSTR pszKeyContainer,  
    void* pvPublicKeyToken,  
    DWORD* pcbPublicKeyToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="2e21d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2e21d-105">Parameters</span></span>  
 `pszKeyFile`  
 <span data-ttu-id="2e21d-106">Der Dateiname des Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="2e21d-106">Filename of the key.</span></span>  
  
 `pszKeyContainer`  
 <span data-ttu-id="2e21d-107">Der Name des Schlüsselcontainers.</span><span class="sxs-lookup"><span data-stu-id="2e21d-107">Name of the key container.</span></span>  
  
 `pvPublicKeyToken`  
 <span data-ttu-id="2e21d-108">Die Adresse, in dem Token des Schlüssels ist, gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="2e21d-108">Address where key token is to be stored.</span></span>  
  
 `pcbPublicKeyToken`  
 <span data-ttu-id="2e21d-109">Gibt die Größe in Byte des Puffers erkennbar `pvPublicKeyToken`.</span><span class="sxs-lookup"><span data-stu-id="2e21d-109">Specifies the size, in bytes, of the buffer indicated by `pvPublicKeyToken`.</span></span> <span data-ttu-id="2e21d-110">Enthält bei der Rückgabe die tatsächliche Anzahl von Bytes verwendet.</span><span class="sxs-lookup"><span data-stu-id="2e21d-110">Upon return, contains actual number of bytes used.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2e21d-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2e21d-111">Return Value</span></span>  
 <span data-ttu-id="2e21d-112">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="2e21d-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e21d-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2e21d-113">Requirements</span></span>  
 <span data-ttu-id="2e21d-114">Erfordert alink.h an.</span><span class="sxs-lookup"><span data-stu-id="2e21d-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e21d-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2e21d-115">See also</span></span>

- [<span data-ttu-id="2e21d-116">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2e21d-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="2e21d-117">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2e21d-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="2e21d-118">Alink-API</span><span class="sxs-lookup"><span data-stu-id="2e21d-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
