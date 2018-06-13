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
ms.openlocfilehash: ed8b6bf60790c10b9869dcc41678be050b8979dd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420224"
---
# <a name="icordebugnativeframesetip-method"></a>ICorDebugNativeFrame::SetIP-Methode
Legt den Anweisungszeiger am angegebenen Offset Speicherort in systemeigenem Code.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `nOffset`  
 [in] Die Offsetposition im systemeigenen Code.  
  
## <a name="remarks"></a>Hinweise  
 Aufrufe von `SetIP` sofort ungültig werden alle Frames und Ketten für den aktuellen Thread. Wenn der Debugger die Frame-Informationen nach einem Aufruf von benötigt `SetIP`, müssen sie eine neue stapelüberwachung ausführen.  
  
 [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) versucht, den Stapelrahmen in einem gültigen Zustand zu behalten. Jedoch, selbst wenn der Frame in einem gültigen Zustand befindet, soweit die Common Language Runtime ist, weiterhin möglicherweise Probleme, z. B. nicht initialisierten lokalen Variablen und So weiter. Der Aufrufer ist verantwortlich für die Kohärenz des ausgeführten Programms.  
  
 Auf 64-Bit-Plattformen kann nicht aus der Anweisungszeiger verschoben werden eine `catch` oder `finally` Block. Wenn `SetIP` wird aufgerufen, um eine solche Verschiebung auf einer 64-Bit-Plattform zu gestalten, wird einen HRESULT-Fehler zurückgegeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 
