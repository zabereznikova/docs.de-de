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
ms.openlocfilehash: 09bcebfdcfea3d5728d404cdb6b5fb170a5432c3
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008494"
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
  
|Rückgabecode|BESCHREIBUNG|  
|-----------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|E_INVALIDARG|Mindestens eines der Argumente ist NULL.|  
  
## <a name="remarks"></a>Hinweise  
 Der Host ruft auf, `LockClrVersion` bevor die CLR initialisiert wird. `LockClrVersion`erfordert drei Parameter, von denen alle Rückrufe des Typs [FLockClrVersionCallback](flockclrversioncallback-function-pointer.md)sind. Dieser Typ wird wie folgt definiert.  
  
```cpp  
typedef HRESULT ( __stdcall *FLockClrVersionCallback ) ();  
```  
  
 Die folgenden Schritte erfolgen bei der Initialisierung der Laufzeit:  
  
1. Der Host ruft [CorBindToRuntimeEx](corbindtoruntimeex-function.md) oder eine der anderen Lauf Zeit Initialisierungs Funktionen auf. Alternativ kann der Host die Laufzeit mithilfe der COM-Objekt Aktivierung initialisieren.  
  
2. Die Laufzeit ruft die durch den-Parameter angegebene Funktion auf `hostCallback` .  
  
3. Die von angegebene Funktion `hostCallback` führt dann die folgende Sequenz von Aufrufen aus:  
  
    - Die Funktion, die durch den-Parameter angegeben wird `pBeginHostSetup` .  
  
    - `CorBindToRuntimeEx`(oder eine andere Lauf Zeit Initialisierungsfunktion).  
  
    - [ICLRRuntimeHost:: abgelegte Control](iclrruntimehost-sethostcontrol-method.md).  
  
    - [ICLRRuntimeHost:: Start](iclrruntimehost-start-method.md).  
  
    - Die Funktion, die durch den-Parameter angegeben wird `pEndHostSetup` .  
  
 Alle Aufrufe von `pBeginHostSetup` bis `pEndHostSetup` müssen in einem einzelnen Thread oder einer Fiber mit demselben logischen Stapel erfolgen. Dieser Thread kann sich von dem Thread unterscheiden, bei dem `hostCallback` aufgerufen wird.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Mscoree. dll  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [Veraltete CLR-Hostingfunktionen](deprecated-clr-hosting-functions.md)
