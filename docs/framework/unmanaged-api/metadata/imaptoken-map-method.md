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
ms.openlocfilehash: 428b022ed560648f59798154d5987d382938c280
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176070"
---
# <a name="imaptokenmap-method"></a>IMapToken::Map-Methode
Ordnet eine Beziehung zwischen den Assemblys mithilfe von Metadatensignaturen zu.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Map (  
    [in]  mdToken tkImp,
    [in]  mdToken tkEmit  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `tkImp`  
 [in] Das Metadatentoken, das das importierte Codeobjekt darstellt.  
  
 `tkEmit`  
 [in] Das Metadatentoken, das das emittierte Codeobjekt darstellt.  
  
## <a name="remarks"></a>Bemerkungen  
 Wenn die Neuzuordnung des Tokens während einer Zusammenführung auftritt, wird das ursprüngliche Token im importierten (Quell-)Metadatenbereich und das neue Token im emittierten (Ziel-)Metadatenbereich bereichiert.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Kopfzeile:** Cor.h  
  
 **Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMapToken-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md)
