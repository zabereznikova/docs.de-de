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
ms.openlocfilehash: e41be6407076a2609a83a5be3b0c42d28914ec38
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720341"
---
# <a name="getpublickeytoken-method"></a><span data-ttu-id="f3023-102">GetPublicKeyToken-Methode</span><span class="sxs-lookup"><span data-stu-id="f3023-102">GetPublicKeyToken Method</span></span>

<span data-ttu-id="f3023-103">Ruft das Token des öffentlichen Schlüssels für eine angegebene keyfile oder einen Schlüssel Container ab.</span><span class="sxs-lookup"><span data-stu-id="f3023-103">Retrieves the public key token for a given keyfile or key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3023-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f3023-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPublicKeyToken(  
    LPCWSTR pszKeyFile,  
    LPCWSTR pszKeyContainer,  
    void* pvPublicKeyToken,  
    DWORD* pcbPublicKeyToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="f3023-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f3023-105">Parameters</span></span>  

 `pszKeyFile`  
 <span data-ttu-id="f3023-106">Der Dateiname des Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="f3023-106">Filename of the key.</span></span>  
  
 `pszKeyContainer`  
 <span data-ttu-id="f3023-107">Der Name des Schlüssel Containers.</span><span class="sxs-lookup"><span data-stu-id="f3023-107">Name of the key container.</span></span>  
  
 `pvPublicKeyToken`  
 <span data-ttu-id="f3023-108">Adresse, an der das Schlüssel Token gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="f3023-108">Address where key token is to be stored.</span></span>  
  
 `pcbPublicKeyToken`  
 <span data-ttu-id="f3023-109">Gibt die Größe (in Bytes) des Puffers an, der durch angegeben wird `pvPublicKeyToken` .</span><span class="sxs-lookup"><span data-stu-id="f3023-109">Specifies the size, in bytes, of the buffer indicated by `pvPublicKeyToken`.</span></span> <span data-ttu-id="f3023-110">Enthält bei der Rückgabe die tatsächliche Anzahl der verwendeten Bytes.</span><span class="sxs-lookup"><span data-stu-id="f3023-110">Upon return, contains actual number of bytes used.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f3023-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f3023-111">Return Value</span></span>  

 <span data-ttu-id="f3023-112">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="f3023-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3023-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f3023-113">Requirements</span></span>  

 <span data-ttu-id="f3023-114">Erfordert Alink. h.</span><span class="sxs-lookup"><span data-stu-id="f3023-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3023-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f3023-115">See also</span></span>

- [<span data-ttu-id="f3023-116">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f3023-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="f3023-117">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f3023-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="f3023-118">ALink-API</span><span class="sxs-lookup"><span data-stu-id="f3023-118">ALink API</span></span>](index.md)
