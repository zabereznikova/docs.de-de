---
title: ICorDebugStringValue::GetLength-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugStringValue.GetLength
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStringValue::GetLength
helpviewer_keywords:
- ICorDebugStringValue::GetLength method [.NET Framework debugging]
- GetLength method [.NET Framework debugging]
ms.assetid: a1ebfc69-46a6-4225-8788-b7cfb2f15e1d
topic_type:
- apiref
ms.openlocfilehash: 74a4b42be09c577cc80f1a73e077694e5a4a8d5f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697115"
---
# <a name="icordebugstringvaluegetlength-method"></a>ICorDebugStringValue::GetLength-Methode

Ruft die Anzahl der Zeichen in der Zeichenfolge ab, auf die dieser ICorDebug-Wert verweist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetLength (  
    [out] ULONG32   *pcchString  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `pcchString`  
 vorgenommen Ein Zeiger auf einen-Wert, der die Länge der Zeichenfolge angibt, auf die von diesem-Objekt verwiesen wird `ICorDebugStringValue` .  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
