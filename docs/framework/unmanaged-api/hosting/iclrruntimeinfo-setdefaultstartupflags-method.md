---
title: ICLRRuntimeInfo::SetDefaultStartupFlags-Methode
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.SetDefaultStartupFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::SetDefaultStartupFlags
helpviewer_keywords:
- ICLRRuntimeInfo::SetDefaultStartupFlags method [.NET Framework hosting]
- SetDefaultStartupFlags method [.NET Framework hosting]
ms.assetid: 98ae174f-bff0-48f1-9e05-6cb63b451824
topic_type:
- apiref
ms.openlocfilehash: aa02d42511a863434fef236f90afae2c5417a78d
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504016"
---
# <a name="iclrruntimeinfosetdefaultstartupflags-method"></a>ICLRRuntimeInfo::SetDefaultStartupFlags-Methode
Legt die startflags und die Host Konfigurationsdatei fest, die zum Starten der Laufzeit verwendet werden. Diese Methode ersetzt die Verwendung des `startupFlags` -Parameters in den [CorBindToRuntimeEx](corbindtoruntimeex-function.md) -und [CorBindToRuntimeHost](corbindtoruntimehost-function.md) -Funktionen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT SetDefaultStartupFlags(  
           [in]  DWORD dwStartupFlags,  
           [in]  LPCWSTR pwzHostConfigFile);  
```  
  
## <a name="parameters"></a>Parameter  
 `dwStartupFlags`  
 in Die festzulegenden hoststartflags. Verwenden Sie die gleichen Flags wie die [CorBindToRuntimeEx](corbindtoruntimeex-function.md) -Funktion und die [CorBindToRuntimeHost](corbindtoruntimehost-function.md) -Funktion.  
  
 `pwzHostConfigFile`  
 in Der Verzeichnispfad der festzulegenden Host Konfigurationsdatei.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULT-und HRESULT-Fehler zurück, die auf Methoden Fehler hinweisen.  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
  
## <a name="remarks"></a>Bemerkungen  
 Ein Multithread-Host sollte Aufrufe dieser Methode synchronisieren. Andernfalls ruft Thread A möglicherweise die `SetStartupFlags` -Methode auf, nachdem Thread b einen-Aufrufvorgang abgeschlossen hat `SetStartupFlags` und bevor Thread b die Laufzeit startet.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** MetaHost. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [ICLRRuntimeInfo-Schnittstelle](iclrruntimeinfo-interface.md)
- [Hosten von Schnittstellen](hosting-interfaces.md)
- [Hosting](index.md)
