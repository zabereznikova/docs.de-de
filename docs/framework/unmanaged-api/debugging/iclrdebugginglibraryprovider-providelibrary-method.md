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
ms.openlocfilehash: 7bbb49dc6ee9b1d29dd61ccdcfdacb62740133ed
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860264"
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

|HRESULT|BESCHREIBUNG|
|-------------|-----------------|
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|

## <a name="exceptions"></a>Ausnahmen

## <a name="remarks"></a>Hinweise

`ProvideLibrary`ermöglicht es dem Debugger, Module bereitzustellen, die zum Debuggen bestimmter CLR-Dateien wie mscordbi. dll und mscordacwert. dll erforderlich sind. Die Modul Handles müssen gültig bleiben, bis ein Aufruf der [ICLRDebugging:: CanUnloadNow](iclrdebugging-canunloadnow-method.md) -Methode anzeigt, dass Sie freigegeben werden können. an diesem Punkt ist es die Aufgabe des Aufrufers, die Handles freizugeben.

Der Debugger kann beliebige verfügbare Mittel verwenden, um das Debug-Modul zu suchen oder zu beschaffen.

> [!IMPORTANT]
> Diese Funktion ermöglicht es dem API-Aufrufer, Module bereitzustellen, die ausführbare und möglicherweise bösartigen Code enthalten. Als Sicherheitsmaßnahme sollte der Aufrufer nicht verwenden `ProvideLibrary` , um Code zu verteilen, der nicht für die Selbstausführung bereit ist.
>
> Wenn in einer bereits veröffentlichten Bibliothek, wie z. b. mscordbi. dll oder mscordacwks. dll, ein schwerwiegendes Sicherheitsproblem entdeckt wird, kann das Shim gepatcht werden, um die ungültigen Versionen der Dateien zu erkennen. Der Shim kann dann Anforderungen für die gepatchten Versionen der Dateien ausgeben und die ungültigen Versionen ablehnen, wenn Sie als Antwort auf eine Anforderung bereitgestellt werden. Dies kann nur auftreten, wenn der Benutzer auf eine neue Version des Shims gepatcht hat. Nicht gepatchte Versionen bleiben anfällig.

## <a name="requirements"></a>Anforderungen

**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).

**Header:** CorDebug.idl, CorDebug.h

**Bibliothek:** CorGuids.lib

**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]

## <a name="see-also"></a>Weitere Informationen:

- [Debugschnittstellen](debugging-interfaces.md)
- [Debuggen](index.md)
