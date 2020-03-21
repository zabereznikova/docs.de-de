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
ms.openlocfilehash: 383e3f8990a1f355c94ff5e9f9daa69bdbdd97bb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178653"
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
 [in] Ein `CORDB_ADDRESS` Wert, der die Basisadresse des zu lesenden Speichers angibt.  
  
 `size`  
 [in] Die Anzahl der Bytes, die aus dem Arbeitsspeicher gelesen werden sollen.  
  
 `buffer`  
 [out] Ein Puffer, der den Inhalt des Speichers empfängt.  
  
 `read`  
 [out] Ein Zeiger auf die Anzahl der Bytes, die in den angegebenen Puffer übertragen werden.  
  
## <a name="remarks"></a>Bemerkungen  
 Die `ReadMemory` Methode ist in erster Linie für das Interop-Debuggen gedacht, um Speicherbereiche zu überprüfen, die vom nicht verwalteten Teil des Debuggees verwendet werden. Diese Methode kann auch zum Lesen von MSIL-Code (Microsoft Intermediate Language) und systemeigenem JIT-kompilierten Code verwendet werden.  
  
 Alle verwalteten Haltepunkte werden aus den Daten `buffer` entfernt, die im Parameter zurückgegeben werden. Für systemeigene Haltepunkte, die von [ICorDebugProcess2::SetUnmanagedBreakpoint](icordebugprocess2-setunmanagedbreakpoint-method.md)festgelegt wurden, werden keine Anpassungen vorgenommen.  
  
 Es wird kein Zwischenspeichern des Prozessspeichers durchgeführt.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
