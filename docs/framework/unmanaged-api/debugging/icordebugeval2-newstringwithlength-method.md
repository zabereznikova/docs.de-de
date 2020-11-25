---
title: ICorDebugEval2::NewStringWithLength-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.NewStringWithLength
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::NewStringWithLength
helpviewer_keywords:
- NewStringWithLength method [.NET Framework debugging]
- ICorDebugEval2::NewStringWithLength method [.NET Framework debugging]
ms.assetid: d5f54a34-6335-4708-b407-a756ec70fab4
topic_type:
- apiref
ms.openlocfilehash: e5bab32f6d18c87b030f484a47bc3f1d525d2338
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729628"
---
# <a name="icordebugeval2newstringwithlength-method"></a>ICorDebugEval2::NewStringWithLength-Methode

Erstellt eine Zeichenfolge mit der angegebenen Länge und dem angegebenen Inhalt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT NewStringWithLength (  
    [in] LPCWSTR               string,  
    [in] UINT                  uiLength  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `string`  
 in Ein Zeiger auf den Zeichen folgen Wert.  
  
 `uiLength`  
 in Länge der Zeichenfolge.  
  
## <a name="remarks"></a>Hinweise  

 Wenn erwartet wird, dass das nachfolgende NULL-Zeichen in der verwalteten Zeichenfolge enthalten ist, muss der Aufrufer der- `NewStringWithLength` Methode sicherstellen, dass die Zeichen folgen Länge das nachfolgende NULL-Zeichen enthält.  
  
 Die Zeichenfolge wird immer in der Anwendungsdomäne erstellt, in der der Thread gerade ausgeführt wird.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
