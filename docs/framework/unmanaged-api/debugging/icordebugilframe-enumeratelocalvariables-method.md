---
title: ICorDebugILFrame::EnumerateLocalVariables-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.EnumerateLocalVariables
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::EnumerateLocalVariables
helpviewer_keywords:
- EnumerateLocalVariables method [.NET Framework debugging]
- ICorDebugILFrame::EnumerateLocalVariables method [.NET Framework debugging]
ms.assetid: 1a67fa1b-2419-4cd0-aad4-6f46a0719b4b
topic_type:
- apiref
ms.openlocfilehash: 07331a512dd513a94a7d8c3a8d8b0754d998b94b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130998"
---
# <a name="icordebugilframeenumeratelocalvariables-method"></a>ICorDebugILFrame::EnumerateLocalVariables-Methode
Ruft einen Enumerator für die lokalen Variablen in diesem Frame ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT EnumerateLocalVariables(   
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `ppValueEnum`  
 vorgenommen Ein Zeiger auf die Adresse eines ICorDebugValueEnum-Objekts, bei dem es sich um den Enumerator für die lokalen Variablen in diesem Frame handelt.  
  
## <a name="remarks"></a>Hinweise  
 `EnumerateLocalVariables` Ruft einen Enumerator ab, der die lokalen Variablen auflisten kann, die in dem von diesem ICorDebugILFrame-Objekt dargestellten Aufrufframe verfügbar sind. Die Liste enthält möglicherweise nicht alle lokalen Variablen in der Funktion "wird ausgeführt", da einige von Ihnen möglicherweise nicht aktiv sind.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
