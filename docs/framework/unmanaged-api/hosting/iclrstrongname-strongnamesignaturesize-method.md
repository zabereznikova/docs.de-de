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
ms.openlocfilehash: e789996af3aedd17251fc52cde52a336f65053ec
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176343"
---
# <a name="iclrstrongnamestrongnamesignaturesize-method"></a><span data-ttu-id="d0663-102">ICLRStrongName::StrongNameSignatureSize-Methode</span><span class="sxs-lookup"><span data-stu-id="d0663-102">ICLRStrongName::StrongNameSignatureSize Method</span></span>
<span data-ttu-id="d0663-103">Gibt die Größe der Signatur mit starkem Namen zurück.</span><span class="sxs-lookup"><span data-stu-id="d0663-103">Returns the size of the strong name signature.</span></span> <span data-ttu-id="d0663-104">Diese Methode wird in der Regel von Compilern verwendet, um zu bestimmen, wie viel Speicherplatz in der Datei reserviert werden soll, wenn eine mit Verzögerung signierte Assembly erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="d0663-104">This method is typically used by compilers to determine how much space to reserve in the file when creating a delay-signed assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0663-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="d0663-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameSignatureSize (
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,
    [in]  DWORD  *pcbSize  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="d0663-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="d0663-106">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="d0663-107">[in] Eine Struktur vom Typ [PublicKeyBlob,](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) die den öffentlichen Teil des Schlüsselpaars enthält, der zum Generieren der Signatur mit starkem Namen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d0663-107">[in] A structure of type [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="d0663-108">[in] Die Größe von in `pbPublicKeyBlob`Bytes von .</span><span class="sxs-lookup"><span data-stu-id="d0663-108">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="d0663-109">[in] Die Anzahl der Bytes, die zum Speichern der Signatur mit starkem Namen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="d0663-109">[in] The number of bytes required to store the strong name signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d0663-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d0663-110">Return Value</span></span>  
 <span data-ttu-id="d0663-111">`S_OK`wenn die Methode erfolgreich abgeschlossen wurde; Andernfalls ein HRESULT-Wert, der auf einen Fehler hinweist (siehe [Allgemeine HRESULT-Werte](/windows/win32/seccrypto/common-hresult-values) für eine Liste).</span><span class="sxs-lookup"><span data-stu-id="d0663-111">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0663-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d0663-112">Requirements</span></span>  
 <span data-ttu-id="d0663-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d0663-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0663-114">**Kopfzeile:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="d0663-114">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="d0663-115">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d0663-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d0663-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0663-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0663-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d0663-117">See also</span></span>

- [<span data-ttu-id="d0663-118">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d0663-118">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
