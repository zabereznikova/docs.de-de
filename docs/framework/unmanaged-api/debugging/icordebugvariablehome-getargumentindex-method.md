---
title: 'Icordebugvariablehome:: getargumentindex-Methode'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetArgumentIndex
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetArgumentIndex
helpviewer_keywords:
- ICorDebugVariableHome::GetArgumentIndex method [.NET Framework debugging]
- GetArgumentIndex method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: e86fcc72-388d-4009-ab21-8f9c3323e9a3
topic_type:
- apiref
ms.openlocfilehash: 12d4e63480f03bfad613f30362ddaeaf12b57a88
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791051"
---
# <a name="icordebugvariablehomegetargumentindex-method"></a>Icordebugvariablehome:: getargumentindex-Methode

Ruft den Index eines Funktionsarguments ab.

## <a name="syntax"></a>Syntax

```cpp
HRESULT GetArgumentIndex(
    [out] ULONG32* pArgumentIndex
);
```

## <a name="parameters"></a>Parameters

`pArgumentIndex`\
vorgenommen Ein Zeiger auf den Argument index.

## <a name="return-value"></a>Rückgabewert

Die-Methode gibt die folgenden Werte zurück.

|{2&gt;Wert&lt;2}|Beschreibung|
|-----------|-----------------|
|`S_OK`|Der Methodenaufrufe hat einen gültigen Argument Index zurückgegeben.|
|`E_FAIL`|Die aktuelle [icorentbugvariablehome](icordebugvariablehome-interface.md) -Instanz stellt eine lokale Variable dar.|

## <a name="remarks"></a>Hinweise

Der Argument Index kann zum Abrufen von Metadaten für dieses Argument verwendet werden.

## <a name="requirements"></a>-Anforderungen

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).

**Header:** CorDebug.idl, CorDebug.h

**Bibliothek:** CorGuids.lib

**.NET Framework Versionen:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]

## <a name="see-also"></a>Siehe auch

- [ICorDebugVariableHome-Schnittstelle](icordebugvariablehome-interface.md)
