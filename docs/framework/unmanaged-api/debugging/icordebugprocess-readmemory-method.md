---
title: ICorDebugProcess::ReadMemory-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess.ReadMemory
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess::ReadMemory
helpviewer_keywords:
- ReadMemory method [.NET Framework debugging]
- ICorDebugProcess::ReadMemory method [.NET Framework debugging]
ms.assetid: 28e4b2f6-9589-445c-be24-24a3306795e7
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 33345ada6606bc1a43a630340251d3ba1404b2f2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
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
  
#### <a name="parameters"></a>Parameter  
 `address`  
 [in] Ein `CORDB_ADDRESS` Wert, der die Basisadresse des Arbeitsspeichers zu lesende angibt.  
  
 `size`  
 [in] Die Anzahl der Bytes, die aus dem Arbeitsspeicher gelesen werden.  
  
 `buffer`  
 [out] Ein Puffer, der den Inhalt des Arbeitsspeichers empfängt.  
  
 `read`  
 [out] Ein Zeiger auf die Anzahl der Bytes, die in den angegebenen Puffer übertragen werden.  
  
## <a name="remarks"></a>Hinweise  
 Die `ReadMemory` -Methode ist hauptsächlich von Interop-Debuggen verwendet werden, um Speicherbereiche zu überprüfen, die durch den nicht verwalteten Teil der zu debuggenden Komponente verwendet werden. Diese Methode kann auch verwendet werden, um Microsoft intermediate Language (MSIL)-Code und den systemeigenen JIT-kompilierten Code lesen.  
  
 Alle verwalteten Haltepunkte aus den Daten, die in zurückgegeben werden, entfernt werden die `buffer` Parameter. Ohne Korrekturen durchgeführt werden, für die systemeigene Haltepunkte festlegen, indem Sie [ICorDebugProcess2:: SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md).  
  
 Keine der Prozessspeicher zwischengespeichert.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
