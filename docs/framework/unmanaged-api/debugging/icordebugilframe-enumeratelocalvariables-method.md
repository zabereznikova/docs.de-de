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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c18f2fce23e979f27d9116e74b6c6b007cd33bf0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752887"
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
 [out] Ein Zeiger auf die Adresse des ICorDebugValueEnum-Objekts, das den Enumerator für die lokalen Variablen in diesem Frame ist.  
  
## <a name="remarks"></a>Hinweise  
 `EnumerateLocalVariables` Ruft einen Enumerator, der den verfügbaren lokalen Variablen in den Aufrufframe auflisten kann, die von diesem ICorDebugILFrame-Objekt dargestellt wird. Die Liste kann alle lokalen Variablen in der ausgeführten-Funktion nicht enthalten, da einige von ihnen möglicherweise nicht aktiv sind.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
