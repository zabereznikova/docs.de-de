---
title: ICorDebugNativeFrame::SetIP-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.SetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::SetIP
helpviewer_keywords:
- ICorDebugNativeFrame::SetIP method [.NET Framework debugging]
- SetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 57784a51-c76d-48f8-9392-584d0e1946d9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 33a4315d8908906e9ae1511aa9501969752d4af6
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484861"
---
# <a name="icordebugnativeframesetip-method"></a>ICorDebugNativeFrame::SetIP-Methode
Legt den Anweisungszeiger auf die angegebenen Offsetposition in systemeigenem Code fest.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `nOffset`  
 [in] Die Offsetposition im nativen Code.  
  
## <a name="remarks"></a>Hinweise  
 Aufrufe von `SetIP` direkt für ungültig erklären alle Rahmen und Ketten für den aktuellen Thread. Wenn der Debugger die Frame-Informationen nach einem Aufruf von benötigt `SetIP`, müssen sie eine neue stapelüberwachung ausführen.  
  
 [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) wird versucht, den Stapelrahmen in einem gültigen Zustand zu halten. Allerdings auch, wenn der Frame in einem gültigen Zustand ist, als die Runtime geht, gibt es immer noch möglicherweise Probleme, z. B. nicht initialisierten lokalen Variablen und So weiter. Der Aufrufer ist verantwortlich für die Kohärenz des laufenden Programms.  
  
 Auf 64-Bit-Plattformen kann nicht von der Anweisungszeiger verschoben werden eine `catch` oder `finally` Block. Wenn `SetIP` wird aufgerufen, um eine solche Verschiebung auf einer 64-Bit-Plattform zu machen, wird einen HRESULT-Fehler zurückgegeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

