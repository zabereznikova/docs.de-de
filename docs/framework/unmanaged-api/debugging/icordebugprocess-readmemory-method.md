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
ms.openlocfilehash: dca2a4e5ee869346108137a8ba01ab8855756725
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792555"
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
  
## <a name="parameters"></a>Parameters  
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
  
 Alle verwalteten Breakpoints werden aus den Daten entfernt, die im `buffer`-Parameter zurückgegeben werden. Für Native Breakpoints, die von [ICorDebugProcess2:: SetUnmanagedBreakpoint](icordebugprocess2-setunmanagedbreakpoint-method.md)festgelegt werden, werden keine Anpassungen vorgenommen.  
  
 Es wird kein Zwischenspeichern des Prozess Arbeitsspeichers ausgeführt.  
  
## <a name="requirements"></a>-Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
