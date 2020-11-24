---
title: AXL_AUTHENTICODE_TIMESTAMPER_INFO-Struktur
ms.date: 03/30/2017
ms.assetid: 89e41a81-0f41-45ad-8f20-a120e4ff24fb
ms.openlocfilehash: b6852519da6cf4e12669aa2efa24862053adbc03
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674241"
---
# <a name="axl_authenticode_timestamper_info-structure"></a>AXL_AUTHENTICODE_TIMESTAMPER_INFO-Struktur

Definiert die Authenticode-Informationen des Zeitstempelgebers.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef struct _AXL_AUTHENTICODE_SIGNER_INFO {  
    DWORD cbSize;  
    HRESULT dwError;  
    ALG_ID algHash;  
    FILETIME ftTimestamp  
    PCCERT_CHAIN_CONTEXT pChainContext;  
} AXL_AUTHENTICODE_TIMESTAMPER_INFO, * PAXL_AUTHENTICODE_TIMESTAMPER_INFO;  
```  
  
## <a name="members"></a>Member  
  
|Member|BESCHREIBUNG|  
|------------|-----------------|  
|`cbSize`|Die Größe dieser Struktur.|  
|`dwError`|Der Fehlercode.|  
|`algHash`|Der hash-Algorithmus.|  
|`ftTimestamp`|Der Zeitpunkt des Zeitstempels.|  
|`pChainContext`|Der Chaincontext des Erstellers des Zeitstempels.  Siehe [CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) Struktur.|  
  
## <a name="see-also"></a>Weitere Informationen

- [Authenticode](index.md)
