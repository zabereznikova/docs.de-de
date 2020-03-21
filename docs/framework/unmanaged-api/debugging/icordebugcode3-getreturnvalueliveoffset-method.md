---
title: ICorDebugCode3::GetReturnValueLiveOffset-Methode
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugCode3.GetReturnValueLiveOffset
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode3::GetReturnValueLiveOffset
helpviewer_keywords:
- ICorDebugCode3::GetReturnValueLiveOffset method [.NET Framework debugging]
- GetReturnValueLiveOffset method [.NET Framework debugging]
ms.assetid: 8c2ff5d8-8c04-4423-b1e1-e1c8764b36d3
topic_type:
- apiref
ms.openlocfilehash: 34d543dd76de05bdf55d8187cf192455d1387a9f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178941"
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
  
## <a name="parameters"></a>Parameter  
 `ILoffset`  
 Der IL-Offset. Es muss sich um eine Funktionsaufrufsite handeln, andernfalls schlägt der Funktionsaufruf fehl.  
  
 `bufferSize`  
 Die Anzahl der zum Speichern von `pOffsets` verfügbaren Bytes.  
  
 `pFetched`  
 Ein Zeiger auf die Anzahl der tatsächlich zurückgegebenen Offsets. Normalerweise ist dies der Wert 1, eine einzelne IL-Anweisung kann jedoch mehrere `CALL`-Assemblyanweisungen zuordnen.  
  
 `pOffsets`  
 Ein Array systemeigener Offsets. Normalerweise enthält `pOffsets` einen einzelnen Offset, obwohl eine einzelne IL-Anweisung mehreren `CALL`-Assemblyanweisungen zugeordnet werden kann.  
  
## <a name="remarks"></a>Bemerkungen  
 Diese Methode wird zusammen mit der [ICorDebugILFrame3::GetReturnValueForILOffset-Methode](icordebugilframe3-getreturnvalueforiloffset-method.md) verwendet, um den Rückgabewert einer Methode abzusuchen, die einen Verweistyp zurückgibt. Durch die Übergabe eines IL-Offsets an eine Funktionsaufrufsite für diese Methode wird mindestens ein systemeigener Offset zurückgegeben. In diesem Fall kann der Debugger Haltepunkte für diese systemeigenen Offsets in der Funktion festlegen. Wenn der Debugger einen der Haltepunkte erreicht, können Sie denselben IL-Offset, den Sie an diese Methode übergeben haben, an die [ICorDebugILFrame3::GetReturnValueForILOffset-Methode](icordebugilframe3-getreturnvalueforiloffset-method.md) übergeben, um den Rückgabewert abzubekommen. Der Debugger sollte dann alle von ihm festgelegten Haltepunkte entfernen.  
  
> [!WARNING]
> Mit `ICorDebugCode3::GetReturnValueLiveOffset` den Methoden und [ICorDebugILFrame3::GetReturnValueForILOffset](icordebugilframe3-getreturnvalueforiloffset-method.md) können Sie Nur Rückgabewertinformationen für Referenztypen abrufen. Das Abrufen von Rückgabewertinformationen für Werttypen wird nicht unterstützt (alle Typen, die von <xref:System.ValueType> abgeleitet werden).  
  
 Die Funktion gibt die `HRESULT`-Werte zurück, die in der folgenden Tabelle dargestellt sind.  
  
|Wert vom Typ `HRESULT`|Beschreibung|  
|---------------------|-----------------|  
|`S_OK`|Erfolg.|  
|`CORDBG_E_INVALID_OPCODE`|Die angegebene IL-Offsetsite ist keine Aufrufanweisung, oder die Funktion gibt `void` zurück.|  
|`CORDBG_E_UNSUPPORTED`|Der angegebene IL-Offset ist ein richtiger Aufruf, der Rückgabetyp wird für das Abrufen eines Rückgabewerts nicht unterstützt.|  
  
 Die `ICorDebugCode3::GetReturnValueLiveOffset`-Methode ist nur auf x86- und AMD64-basierten Systemen verfügbar.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [GetReturnValueForILOffset-Methode](icordebugilframe3-getreturnvalueforiloffset-method.md)
- [ICorDebugCode3-Schnittstelle](icordebugcode3-interface.md)
