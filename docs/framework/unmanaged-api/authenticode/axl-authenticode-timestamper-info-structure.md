---
title: AXL_AUTHENTICODE_TIMESTAMPER_INFO-Struktur
ms.date: 03/30/2017
ms.assetid: 89e41a81-0f41-45ad-8f20-a120e4ff24fb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d7f4fff4f2c2b3dd04625f4cf50b8b19a0ef6f39
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43415896"
---
# <a name="axlauthenticodetimestamperinfo-structure"></a>AXL_AUTHENTICODE_TIMESTAMPER_INFO-Struktur
Definiert Informationen zum Ersteller des Zeitstempels für Authenticode.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef struct _AXL_AUTHENTICODE_SIGNER_INFO {  
    DWORD cbSize;  
    HRESULT dwError;  
    ALG_ID algHash;  
    FILETIME ftTimestamp  
    PCCERT_CHAIN_CONTEXT pChainContext;  
} AXL_AUTHENTICODE_TIMESTAMPER_INFO, * PAXL_AUTHENTICODE_TIMESTAMPER_INFO;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`cbSize`|Die Größe dieser Struktur.|  
|`dwError`|Der Fehlercode.|  
|`algHash`|Der hash-Algorithmus.|  
|`ftTimestamp`|Der Zeitpunkt des Zeitstempels.|  
|`pChainContext`|Der Chaincontext des Erstellers des Zeitstempels.  Finden Sie unter den [CERT_CONTEXT](/windows/desktop/api/wincrypt/ns-wincrypt-_cert_context) Struktur.|  
  
## <a name="see-also"></a>Siehe auch  
 [Authenticode](../../../../docs/framework/unmanaged-api/authenticode/index.md)
