---
title: ICorDebugEval::NewString-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewString
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewString
helpviewer_keywords:
- NewString method [.NET Framework debugging]
- ICorDebugEval::NewString method [.NET Framework debugging]
ms.assetid: 29e7a14b-d50e-4852-bfda-011b76c0c9ee
topic_type:
- apiref
ms.openlocfilehash: 8a5d421bf0eb8ec5a34fe21d6efc79bbe56c294c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137641"
---
# <a name="icordebugevalnewstring-method"></a>ICorDebugEval::NewString-Methode
Weist dem angegebenen Inhalt eine neue Zeichen folgen Instanz zu.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT NewString (  
    [in] LPCWSTR   string  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `string`  
 in Zeiger auf den Inhalt der Zeichenfolge.  
  
## <a name="remarks"></a>Hinweise  
 Die Zeichenfolge wird immer in der Anwendungsdomäne erstellt, in der der Thread gerade ausgeführt wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
