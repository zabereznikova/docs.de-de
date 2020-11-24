---
title: CertFreeAuthenticodeTimestamperInfo-Funktion
ms.date: 03/30/2017
api_name:
- CertFreeAuthenticodeTimestamperInfo
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 3eb14c49-68c2-4516-ac89-e5bd7473831c
ms.openlocfilehash: 1ef71b14faf66c179030dff2a7d953e27463c1f7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674163"
---
# <a name="certfreeauthenticodetimestamperinfo-function"></a>CertFreeAuthenticodeTimestamperInfo-Funktion

Gibt Ressourcen frei, die der [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) Struktur zugeordnet sind.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT CertFreeAuthenticodeTimestamperInfo (  
    [in, out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO   pTimestamperInfo  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `pTimestamperInfo`  
 [in, out] Informationen über den Ersteller des Zeitstempels, die veröffentlicht werden sollen. Siehe [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) Struktur.  
  
## <a name="return-value"></a>Rückgabewert  

 `S_OK`, wenn die Funktion erfolgreich ausgeführt wurde. Andernfalls wird ein Fehlercode zurückgegeben.  
  
## <a name="see-also"></a>Weitere Informationen

- [Authenticode](index.md)
