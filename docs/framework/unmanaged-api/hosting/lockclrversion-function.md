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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 95f61170d401161dcf217f139dbe6e4c6d3a0e0c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54735038"
---
# <a name="lockclrversion-function"></a>LockClrVersion-Funktion
Ermöglicht dem Host, um zu bestimmen, welche Version der common Language Runtime (CLR) innerhalb des Prozesses verwendet werden soll, bevor die CLR explizit initialisiert wird.  
  
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
 [in] Die Funktion, die durch den Host aus, um die CLR darüber zu informieren, dass die Initialisierung aufgerufen werden, wird gestartet.  
  
 `pEndHostSetup`  
 [in] Die Funktion, die durch den Host aus, um die CLR darüber zu informieren, dass die Initialisierung aufgerufen werden, ist abgeschlossen.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die standard-COM-Fehlercodes, zurück, wie in "Winerror.h", zusätzlich zu den folgenden Werten definiert.  
  
|Rückgabecode|Beschreibung|  
|-----------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|E_INVALIDARG|Eine oder mehrere der Argumente ist null.|  
  
## <a name="remarks"></a>Hinweise  
 Der Host ruft `LockClrVersion` vor der Initialisierung der CLR. `LockClrVersion` akzeptiert drei Parameter, die alle Rückrufe vom Typ sind [FLockClrVersionCallback](../../../../docs/framework/unmanaged-api/hosting/flockclrversioncallback-function-pointer.md). Dieser Typ ist wie folgt definiert.  
  
```  
typedef HRESULT ( __stdcall *FLockClrVersionCallback ) ();  
```  
  
 Die folgenden Schritte werden bei der Initialisierung der Runtime:  
  
1.  Der Host ruft [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) oder eine der anderen Initialisierungsfunktionen Common Language Runtime. Sie können auch konnte der Host die Laufzeit mithilfe von COM-objektaktivierung initialisiert werden.  
  
2.  Ruft die Runtime die Funktion, die anhand der `hostCallback` Parameter.  
  
3.  Die Funktion anhand des `hostCallback` macht anschließend die folgende Sequenz von aufrufen:  
  
    -   Die Funktion, die anhand der `pBeginHostSetup` Parameter.  
  
    -   `CorBindToRuntimeEx` (oder eine andere Funktion der Common Language Runtime-Initialisierung).  
  
    -   [ICLRRuntimeHost::SetHostControl](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-sethostcontrol-method.md).  
  
    -   [ICLRRuntimeHost::Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md).  
  
    -   Die Funktion, die anhand der `pEndHostSetup` Parameter.  
  
 Alle Aufrufe von `pBeginHostSetup` zu `pEndHostSetup` muss auf einem einzelnen Thread oder eine Fiber mit demselben logischen Stapel auftreten. Dieser Thread kann aus dem Thread, von denen unterscheiden `hostCallback` aufgerufen wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** MSCorEE.dll  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
- [Veraltete CLR-Hostingfunktionen](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
