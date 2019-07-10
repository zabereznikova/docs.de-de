---
title: ICorDebugILFrame::SetIP-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.SetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::SetIP
helpviewer_keywords:
- SetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::SetIP method [.NET Framework debugging]
ms.assetid: 23f38dc1-85e4-4263-9235-2d05bbb6a833
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2af3f58fa7714b3c2b0ba387b1da650f0638dd6c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67758778"
---
# <a name="icordebugilframesetip-method"></a>ICorDebugILFrame::SetIP-Methode
Legt den Anweisungszeiger am angegebenen Offset Speicherort im Microsoft intermediate Language (MSIL)-Code fest.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `nOffset`  
 Die Offsetposition im MSIL-Code.  
  
## <a name="remarks"></a>Hinweise  
 Aufrufe von `SetIP` direkt für ungültig erklären alle Rahmen und Ketten für den aktuellen Thread. Wenn der Debugger die Frame-Informationen nach einem Aufruf von benötigt `SetIP`, müssen sie eine neue stapelüberwachung ausführen.  
  
 [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) wird versucht, den Stapelrahmen in einem gültigen Zustand zu halten. Allerdings auch, wenn der Frame in einem gültigen Zustand ist, gibt es immer noch möglicherweise Probleme wie z. B. nicht initialisierten lokalen Variablen. Der Aufrufer ist verantwortlich für die Kohärenz des laufenden Programms.  
  
 Auf 64-Bit-Plattformen kann nicht von der Anweisungszeiger verschoben werden eine `catch` oder `finally` Block. Wenn `SetIP` wird aufgerufen, um eine solche Verschiebung auf einer 64-Bit-Plattform zu machen, wird einen HRESULT-Fehler zurückgegeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
