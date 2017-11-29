---
title: ICorDebugCode3::GetReturnValueLiveOffset-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICorDebugCode3.GetReturnValueLiveOffset
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode3::GetReturnValueLiveOffset
helpviewer_keywords:
- ICorDebugCode3::GetReturnValueLiveOffset method [.NET Framework debugging]
- GetReturnValueLiveOffset method [.NET Framework debugging]
ms.assetid: 8c2ff5d8-8c04-4423-b1e1-e1c8764b36d3
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4516f2244b72bd4f254c5090b09d6d90579f1ae6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugcode3getreturnvalueliveoffset-method"></a>ICorDebugCode3::GetReturnValueLiveOffset-Methode
Ruft während eines festgelegten IL-Offsets die systemeigenen Offsets ab, in denen ein Haltepunkt eingefügt werden sollte, damit der Debugger den Rückgabewert aus einer Funktion abrufen kann.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
HRESULT GetReturnValueLiveOffset(  
    [in] ULONG32 ILoffset,  
    [in] ULONG32 bufferSize,   
    [out] ULONG32 *pFetched,   
    [out, size_is(buffersize), length_is(*pFetched)] ULong32 pOffsets[]  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `ILoffset`  
 Der IL-Offset. Es muss sich um eine Funktionsaufrufsite handeln, andernfalls schlägt der Funktionsaufruf fehl.  
  
 `bufferSize`  
 Die Anzahl der zum Speichern von `pOffsets` verfügbaren Bytes.  
  
 `pFetched`  
 Ein Zeiger auf die Anzahl der tatsächlich zurückgegebenen Offsets. Normalerweise ist dies der Wert 1, eine einzelne IL-Anweisung kann jedoch mehrere `CALL`-Assemblyanweisungen zuordnen.  
  
 `pOffsets`  
 Ein Array systemeigener Offsets. Normalerweise enthält `pOffsets` einen einzelnen Offset, obwohl eine einzelne IL-Anweisung mehreren `CALL`-Assemblyanweisungen zugeordnet werden kann.  
  
## <a name="remarks"></a>Hinweise  
 Diese Methode wird verwendet, zusammen mit den [icordebugilframe3:: Getreturnvalueforiloffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) Methode, um den Rückgabewert einer Methode abzurufen, die einen Verweistyp zurückgibt. Durch die Übergabe eines IL-Offsets an eine Funktionsaufrufsite für diese Methode wird mindestens ein systemeigener Offset zurückgegeben. In diesem Fall kann der Debugger Haltepunkte für diese systemeigenen Offsets in der Funktion festlegen. Wenn der Debugger einen der Haltepunkte trifft, können Sie dann den identischen IL-Offset, die Sie an diese Methode übergeben übergeben der [icordebugilframe3:: Getreturnvalueforiloffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) Methode, um den Rückgabewert abzurufen. Der Debugger sollte dann alle von ihm festgelegten Haltepunkte entfernen.  
  
> [!WARNING]
>  Die `ICorDebugCode3::GetReturnValueLiveOffset` und [icordebugilframe3:: Getreturnvalueforiloffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) Methoden ermöglichen es Ihnen, Rückgabewertinformationen nur für Verweistypen abzurufen. Das Abrufen von Rückgabewertinformationen für Werttypen wird nicht unterstützt (alle Typen, die von <xref:System.ValueType> abgeleitet werden).  
  
 Die Funktion gibt die `HRESULT`-Werte zurück, die in der folgenden Tabelle dargestellt sind.  
  
|`HRESULT`-Wert|Beschreibung|  
|---------------------|-----------------|  
|`S_OK`|Erfolgreich.|  
|`CORDBG_E_INVALID_OPCODE`|Die angegebene IL-Offsetsite ist keine Aufrufanweisung, oder die Funktion gibt `void` zurück.|  
|`CORDBG_E_UNSUPPORTED`|Der angegebene IL-Offset ist ein richtiger Aufruf, der Rückgabetyp wird für das Abrufen eines Rückgabewerts nicht unterstützt.|  
  
 Die `ICorDebugCode3::GetReturnValueLiveOffset`-Methode ist nur auf x86- und AMD64-basierten Systemen verfügbar.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [GetReturnValueForILOffset-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md)  
 [ICorDebugCode3-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)
