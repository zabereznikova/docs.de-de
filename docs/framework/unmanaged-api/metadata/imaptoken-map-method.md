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
ms.openlocfilehash: 51cca1ab61027090b0d22781dfd740038bc9372d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718201"
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
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Cor. h  
  
 **Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [IMapToken-Schnittstelle](imaptoken-interface.md)
