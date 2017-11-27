---
title: IMapToken::Map-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMapToken.Map
api_location: mscoree.dll
api_type: COM
f1_keywords: IMapToken::Map
helpviewer_keywords:
- IMapToken::Map method [.NET Framework metadata]
- Map method [.NET Framework metadata]
ms.assetid: b9b4bf2f-1098-43d6-9619-a99b4bda1940
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2e3a9701bab27764803442a3cd0c24c4e412deaf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="imaptokenmap-method"></a>IMapToken::Map-Methode
Ordnet eine Beziehung zwischen den Assemblys, die mithilfe von Metadatensignaturen an.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT Map (  
    [in]  mdToken tkImp,   
    [in]  mdToken tkEmit  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `tkImp`  
 [in] Das Metadatentoken, das das importierte Codeobjekt darstellt.  
  
 `tkEmit`  
 [in] Das Metadatentoken, das das Objekt der ausgegebene Code darstellt.  
  
## <a name="remarks"></a>Hinweise  
 Wenn das token erneut zuordnen während eines Merge auftritt, das ursprüngliche Token im Metadatenbereich importierten (Quelle) beschränkt, und das neue Token wird im Metadatenbereich ausgegebenen (Ziel) bewertet.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMapToken-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md)
