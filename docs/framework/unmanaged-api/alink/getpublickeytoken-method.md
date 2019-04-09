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
ms.openlocfilehash: 0d1b28eadc9f09abff799f99d1d6012c98b1d3dd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59215767"
---
# <a name="getpublickeytoken-method"></a><span data-ttu-id="fed6d-102">GetPublicKeyToken-Methode</span><span class="sxs-lookup"><span data-stu-id="fed6d-102">GetPublicKeyToken Method</span></span>
<span data-ttu-id="fed6d-103">Ruft das Token des öffentlichen Schlüssels für eine angegebene Schlüsseldatei oder Schlüsselcontainer ab.</span><span class="sxs-lookup"><span data-stu-id="fed6d-103">Retrieves the public key token for a given keyfile or key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fed6d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fed6d-104">Syntax</span></span>  
  
```  
HRESULT GetPublicKeyToken(  
    LPCWSTR pszKeyFile,  
    LPCWSTR pszKeyContainer,  
    void* pvPublicKeyToken,  
    DWORD* pcbPublicKeyToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="fed6d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fed6d-105">Parameters</span></span>  
 `pszKeyFile`  
 <span data-ttu-id="fed6d-106">Der Dateiname des Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="fed6d-106">Filename of the key.</span></span>  
  
 `pszKeyContainer`  
 <span data-ttu-id="fed6d-107">Der Name des Schlüsselcontainers.</span><span class="sxs-lookup"><span data-stu-id="fed6d-107">Name of the key container.</span></span>  
  
 `pvPublicKeyToken`  
 <span data-ttu-id="fed6d-108">Die Adresse, in dem Token des Schlüssels ist, gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="fed6d-108">Address where key token is to be stored.</span></span>  
  
 `pcbPublicKeyToken`  
 <span data-ttu-id="fed6d-109">Gibt die Größe in Byte des Puffers erkennbar `pvPublicKeyToken`.</span><span class="sxs-lookup"><span data-stu-id="fed6d-109">Specifies the size, in bytes, of the buffer indicated by `pvPublicKeyToken`.</span></span> <span data-ttu-id="fed6d-110">Enthält bei der Rückgabe die tatsächliche Anzahl von Bytes verwendet.</span><span class="sxs-lookup"><span data-stu-id="fed6d-110">Upon return, contains actual number of bytes used.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fed6d-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="fed6d-111">Return Value</span></span>  
 <span data-ttu-id="fed6d-112">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="fed6d-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fed6d-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fed6d-113">Requirements</span></span>  
 <span data-ttu-id="fed6d-114">Erfordert alink.h an.</span><span class="sxs-lookup"><span data-stu-id="fed6d-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fed6d-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fed6d-115">See also</span></span>

- [<span data-ttu-id="fed6d-116">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fed6d-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="fed6d-117">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fed6d-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="fed6d-118">ALink-API</span><span class="sxs-lookup"><span data-stu-id="fed6d-118">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
