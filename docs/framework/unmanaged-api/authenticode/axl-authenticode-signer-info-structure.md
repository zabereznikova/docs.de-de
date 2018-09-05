---
title: AXL_AUTHENTICODE_SIGNER_INFO-Struktur
ms.date: 03/30/2017
ms.assetid: 81c0f8b4-ce35-4716-8651-b642d40648a2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4b9f54c7c57d122ac1214b9f31cc4e1d1cddd71c
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43773324"
---
# <a name="axlauthenticodesignerinfo-structure"></a>AXL_AUTHENTICODE_SIGNER_INFO-Struktur
Definiert Informationen zum Signaturgeber für Authenticode.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef struct _AXL_AUTHENTICODE_SIGNER_INFO {  
    DWORD cbSize;  
    HRESULT dwError;  
    ALG_ID algHash;  
    LPCWSTR pwszHash  
    LPCWSTR pwszDescription;  
    LPCWSTR pwszDescriptionUrl;  
    PCCERT_CHAIN_CONTEXT pChainContext  
} AXL_AUTHENTICODE_SIGNER_INFO, * PAXL_AUTHENTICODE_SIGNER_INFO;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`cbSize`|Die Größe dieser Struktur.|  
|`dwError`|Der Fehlercode.|  
|`algHash`|Der hash-Algorithmus.|  
|`pwszHash`|Der Hash.|  
|`pwszDescription`|Hierbei handelt es sich um die Beschreibung.|  
|`pwszDescriptionUrl`|Die URL der Beschreibung.|  
|`pChainContext`|Der Chaincontext des Signaturgebers. Finden Sie unter den [CERT_CONTEXT](/windows/desktop/api/wincrypt/ns-wincrypt-_cert_context) Struktur.|  
  
## <a name="see-also"></a>Siehe auch  
 [Authenticode](../../../../docs/framework/unmanaged-api/authenticode/index.md)
