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
ms.openlocfilehash: e064a7db131a671adc4d0b6df522f3456e3a31d5
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83377153"
---
# <a name="icordebugthread2getactivefunctions-method"></a>ICorDebugThread2::GetActiveFunctions-Methode
Ruft Informationen über die aktive Funktion in den einzelnen Rahmen dieses Threads ab.  
  
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
 vorgenommen Ein Zeiger auf die Anzahl der-Objekte, die im-Array zurückgegeben werden `pFunctions` . Die Anzahl der zurückgegebenen Objekte ist gleich der Anzahl der verwalteten Frames auf dem Stapel.  
  
 `pFunctions`  
 [in, out] Ein Array von COR_ACTIVE_FUNCTION-Objekten, von denen jede Informationen über die aktiven Funktionen in den Frames dieses Threads enthält.  
  
 Das erste-Element wird für den blattrahmen verwendet usw. zurück zum Stamm des Stapels.  
  
## <a name="remarks"></a>Hinweise  
 Wenn `pFunctions` bei Eingabe NULL ist, `GetActiveFunctions` gibt nur die Anzahl der Funktionen zurück, die sich auf dem Stapel befinden. Das heißt, wenn `pFunctions` bei Eingabe NULL ist, `GetActiveFunctions` gibt nur in einen Wert zurück `pcFunctions` .  
  
 Die `GetActiveFunctions` -Methode ist als Optimierung gedacht, um die gleichen Informationen aus Frames in einer Stapel Überwachung zu erhalten, und schließt nur Frames ein, die ein ICorDebugILFrame-Objekt für Sie in der vollständigen Stapel Überwachung hätten.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
