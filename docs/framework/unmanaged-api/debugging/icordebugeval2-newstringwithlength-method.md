---
title: ICorDebugEval2::NewStringWithLength-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval2.NewStringWithLength
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval2::NewStringWithLength
helpviewer_keywords:
- NewStringWithLength method [.NET Framework debugging]
- ICorDebugEval2::NewStringWithLength method [.NET Framework debugging]
ms.assetid: d5f54a34-6335-4708-b407-a756ec70fab4
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b794482e491dc9825b0311cf1731d159082bd1f1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugeval2newstringwithlength-method"></a>ICorDebugEval2::NewStringWithLength-Methode
Erstellt eine Zeichenfolge der angegebenen Länge und mit dem angegebenen Inhalt.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT NewStringWithLength (  
    [in] LPCWSTR               string,  
    [in] UINT                  uiLength  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `string`  
 [in] Ein Zeiger auf den Zeichenfolgenwert.  
  
 `uiLength`  
 [in] Die Länge der Zeichenfolge.  
  
## <a name="remarks"></a>Hinweise  
 Wenn die Zeichenfolge nachfolgende des Null-Zeichen wird erwartet in die verwaltete Zeichenfolge, der Aufrufer die `NewStringWithLength` Methode muss sicherstellen, dass die Länge der Zeichenfolge das abschließende Null-Zeichen enthält.  
  
 Die Zeichenfolge wird immer in der Anwendungsdomäne erstellt, in dem der Thread gerade ausgeführt wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
