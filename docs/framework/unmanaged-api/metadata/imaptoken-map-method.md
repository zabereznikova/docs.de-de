---
title: IMapToken::Map-Methode
ms.date: 03/30/2017
api_name:
- IMapToken.Map
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMapToken::Map
helpviewer_keywords:
- IMapToken::Map method [.NET Framework metadata]
- Map method [.NET Framework metadata]
ms.assetid: b9b4bf2f-1098-43d6-9619-a99b4bda1940
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ece12247e48a0a005fd542bf76a32a1c6eeaa7cb
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478401"
---
# <a name="imaptokenmap-method"></a>IMapToken::Map-Methode
Ordnet eine Beziehung zwischen den Signaturen von Metadaten mit Assemblys.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT Map (  
    [in]  mdToken tkImp,   
    [in]  mdToken tkEmit  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `tkImp`  
 [in] Das Metadatentoken, das das importierte Codeobjekt darstellt.  
  
 `tkEmit`  
 [in] Das Metadatentoken, das ausgegebene Code darstellt.  
  
## <a name="remarks"></a>Hinweise  
 Wenn das token neu zuordnen während eines Merge auftritt, bezieht sich das ursprüngliche Token im Metadatenbereich importiert (Quelle) und das neue Token im Metadatenbereich ausgegeben (Ziel) ausgerichtet ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** Als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [IMapToken-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md)
