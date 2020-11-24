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
ms.openlocfilehash: 18416954517c3cac09d013b8075bd097305a1dca
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673963"
---
# <a name="icordebugprocesswritememory-method"></a>ICorDebugProcess::WriteMemory-Methode

Schreibt Daten in diesem Prozess in einen Arbeitsspeicher Bereich.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT WriteMemory(  
    [in]  CORDB_ADDRESS address,  
    [in]  DWORD size,  
    [in, size_is(size)] BYTE buffer[],  
    [out] SIZE_T *written);  
```  
  
## <a name="parameters"></a>Parameter  

 `address`  
 in Ein- `CORDB_ADDRESS` Wert, der die Basisadresse des Speicherbereichs ist, in den Daten geschrieben werden. Vor der Datenübertragung überprüft das System, ob der Speicherbereich der angegebenen Größe, beginnend bei der Basisadresse, zum Schreiben zugänglich ist. Wenn nicht auf Sie zugegriffen werden kann, schlägt die Methode fehl.  
  
 `size`  
 in Die Anzahl der Bytes, die in den Speicherbereich geschrieben werden sollen.  
  
 `buffer`  
 in Ein Puffer, der die zu schreibenden Daten enthält.  
  
 `written`  
 vorgenommen Ein Zeiger auf eine Variable, die die Anzahl von Bytes empfängt, die in diesem Prozess in den Speicherbereich geschrieben werden. Wenn `written` NULL ist, wird dieser Parameter ignoriert.  
  
## <a name="remarks"></a>Hinweise  

 Daten werden automatisch hinter Breakpoints geschrieben. In der .NET Framework Version 2,0 sollten Native Debugger diese Methode nicht verwenden, um Breakpoints in den Anweisungs Datenstrom einzufügen. Verwenden Sie stattdessen [ICorDebugProcess2:: Abort](icordebugprocess2-setunmanagedbreakpoint-method.md) .  
  
 Die- `WriteMemory` Methode sollte nur außerhalb von verwaltetem Code verwendet werden. Diese Methode kann die Laufzeit beschädigt werden, wenn Sie nicht ordnungsgemäß verwendet wird.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
