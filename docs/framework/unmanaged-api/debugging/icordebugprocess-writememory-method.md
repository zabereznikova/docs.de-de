---
title: ICorDebugProcess::WriteMemory-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess.WriteMemory
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess::WriteMemory
helpviewer_keywords:
- ICorDebugProcess::WriteMemory method [.NET Framework debugging]
- WriteMemory method [.NET Framework debugging]
ms.assetid: d5c07d86-045d-4391-893b-0bcd2959f90e
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2a1a12d1393d1db69ea47833958fdf828b552064
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
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
  
#### <a name="parameters"></a>Parameter  
 `address`  
 [in] Ein `CORDB_ADDRESS` -Wert, der die Basisadresse des Speicherbereichs, welche Daten geschrieben. Bevor die Datenübertragung erfolgt, das System überprüft, ob der Speicherbereich, der angegebenen Größe, beginnend an der Basisadresse zum Schreiben zugegriffen werden kann. Wenn es nicht möglich ist, schlägt die Methode fehl.  
  
 `size`  
 [in] Die Anzahl der Bytes in den Speicherbereich geschrieben werden sollen.  
  
 `buffer`  
 [in] Ein Puffer, der zu schreibenden Daten enthält.  
  
 `written`  
 [out] Ein Zeiger auf eine Variable, die Anzahl der Bytes, die in den Speicherbereich in diesem Prozess geschrieben empfängt. Wenn `written` NULL ist, wird dieser Parameter ignoriert.  
  
## <a name="remarks"></a>Hinweise  
 Daten werden automatisch hinter die Haltepunkte geschrieben. In .NET Framework, Version 2.0 verwenden nativen Debugger nicht diese Methode zum Einfügen von Haltepunkten in den Anweisungsstream. Verwendung [ICorDebugProcess2:: SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md) stattdessen.  
  
 Die `WriteMemory` Methode sollte nur außerhalb von verwaltetem Code verwendet werden. Diese Methode kann die Common Language Runtime beschädigt werden, wenn Sie nicht ordnungsgemäß verwendet.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
