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
ms.openlocfilehash: 65de42a0b86e4b4593b7880e9dc290ce00007a40
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709257"
---
# <a name="icordebugnativeframesetip-method"></a>ICorDebugNativeFrame::SetIP-Methode

Legt den Anweisungs Zeiger auf die angegebene Offset Position in nativem Code fest.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `nOffset`  
 in Die Offset Position im systemeigenen Code.  
  
## <a name="remarks"></a>Hinweise  

 Ruft auf, um `SetIP` alle Frames und Ketten für den aktuellen Thread sofort für ungültig zu erklären. Wenn der Debugger nach einem-Aufrufvorgang Frame Informationen benötigt `SetIP` , muss er eine neue Stapel Überwachung ausführen.  
  
 [ICorDebug](icordebug-interface.md) versucht, den Stapel Rahmen in einem gültigen Zustand zu belassen. Auch wenn sich der Frame in einem gültigen Zustand befindet, soweit die Laufzeit betroffen ist, können Probleme wie nicht initialisierte lokale Variablen usw. auftreten. Der Aufrufer ist dafür verantwortlich, die Kohärenz des laufenden Programms zu sichern.  
  
 Auf 64-Bit-Plattformen kann der Anweisungs Zeiger nicht aus einem-oder-Block verschoben werden `catch` `finally` . Wenn `SetIP` aufgerufen wird, um eine solche Verschiebung auf einer 64-Bit-Plattform vorzunehmen, wird ein HRESULT zurückgegeben, das einen Fehler anzeigt.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen
