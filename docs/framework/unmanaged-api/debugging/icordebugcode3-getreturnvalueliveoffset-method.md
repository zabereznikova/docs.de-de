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
ms.openlocfilehash: 2cb4c79601061ab8473d6d7ca50c4ed2f92b01c4
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82893429"
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
  
## <a name="remarks"></a>Hinweise  
 Diese Methode wird zusammen mit der [ICorDebugILFrame3:: getreturnvalueforiloffset](icordebugilframe3-getreturnvalueforiloffset-method.md) -Methode verwendet, um den Rückgabewert einer Methode, die einen Verweistyp zurückgibt, zu erhalten. Durch die Übergabe eines IL-Offsets an eine Funktionsaufrufsite für diese Methode wird mindestens ein systemeigener Offset zurückgegeben. In diesem Fall kann der Debugger Haltepunkte für diese systemeigenen Offsets in der Funktion festlegen. Wenn der Debugger auf einen der Breakpoints trifft, können Sie denselben IL-Offset übergeben, den Sie an diese Methode übergeben haben, an die [ICorDebugILFrame3:: getreturnvalueforiloffset](icordebugilframe3-getreturnvalueforiloffset-method.md) -Methode, um den Rückgabewert zu erhalten. Der Debugger sollte dann alle von ihm festgelegten Haltepunkte entfernen.  
  
> [!WARNING]
> Die `ICorDebugCode3::GetReturnValueLiveOffset` -Methode und die [ICorDebugILFrame3:: getreturnvalueforiloffset](icordebugilframe3-getreturnvalueforiloffset-method.md) -Methode ermöglichen es Ihnen, Rückgabewert Informationen nur für Verweis Typen zu erhalten. Das Abrufen von Rückgabewertinformationen für Werttypen wird nicht unterstützt (alle Typen, die von <xref:System.ValueType> abgeleitet werden).  
  
 Die Funktion gibt die `HRESULT`-Werte zurück, die in der folgenden Tabelle dargestellt sind.  
  
|`HRESULT`-Wert|Beschreibung|  
|---------------------|-----------------|  
|`S_OK`|Erfolg.|  
|`CORDBG_E_INVALID_OPCODE`|Die angegebene IL-Offsetsite ist keine Aufrufanweisung, oder die Funktion gibt `void` zurück.|  
|`CORDBG_E_UNSUPPORTED`|Der angegebene IL-Offset ist ein richtiger Aufruf, der Rückgabetyp wird für das Abrufen eines Rückgabewerts nicht unterstützt.|  
  
 Die `ICorDebugCode3::GetReturnValueLiveOffset`-Methode ist nur auf x86- und AMD64-basierten Systemen verfügbar.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [GetReturnValueForILOffset-Methode](icordebugilframe3-getreturnvalueforiloffset-method.md)
- [ICorDebugCode3-Schnittstelle](icordebugcode3-interface.md)
