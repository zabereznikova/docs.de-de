---
title: ICorDebugProcess::WriteMemory-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.WriteMemory
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::WriteMemory
helpviewer_keywords:
- ICorDebugProcess::WriteMemory method [.NET Framework debugging]
- WriteMemory method [.NET Framework debugging]
ms.assetid: d5c07d86-045d-4391-893b-0bcd2959f90e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2e9d640fb1c9dae5bb195baa504e560ba8e45821
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57497092"
---
# <a name="icordebugprocesswritememory-method"></a>ICorDebugProcess::WriteMemory-Methode
Schreibt Daten in einem Bereich des Arbeitsspeichers in diesem Prozess.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT WriteMemory(  
    [in]  CORDB_ADDRESS address,  
    [in]  DWORD size,  
    [in, size_is(size)] BYTE buffer[],  
    [out] SIZE_T *written);  
```  
  
## <a name="parameters"></a>Parameter  
 `address`  
 [in] Ein `CORDB_ADDRESS` -Wert, der die Basisadresse des Speicherbereichs, welche Daten geschrieben. Bevor die Datenübertragung erfolgt, das System überprüft, ob der Speicherbereich, der angegebenen Größe, beginnend an der Basisadresse, zum Schreiben zugegriffen werden kann. Ist dies nicht zugegriffen werden kann, schlägt die Methode fehl.  
  
 `size`  
 [in] Die Anzahl der Bytes in den Speicherbereich geschrieben werden sollen.  
  
 `buffer`  
 [in] Ein Puffer, der zu schreibenden Daten enthält.  
  
 `written`  
 [out] Ein Zeiger auf eine Variable, die Anzahl der Bytes, die in den Speicherbereich in diesem Prozess geschrieben empfängt. Wenn `written` NULL ist, dieser Parameter wird ignoriert.  
  
## <a name="remarks"></a>Hinweise  
 Daten werden automatisch hinter die Haltepunkte geschrieben. In .NET Framework, Version 2.0 verwenden systemeigenen Debugger nicht diese Methode, Haltepunkte in den Anweisungsstream einzufügen. Verwendung [ICorDebugProcess2:: SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md) stattdessen.  
  
 Die `WriteMemory` Methode sollte nur außerhalb von verwaltetem Code verwendet werden. Diese Methode kann die Laufzeit beschädigt werden, wenn nicht ordnungsgemäß verwendet.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
