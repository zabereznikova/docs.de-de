---
title: ICLRMetaHost::GetRuntime-Methode
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.GetRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::GetRuntime
helpviewer_keywords:
- GetRuntime method [.NET Framework hosting]
- ICLRMetaHost::GetRuntime method [.NET Framework hosting]
ms.assetid: a10749f1-ab91-47cf-982f-d8ccd2e81bd2
topic_type:
- apiref
ms.openlocfilehash: d482e25c7bf0f028e2478c8e7b7863bc54d7aeb9
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504192"
---
# <a name="iclrmetahostgetruntime-method"></a>ICLRMetaHost::GetRuntime-Methode
Ruft die [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) -Schnittstelle ab, die einer bestimmten Version des Common Language Runtime (CLR) entspricht. Diese Methode ersetzt die [CorBindToRuntimeEx](corbindtoruntimeex-function.md) -Funktion, die mit dem [STARTUP_LOADER_SAFEMODE](startup-flags-enumeration.md) -Flag verwendet wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT GetRuntime (  
    [in] LPCWSTR pwzVersion,  
    [in] REFIID riid,  
    [out,iid_is(riid), retval] LPVOID *ppRuntime  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pwzVersion`  
 in Die in den Metadaten gespeicherte .NET Framework Kompilierungs Version im Format "v*A*. *B*[.* X*] ". *A*, *B*und *X* sind Dezimalzahlen, die der Hauptversion, der neben Version und der Buildnummer entsprechen.  
  
> [!NOTE]
> Dieser Parameter muss dem Verzeichnisnamen für die .NET Framework Version entsprechen, wie er unter "c:\WINDOWS\Microsoft.NET\Framework" oder "c:\WINDOWS\Microsoft.NET\Framework64." angezeigt wird.  
  
 Beispiel Werte sind "v 1.0.3705", "v 1.1.4322", "v 2.0.50727" und "v 4.0". *X*", wobei *x* von der installierten Buildnummer abhängig ist. Das Präfix "v" ist erforderlich.  
  
 `riid`  
 in Der Bezeichner für die gewünschte Schnittstelle. Derzeit ist der einzige gültige Wert für diesen Parameter IID_ICLRRuntimeInfo.  
  
 `ppRuntime`  
 vorgenommen Ein Zeiger auf die [iclrruntimeingefo](iclrruntimeinfo-interface.md) -Schnittstelle, die der angeforderten Laufzeit entspricht.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|BESCHREIBUNG|  
|-------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|E_POINTER|`pwzVersion` oder `ppRuntime` ist NULL.|  
  
## <a name="remarks"></a>Bemerkungen  
 Diese Methode interagiert konsistent mit Legacy Schnittstellen, wie z. b. der [ICorRuntimeHost](icorruntimehost-interface.md) -Schnittstelle, und Legacy Funktionen wie den veralteten `CorBindTo*` Funktionen (siehe [Veraltete CLR-Hostingfunktionen](deprecated-clr-hosting-functions.md) in der .NET Framework 2,0-Hosting-API). Das heißt, Laufzeiten, die mit der Legacy-API geladen werden, sind für die neue API sichtbar, und Laufzeiten, die mit der neuen API geladen werden, sind für die Legacy-API sichtbar.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** MetaHost. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen:

- [ICLRMetaHost-Schnittstelle](iclrmetahost-interface.md)
- [Veraltete CLR-Hostingschnittstellen und Co-Klassen](deprecated-clr-hosting-interfaces-and-coclasses.md)
- [CLR-Hostingschnittstellen](clr-hosting-interfaces.md)
- [Veraltete CLR-Hostingfunktionen](deprecated-clr-hosting-functions.md)
- [Hosting](index.md)
