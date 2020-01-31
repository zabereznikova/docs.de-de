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
ms.openlocfilehash: bc33768e4155a0e272d3374d4c586c79ef2ff3fb
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792780"
---
# <a name="icordebugnativeframesetip-method"></a>ICorDebugNativeFrame::SetIP-Methode
Legt den Anweisungs Zeiger auf die angegebene Offset Position in nativem Code fest.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `nOffset`  
 in Die Offset Position im systemeigenen Code.  
  
## <a name="remarks"></a>Hinweise  
 Durch Aufrufe von `SetIP` werden alle Frames und Ketten für den aktuellen Thread sofort ungültig. Wenn der Debugger nach einem Aufruf`SetIP`Frame Informationen benötigt, muss er eine neue Stapel Überwachung ausführen.  
  
 [ICorDebug](icordebug-interface.md) versucht, den Stapel Rahmen in einem gültigen Zustand zu belassen. Auch wenn sich der Frame in einem gültigen Zustand befindet, soweit die Laufzeit betroffen ist, können Probleme wie nicht initialisierte lokale Variablen usw. auftreten. Der Aufrufer ist dafür verantwortlich, die Kohärenz des laufenden Programms zu sichern.  
  
 Auf 64-Bit-Plattformen kann der Anweisungs Zeiger nicht aus einem `catch` oder `finally` Block verschoben werden. Wenn `SetIP` aufgerufen wird, um eine solche Verschiebung auf einer 64-Bit-Plattform vorzunehmen, wird ein HRESULT zurückgegeben, das einen Fehler anzeigt.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
