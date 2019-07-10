---
title: ICorDebugThread2::GetActiveFunctions-Methode
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fdf3998d7430348cb71af8e7dd75cf2203d380ce
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67769032"
---
# <a name="icordebugthread2getactivefunctions-method"></a>ICorDebugThread2::GetActiveFunctions-Methode
Ruft Informationen über die aktiven Funktion in dieses Threads Frames ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetActiveFunctions (  
    [in]   ULONG32             cFunctions,  
    [out]  ULONG32             *pcFunctions,  
    [in, out, size_is(cFunctions), length_is(*pcFunctions)]  
        COR_ACTIVE_FUNCTION    pFunctions[]  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `cFunctions`  
 [in] Die Größe des `pFunctions`-Arrays.  
  
 `pcFunctions`  
 [out] Ein Zeiger auf die Anzahl der zurückgegebenen Objekte die `pFunctions` Array. Die Anzahl der zurückgegebenen Objekte werden gleich der Anzahl der verwalteten Frames im Stapel.  
  
 `pFunctions`  
 [in, out] Ein Array von COR_ACTIVE_FUNCTION-Objekten, von denen jede Informationen über die aktiven Funktionen in dieses Threads Frames enthält.  
  
 Das erste Element wird für die Endframe und usw. bis zurück in das Stammverzeichnis des Stapels verwendet werden.  
  
## <a name="remarks"></a>Hinweise  
 Wenn `pFunctions` bei Eingabe NULL, `GetActiveFunctions` gibt nur die Anzahl der Funktionen, die im Stapel befinden. D. h. wenn `pFunctions` bei Eingabe NULL, `GetActiveFunctions` gibt einen Wert nur in `pcFunctions`.  
  
 Die `GetActiveFunctions` -Methode dient als eine Optimierung über die gleichen Informationen abrufen, aus der Bilder in eine stapelüberwachung und enthält nur die Frames, die ein ICorDebugILFrame-Objekt für diese in die vollständige stapelüberwachung, müssten.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
