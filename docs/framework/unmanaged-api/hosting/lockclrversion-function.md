---
title: LockClrVersion-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: LockClrVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: LockClrVersion
helpviewer_keywords: LockClrVersion function [.NET Framework hosting]
ms.assetid: 1318ee37-c43b-40eb-bbe8-88fc46453d74
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: be41ae47f78a41e2f2be10a1e38d938dde9a4701
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="lockclrversion-function"></a>LockClrVersion-Funktion
Ermöglicht den Host kann bestimmen, welche Version der common Language Runtime (CLR) innerhalb des Prozesses verwendet werden soll, bevor die CLR explizit initialisiert wird.  
  
 Diese Funktion ist in [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] veraltet.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT LockClrVersion (  
    [in] FLockClrVersionCallback   hostCallback,  
    [in] FLockClrVersionCallback  *pBeginHostSetup,  
    [in] FLockClrVersionCallback  *pEndHostSetup  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `hostCallback`  
 [in] Die Funktion, die von der CLR bei der Initialisierung aufgerufen werden.  
  
 `pBeginHostSetup`  
 [in] Die Funktion, die vom Host der CLR zu informieren, dass die Initialisierung aufgerufen werden, wird gestartet.  
  
 `pEndHostSetup`  
 [in] Die Funktion, die vom Host der CLR zu informieren, dass die Initialisierung aufgerufen werden, ist abgeschlossen.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt COM-Standardfehlercodes in WinError.h definiert, zusätzlich zu den folgenden Werten zurück.  
  
|Rückgabecode|Beschreibung|  
|-----------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|E_INVALIDARG|Eine oder mehrere der Argumente ist null.|  
  
## <a name="remarks"></a>Hinweise  
 Der Host ruft `LockClrVersion` vor dem Initialisieren der CLR. `LockClrVersion`akzeptiert drei Parameter, die Rückrufe vom Typ sind [FLockClrVersionCallback](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md). Dieser Typ ist wie folgt definiert.  
  
```  
typedef HRESULT ( __stdcall *FLockClrVersionCallback ) ();  
```  
  
 Die folgenden Schritte erfolgen bei der Initialisierung der Runtime:  
  
1.  Der Host ruft [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) oder einer anderen Laufzeit Initialization Funktionen. Alternativ konnte den Host die Laufzeit unter Verwendung der Aktivierung von COM-Objekt zu initialisieren.  
  
2.  Die Laufzeit ruft die Funktion, die gemäß der `hostCallback` Parameter.  
  
3.  Die Funktion anhand des `hostCallback` dann wird die folgende Sequenz von aufrufen:  
  
    -   Die angegebene Funktion die `pBeginHostSetup` Parameter.  
  
    -   `CorBindToRuntimeEx`(oder eine andere Funktion der Common Language Runtime-Initialisierung).  
  
    -   [ICLRRuntimeHost:: SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md).  
  
    -   [ICLRRuntimeHost:: Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md).  
  
    -   Die angegebene Funktion die `pEndHostSetup` Parameter.  
  
 Alle Aufrufe von `pBeginHostSetup` auf `pEndHostSetup` muss auf einem einzigen Thread oder Fiber mit demselben logischen Stapel erfolgen. Dieser Thread kann anderen als den Thread auf dem `hostCallback` aufgerufen wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** "Mscoree.dll"  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Veraltete CLR-Hostingfunktionen](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
