---
title: ICLRStrongName::StrongNameSignatureSize-Methode
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureSize
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureSize method [.NET Framework hosting]
- StrongNameSignatureSize method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 76d4f93a-5e25-4399-abcc-a1389549481d
topic_type:
- apiref
ms.openlocfilehash: f43a4e65442ca79ece71ce7e5e014309a611d7cc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671609"
---
# <a name="iclrstrongnamestrongnamesignaturesize-method"></a><span data-ttu-id="b7daf-102">ICLRStrongName::StrongNameSignatureSize-Methode</span><span class="sxs-lookup"><span data-stu-id="b7daf-102">ICLRStrongName::StrongNameSignatureSize Method</span></span>

<span data-ttu-id="b7daf-103">Gibt die Größe der Signatur mit starkem Namen zurück.</span><span class="sxs-lookup"><span data-stu-id="b7daf-103">Returns the size of the strong name signature.</span></span> <span data-ttu-id="b7daf-104">Diese Methode wird in der Regel von Compilern verwendet, um zu bestimmen, wie viel Speicherplatz in der Datei reserviert werden soll, wenn eine verzögert signierte Assembly erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="b7daf-104">This method is typically used by compilers to determine how much space to reserve in the file when creating a delay-signed assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7daf-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b7daf-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameSignatureSize (
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,
    [in]  DWORD  *pcbSize  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="b7daf-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="b7daf-106">Parameters</span></span>  

 `pbPublicKeyBlob`  
 <span data-ttu-id="b7daf-107">in Eine Struktur vom Typ [PublicKeyBlob](../strong-naming/publickeyblob-structure.md) , die den öffentlichen Teil des Schlüssel Paars enthält, das zum Generieren der starken Namens Signatur verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b7daf-107">[in] A structure of type [PublicKeyBlob](../strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="b7daf-108">in Die Größe von in Bytes `pbPublicKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="b7daf-108">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="b7daf-109">in Die Anzahl der Bytes, die zum Speichern der starken Namens Signatur erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="b7daf-109">[in] The number of bytes required to store the strong name signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b7daf-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b7daf-110">Return Value</span></span>  

 <span data-ttu-id="b7daf-111">`S_OK` , wenn die Methode erfolgreich abgeschlossen wurde. andernfalls ein HRESULT-Wert, der einen Fehler angibt (siehe [Allgemeine HRESULT-Werte](/windows/win32/seccrypto/common-hresult-values) für eine Liste).</span><span class="sxs-lookup"><span data-stu-id="b7daf-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7daf-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b7daf-112">Requirements</span></span>  

 <span data-ttu-id="b7daf-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7daf-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7daf-114">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="b7daf-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="b7daf-115">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="b7daf-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b7daf-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7daf-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7daf-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b7daf-117">See also</span></span>

- [<span data-ttu-id="b7daf-118">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b7daf-118">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
