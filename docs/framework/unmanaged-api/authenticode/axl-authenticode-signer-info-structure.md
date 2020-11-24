---
title: AXL_AUTHENTICODE_SIGNER_INFO-Struktur
ms.date: 03/30/2017
ms.assetid: 81c0f8b4-ce35-4716-8651-b642d40648a2
ms.openlocfilehash: 1bb6df4aa82f8dfc367083732af2065aba9d07b1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679987"
---
# <a name="axl_authenticode_signer_info-structure"></a>AXL_AUTHENTICODE_SIGNER_INFO-Struktur

Definiert die Authenticode-Informationen des Signaturgebers.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`cbSize`|Die Größe dieser Struktur.|  
|`dwError`|Der Fehlercode.|  
|`algHash`|Der hash-Algorithmus.|  
|`pwszHash`|Der Hash.|  
|`pwszDescription`|Die Beschreibung.|  
|`pwszDescriptionUrl`|Die URL der Beschreibung.|  
|`pChainContext`|Der Chaincontext des Signaturgebers. Siehe [CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) Struktur.|  
  
## <a name="see-also"></a>Weitere Informationen

- [Authenticode](index.md)
