---
title: CertFreeAuthenticodeSignerInfo-Funktion
ms.date: 03/30/2017
api_name:
- CertFreeAuthenticodeSignerInfo
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 8029633c-b6e4-4665-a7c2-89607c3247ef
ms.openlocfilehash: dc6bb5a137a50ec07f89f292e5d9beac4349c3c7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674176"
---
# <a name="certfreeauthenticodesignerinfo-function"></a>CertFreeAuthenticodeSignerInfo-Funktion

Gibt Ressourcen frei, die der [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) Struktur zugeordnet sind.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT CertFreeAuthenticodeSignerInfo (  
    [in, out]  PAXL_AUTHENTICODE_SIGNER_INFO   pSignerInfo);  
```  
  
## <a name="parameters"></a>Parameter  

 `pSignerInfo`  
 [in, out] Informationen über den Signaturgeber die veröffentlicht werden sollen. Siehe [AXL_AUTHENTICODE_SIGNER_INFO](axl-authenticode-signer-info-structure.md) Struktur.  
  
## <a name="return-value"></a>Rückgabewert  

 `S_OK`, wenn die Funktion erfolgreich ausgeführt wurde. Andernfalls wird ein Fehlercode zurückgegeben.  
  
## <a name="see-also"></a>Weitere Informationen

- [Authenticode](index.md)
