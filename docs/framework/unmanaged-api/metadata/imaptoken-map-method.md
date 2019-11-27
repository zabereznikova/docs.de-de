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
ms.openlocfilehash: fd362beb9f8fd7a1f2076eb6490a96c0358520e4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432151"
---
# <a name="imaptokenmap-method"></a>IMapToken::Map-Methode
Ordnet mithilfe von Metadatensignaturen eine Beziehung zwischen den Assemblys zu.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Map (  
    [in]  mdToken tkImp,   
    [in]  mdToken tkEmit  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `tkImp`  
 in Das Metadatentoken, das das importierte Code Objekt darstellt.  
  
 `tkEmit`  
 in Das Metadatentoken, das das ausgegebene Code Objekt darstellt.  
  
## <a name="remarks"></a>Hinweise  
 Wenn die erneute Zuordnung des Tokens während einer Zusammenführung auftritt, wird das ursprüngliche Token in den importierten (Quell-) Metadatenbereich festgelegt, und das neue Token wird im ausgegebenen (Ziel-) Metadatenbereich festgelegt.  
  
## <a name="requirements"></a>Voraussetzungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [IMapToken-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md)
