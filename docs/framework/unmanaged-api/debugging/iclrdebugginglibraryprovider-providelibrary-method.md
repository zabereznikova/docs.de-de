---
title: ICLRDebuggingLibraryProvider::ProvideLibrary-Methode
ms.date: 03/30/2017
api_name:
- ICLRDebuggingLibraryProvider.ProvideLibrary Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebuggingLibraryProvider::ProvideLibrary
helpviewer_keywords:
- ProvideLibrary method [.NET Framework debugging]
- ICLRDebuggingLibraryProvider::ProvideLibrary method [.NET Framework debugging]
ms.assetid: 86f06245-9517-49be-8d8c-ca5deaf34c02
topic_type:
- apiref
ms.openlocfilehash: 8fc2abd0728115edbbfae42958d8013029523ed1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73111365"
---
# <a name="iclrdebugginglibraryproviderprovidelibrary-method"></a>ICLRDebuggingLibraryProvider::ProvideLibrary-Methode

Ruft eine Bibliotheks Anbieter-Rückruf Schnittstelle ab, die es ermöglicht, Common Language Runtime (CLR) versionsspezifische Debugbibliotheken zu finden und bei Bedarf geladen zu werden.

## <a name="syntax"></a>Syntax

```cpp
HRESULT ProvideLibrary(
     [in] const WCHAR* pwszFileName,
     [in] DWORD dwTimestamp,
     [in] DWORD dwSizeOfImage,
     [out] HMODULE* hModule);
```

## <a name="parameters"></a>Parameter

`pwszFilename` \
in Der Name des Moduls, das angefordert wird.

`dwTimestamp` \
in Der Datums-/Uhrzeitstempel, der im COFF-Dateiheader von PE-Dateien gespeichert ist.

`pLibraryProvider` \
in Das `SizeOfImage` Feld, das in der optionalen COFF-Datei Kopfzeile von PE-Dateien gespeichert ist.

`hModule` \
vorgenommen Das Handle für das angeforderte Modul.

## <a name="return-value"></a>Rückgabewert

Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.

|HRESULT|Beschreibung|
|-------------|-----------------|
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|

## <a name="exceptions"></a>Ausnahmen

## <a name="remarks"></a>Hinweise

mit `ProvideLibrary` kann der Debugger Module bereitstellen, die zum Debuggen bestimmter CLR-Dateien wie mscordbi. dll und mscordacwert. dll erforderlich sind. Die Modul Handles müssen gültig bleiben, bis ein Aufruf der [ICLRDebugging:: CanUnloadNow](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-canunloadnow-method.md) -Methode anzeigt, dass Sie freigegeben werden können. an diesem Punkt ist es die Aufgabe des Aufrufers, die Handles freizugeben.

Der Debugger kann beliebige verfügbare Mittel verwenden, um das Debug-Modul zu suchen oder zu beschaffen.

> [!IMPORTANT]
> Diese Funktion ermöglicht es dem API-Aufrufer, Module bereitzustellen, die ausführbare und möglicherweise bösartigen Code enthalten. Als Sicherheitsmaßnahme sollte der Aufrufer nicht `ProvideLibrary` verwenden, um Code zu verteilen, der nicht für die Selbstausführung bereit ist.
>
> Wenn in einer bereits veröffentlichten Bibliothek, wie z. b. mscordbi. dll oder mscordacwks. dll, ein schwerwiegendes Sicherheitsproblem entdeckt wird, kann das Shim gepatcht werden, um die ungültigen Versionen der Dateien zu erkennen. Der Shim kann dann Anforderungen für die gepatchten Versionen der Dateien ausgeben und die ungültigen Versionen ablehnen, wenn Sie als Antwort auf eine Anforderung bereitgestellt werden. Dies kann nur auftreten, wenn der Benutzer auf eine neue Version des Shims gepatcht hat. Nicht gepatchte Versionen bleiben anfällig.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).

**Header:** CorDebug.idl, CorDebug.h

**Bibliothek:** CorGuids.lib

**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]

## <a name="see-also"></a>Siehe auch

- [Debuggen von Schnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
