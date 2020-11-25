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
ms.openlocfilehash: fdc3d96fd5ad9a6ff59b863cd3f0450283ea0146
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721373"
---
# <a name="icordebugilframesetip-method"></a>ICorDebugILFrame::SetIP-Methode

Legt den Anweisungs Zeiger auf die angegebene Offset Position im MSIL-Code (Microsoft Intermediate Language) fest.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
## <a name="parameters"></a>Parameter  

 `nOffset`  
 Die Offset Position im MSIL-Code.  
  
## <a name="remarks"></a>Hinweise  

 Ruft auf, um `SetIP` alle Frames und Ketten für den aktuellen Thread sofort für ungültig zu erklären. Wenn der Debugger nach einem-Aufrufvorgang Frame Informationen benötigt `SetIP` , muss er eine neue Stapel Überwachung ausführen.  
  
 [ICorDebug](icordebug-interface.md) versucht, den Stapel Rahmen in einem gültigen Zustand zu belassen. Auch wenn sich der Frame in einem gültigen Zustand befindet, sind möglicherweise weiterhin Probleme aufgetreten, z. b. nicht initialisierte lokale Variablen. Der Aufrufer ist dafür verantwortlich, die Kohärenz des laufenden Programms sicherzustellen.  
  
 Auf 64-Bit-Plattformen kann der Anweisungs Zeiger nicht aus einem-oder-Block verschoben werden `catch` `finally` . Wenn `SetIP` aufgerufen wird, um eine solche Verschiebung auf einer 64-Bit-Plattform vorzunehmen, wird ein HRESULT zurückgegeben, das einen Fehler anzeigt.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
