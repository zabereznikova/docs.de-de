---
title: ICorDebugProcess::ReadMemory-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.ReadMemory
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::ReadMemory
helpviewer_keywords:
- ReadMemory method [.NET Framework debugging]
- ICorDebugProcess::ReadMemory method [.NET Framework debugging]
ms.assetid: 28e4b2f6-9589-445c-be24-24a3306795e7
topic_type:
- apiref
ms.openlocfilehash: a0abc7168ff7bffdbb835c1c1bc93de9df6e381c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95694866"
---
# <a name="icordebugprocessreadmemory-method"></a>ICorDebugProcess::ReadMemory-Methode

Liest einen angegebenen Speicherbereich für diesen Prozess.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT ReadMemory(  
    [in]  CORDB_ADDRESS address,
    [in]  DWORD size,  
    [out, size_is(size), length_is(size)] BYTE buffer[],  
    [out] SIZE_T *read);  
```  
  
## <a name="parameters"></a>Parameter  

 `address`  
 in Ein- `CORDB_ADDRESS` Wert, der die Basisadresse des zu lesenden Speichers angibt.  
  
 `size`  
 in Die Anzahl der Bytes, die aus dem Arbeitsspeicher gelesen werden sollen.  
  
 `buffer`  
 vorgenommen Ein Puffer, der den Inhalt des Arbeitsspeichers empfängt.  
  
 `read`  
 vorgenommen Ein Zeiger auf die Anzahl von Bytes, die in den angegebenen Puffer übertragen werden.  
  
## <a name="remarks"></a>Hinweise  

 Die- `ReadMemory` Methode ist hauptsächlich für das Interop-Debuggen vorgesehen, um Speicherbereiche zu überprüfen, die vom nicht verwalteten Teil der zu debuggenden Komponente verwendet werden. Diese Methode kann auch zum Lesen von MSIL-Code (Microsoft Intermediate Language) und nativem JIT-kompiliertem Code verwendet werden.  
  
 Alle verwalteten Breakpoints werden aus den Daten entfernt, die im-Parameter zurückgegeben werden `buffer` . Für Native Breakpoints, die von [ICorDebugProcess2:: SetUnmanagedBreakpoint](icordebugprocess2-setunmanagedbreakpoint-method.md)festgelegt werden, werden keine Anpassungen vorgenommen.  
  
 Es wird kein Zwischenspeichern des Prozess Arbeitsspeichers ausgeführt.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
