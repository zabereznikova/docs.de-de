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
ms.openlocfilehash: 945e4ac88634c9103a722a180a4fe92a554ca53b
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378891"
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
