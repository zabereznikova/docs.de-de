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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 218279684304b766a9bf009f5891ac4910254a3c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492165"
---
# <a name="icordebugprocessreadmemory-method"></a>ICorDebugProcess::ReadMemory-Methode
Liest einen angegebenen Bereich des Arbeitsspeichers für diesen Prozess.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT ReadMemory(  
    [in]  CORDB_ADDRESS address,   
    [in]  DWORD size,  
    [out, size_is(size), length_is(size)] BYTE buffer[],  
    [out] SIZE_T *read);  
```  
  
## <a name="parameters"></a>Parameter  
 `address`  
 [in] Ein `CORDB_ADDRESS` Wert, der angibt, die Basisadresse des Arbeitsspeichers, die gelesen werden.  
  
 `size`  
 [in] Die Anzahl der Bytes, die aus dem Arbeitsspeicher gelesen werden.  
  
 `buffer`  
 [out] Ein Puffer, der den Inhalt des Arbeitsspeichers empfängt.  
  
 `read`  
 [out] Ein Zeiger auf die Anzahl der Bytes, die in den angegebenen Puffer übertragen werden.  
  
## <a name="remarks"></a>Hinweise  
 Die `ReadMemory` Methode dient in erster Linie von interop-Debuggen verwendet werden, um Speicherbereiche zu überprüfen, die durch den nicht verwalteten Teil der zu debuggenden Komponente verwendet werden. Diese Methode kann auch verwendet werden, zum Lesen von Microsoft intermediate Language (MSIL)-Code und das native JIT-kompiliertem Code.  
  
 Alle verwalteten Haltepunkte aus den Daten, die in zurückgegeben werden, entfernt werden die `buffer` Parameter. Werden keine Anpassungen vorgenommen werden, für native Haltepunkte, indem festlegen [ICorDebugProcess2:: SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md).  
  
 Kein Zwischenspeichern der Prozessspeicher wird ausgeführt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
