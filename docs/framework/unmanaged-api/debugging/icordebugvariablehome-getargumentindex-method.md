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
ms.openlocfilehash: 27a676fd1d2d7903943e44f8a7201b88af4fba89
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396995"
---
# <a name="icordebugvariablehomegetargumentindex-method"></a>Icordebugvariablehome:: getargumentindex-Methode

Ruft den Index eines Funktionsarguments ab.

## <a name="syntax"></a>Syntax

```cpp
HRESULT GetArgumentIndex(
    [out] ULONG32* pArgumentIndex
);
```

## <a name="parameters"></a>Parameter

`pArgumentIndex`\
vorgenommen Ein Zeiger auf den Argument index.

## <a name="return-value"></a>Rückgabewert

Die-Methode gibt die folgenden Werte zurück.

|Wert|Beschreibung|
|-----------|-----------------|
|`S_OK`|Der Methodenaufrufe hat einen gültigen Argument Index zurückgegeben.|
|`E_FAIL`|Die aktuelle [icorentbugvariablehome](icordebugvariablehome-interface.md) -Instanz stellt eine lokale Variable dar.|

## <a name="remarks"></a>Bemerkungen

Der Argument Index kann zum Abrufen von Metadaten für dieses Argument verwendet werden.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).

**Header:** CorDebug.idl, CorDebug.h

**Bibliothek:** CorGuids.lib

**.NET Framework Versionen:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]

## <a name="see-also"></a>Siehe auch

- [ICorDebugVariableHome-Schnittstelle](icordebugvariablehome-interface.md)
