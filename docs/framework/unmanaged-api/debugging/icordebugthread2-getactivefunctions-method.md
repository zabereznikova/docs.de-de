---
title: ICorDebugThread2::GetActiveFunctions-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugThread2.GetActiveFunctions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::GetActiveFunctions
helpviewer_keywords:
- GetActiveFunctions method [.NET Framework debugging]
- ICorDebugThread2::GetActiveFunctions method [.NET Framework debugging]
ms.assetid: 27fae01a-ecec-423a-973e-24f8de55826c
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ecd9446f642011b21f784019f583f49e3a70433a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthread2getactivefunctions-method"></a>ICorDebugThread2::GetActiveFunctions-Methode
Ruft Informationen über die aktive Funktion in den einzelnen Frames dieses Threads ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetActiveFunctions (  
    [in]   ULONG32             cFunctions,  
    [out]  ULONG32             *pcFunctions,  
    [in, out, size_is(cFunctions), length_is(*pcFunctions)]  
        COR_ACTIVE_FUNCTION    pFunctions[]  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `cFunctions`  
 [in] Die Größe des `pFunctions`-Arrays.  
  
 `pcFunctions`  
 [out] Ein Zeiger auf die Anzahl der zurückgegebenen Objekte die `pFunctions` Array. Die Anzahl der zurückgegebenen Objekte wird die Anzahl der verwalteten Frames auf dem Stapel gleich sein.  
  
 `pFunctions`  
 [in, out] Ein Array von COR_ACTIVE_FUNCTION-Objekten, von denen jede Informationen über die aktiven Funktionen im Rahmen dieses Threads enthält.  
  
 Das erste Element wird für den Endframe und usw. bis zurück zum Stammverzeichnis des Stapels verwendet werden.  
  
## <a name="remarks"></a>Hinweise  
 Wenn `pFunctions` bei Eingabe NULL, `GetActiveFunctions` gibt nur die Anzahl der Funktionen, die im Stapel befinden. D. h. wenn `pFunctions` bei Eingabe NULL, `GetActiveFunctions` gibt einen Wert nur in `pcFunctions`.  
  
 Die `GetActiveFunctions` Methode dient nur zur Optimierung über die gleichen Informationen abrufen, von Frames in eine stapelüberwachung und enthält nur die Frames, die ein Objekt ICorDebugILFrame dafür in das vollständige stapelüberwachung müssten.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
