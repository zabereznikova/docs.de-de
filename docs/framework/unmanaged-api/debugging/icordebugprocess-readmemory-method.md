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
ms.openlocfilehash: ef9e339c74b2d2785d758ed9c4adfc1901073253
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139363"
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
 in Ein `CORDB_ADDRESS` Wert, der die Basisadresse des zu lesenden Speichers angibt.  
  
 `size`  
 in Die Anzahl der Bytes, die aus dem Arbeitsspeicher gelesen werden sollen.  
  
 `buffer`  
 vorgenommen Ein Puffer, der den Inhalt des Arbeitsspeichers empfängt.  
  
 `read`  
 vorgenommen Ein Zeiger auf die Anzahl von Bytes, die in den angegebenen Puffer übertragen werden.  
  
## <a name="remarks"></a>Hinweise  
 Die `ReadMemory`-Methode ist hauptsächlich für das Interop-Debuggen vorgesehen, um Speicherbereiche zu überprüfen, die vom nicht verwalteten Teil der zu debuggenden Komponente verwendet werden. Diese Methode kann auch zum Lesen von MSIL-Code (Microsoft Intermediate Language) und nativem JIT-kompiliertem Code verwendet werden.  
  
 Alle verwalteten Breakpoints werden aus den Daten entfernt, die im `buffer`-Parameter zurückgegeben werden. Für Native Breakpoints, die von [ICorDebugProcess2:: SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md)festgelegt werden, werden keine Anpassungen vorgenommen.  
  
 Es wird kein Zwischenspeichern des Prozess Arbeitsspeichers ausgeführt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
