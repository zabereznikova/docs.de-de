---
title: LockClrVersion-Funktion
ms.date: 03/30/2017
api_name:
- LockClrVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- LockClrVersion
helpviewer_keywords:
- LockClrVersion function [.NET Framework hosting]
ms.assetid: 1318ee37-c43b-40eb-bbe8-88fc46453d74
topic_type:
- apiref
ms.openlocfilehash: 216852f8f051440b2814619b843a1f25013e4042
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133778"
---
# <a name="lockclrversion-function"></a>LockClrVersion-Funktion
Ermöglicht dem Host, zu bestimmen, welche Version des Common Language Runtime (CLR) innerhalb des Prozesses verwendet werden soll, bevor die CLR explizit initialisiert wird.  
  
 Diese Funktion wurde im .NET Framework 4 als veraltet markiert.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT LockClrVersion (  
    [in] FLockClrVersionCallback   hostCallback,  
    [in] FLockClrVersionCallback  *pBeginHostSetup,  
    [in] FLockClrVersionCallback  *pEndHostSetup  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `hostCallback`  
 in Die Funktion, die von der CLR bei der Initialisierung aufgerufen werden soll.  
  
 `pBeginHostSetup`  
 in Die Funktion, die vom Host aufgerufen werden soll, um die CLR darüber zu informieren, dass die Initialisierung gestartet wird.  
  
 `pEndHostSetup`  
 in Die Funktion, die vom Host aufgerufen werden soll, um die CLR darüber zu informieren, dass die Initialisierung beendet ist.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt neben den folgenden Werten Standard-COM-Fehlercodes zurück, die in WinError. h definiert sind.  
  
|Rückgabecode|Beschreibung|  
|-----------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|E_INVALIDARG|Mindestens eines der Argumente ist NULL.|  
  
## <a name="remarks"></a>Hinweise  
 Der Host ruft `LockClrVersion` vor dem Initialisieren der CLR auf. `LockClrVersion` benötigt drei Parameter, von denen alle Rückrufe des Typs [FLockClrVersionCallback](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md)sind. Dieser Typ wird wie folgt definiert.  
  
```cpp  
typedef HRESULT ( __stdcall *FLockClrVersionCallback ) ();  
```  
  
 Die folgenden Schritte erfolgen bei der Initialisierung der Laufzeit:  
  
1. Der Host ruft [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) oder eine der anderen Lauf Zeit Initialisierungs Funktionen auf. Alternativ kann der Host die Laufzeit mithilfe der COM-Objekt Aktivierung initialisieren.  
  
2. Die Laufzeit ruft die durch den `hostCallback`-Parameter angegebene Funktion auf.  
  
3. Die von `hostCallback` angegebene Funktion führt dann die folgende Sequenz von Aufrufen aus:  
  
    - Die Funktion, die durch den `pBeginHostSetup`-Parameter angegeben wird.  
  
    - `CorBindToRuntimeEx` (oder eine andere Lauf Zeit Initialisierungsfunktion).  
  
    - [ICLRRuntimeHost:: abgelegte Control](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md).  
  
    - [ICLRRuntimeHost:: Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md).  
  
    - Die Funktion, die durch den `pEndHostSetup`-Parameter angegeben wird.  
  
 Alle Aufrufe von `pBeginHostSetup` an `pEndHostSetup` müssen in einem einzelnen Thread oder einer Fiber mit demselben logischen Stapel erfolgen. Dieser Thread kann sich von dem Thread unterscheiden, für den `hostCallback` aufgerufen wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Mscoree. dll  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Veraltete CLR-Hostingfunktionen](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
