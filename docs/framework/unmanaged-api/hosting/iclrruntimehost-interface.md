---
title: ICLRRuntimeHost-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost
helpviewer_keywords:
- ICLRRuntimeHost interface [.NET Framework hosting]
ms.assetid: cb0c5f65-3791-47bc-b833-2f84f4101ba5
topic_type:
- apiref
ms.openlocfilehash: 8d88222215eb31e1c63f3b26079517c4b088e81b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728835"
---
# <a name="iclrruntimehost-interface"></a>ICLRRuntimeHost-Schnittstelle

Bietet ähnliche Funktionen wie die [ICorRuntimeHost](icorruntimehost-interface.md) -Schnittstelle, die in der .NET Framework Version 1 bereitgestellt wurde, mit den folgenden Änderungen:  
  
- Das Hinzufügen der [SetHostControl](iclrruntimehost-sethostcontrol-method.md) -Methode zum Festlegen der Host Steuerelement-Schnittstelle.  
  
- Das Weglassen einiger Methoden, die von bereitgestellt werden `ICorRuntimeHost` .  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[ExecuteApplication-Methode](iclrruntimehost-executeapplication-method.md)|Wird in Manifest-basierten ClickOnce-Bereitstellungs Szenarien verwendet, um die Anwendung anzugeben, die in einer neuen Domäne aktiviert werden soll.|  
|[ExecuteInAppDomain-Methode](iclrruntimehost-executeinappdomain-method.md)|Gibt den an, <xref:System.AppDomain> in dem der angegebene verwaltete Code ausgeführt werden soll.|  
|[ExecuteInDefaultAppDomain-Methode](iclrruntimehost-executeindefaultappdomain-method.md)|Ruft die angegebene Methode des angegebenen Typs in der angegebenen Assembly auf.|  
|[GetCLRControl-Methode](iclrruntimehost-getclrcontrol-method.md)|Ruft einen Schnittstellen Zeiger vom Typ [ICLRControl](iclrcontrol-interface.md) ab, den Hosts zum Anpassen der Aspekte des Common Language Runtime (CLR) verwenden können.|  
|[GetCurrentAppDomainId-Methode](iclrruntimehost-getcurrentappdomainid-method.md)|Ruft den numerischen Bezeichner der ab <xref:System.AppDomain> , die gerade ausgeführt wird.|  
|[SetHostControl-Methode](iclrruntimehost-sethostcontrol-method.md)|Legt die Schnittstelle des Host Steuer Elements fest. Sie müssen aufrufen, `SetHostControl` bevor Sie aufrufen `Start` .|  
|[Start-Methode](iclrruntimehost-start-method.md)|Initialisiert die CLR in einen Prozess.|  
|[Stop-Methode](iclrruntimehost-stop-method.md)|Beendet die Ausführung des Codes durch die Laufzeit.|  
|[UnloadAppDomain-Methode](iclrruntimehost-unloadappdomain-method.md)|Entlädt das <xref:System.AppDomain> , das dem angegebenen numerischen Bezeichner entspricht.|  
  
## <a name="remarks"></a>Hinweise  

 Beginnen Sie mit der .NET Framework 4, indem Sie die [ICLRMetaHost](iclrmetahost-interface.md) -Schnittstelle verwenden, um einen Zeiger auf die [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) -Schnittstelle zu erhalten, und dann die [ICLRRuntimeInfo:: GetInterface](iclrruntimeinfo-getinterface-method.md) -Methode aufrufen, um einen Zeiger auf zu erhalten `ICLRRuntimeHost` . In früheren Versionen der .NET Framework erhält der Host einen Zeiger auf eine `ICLRRuntimeHost` Instanz durch Aufrufen von [corbindtor untimeex](corbindtoruntimeex-function.md) oder [CorBindToCurrentRuntime](corbindtocurrentruntime-function.md). Zum Bereitstellen von Implementierungen der Technologien, die in der .NET Framework Version 2,0 bereitgestellt werden, müssen Sie `ICLRRuntimeHost` anstelle von verwenden `ICorRuntimeHost` .  
  
> [!IMPORTANT]
> Rufen Sie die [Start](iclrruntimehost-start-method.md) -Methode nicht auf, bevor Sie die [ExecuteApplication](iclrruntimehost-executeapplication-method.md) -Methode aufrufen, um eine Manifest-basierte Anwendung zu aktivieren. Wenn die- `Start` Methode zuerst aufgerufen wird, kann der `ExecuteApplication` Methodenaufruf nicht ausgeführt werden.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- [CorBindToCurrentRuntime-Funktion](corbindtocurrentruntime-function.md)
- [CorBindToRuntimeEx-Funktion](corbindtoruntimeex-function.md)
- [ICLRControl-Schnittstelle](iclrcontrol-interface.md)
- [ICorRuntimeHost-Schnittstelle](icorruntimehost-interface.md)
- [Hosten von Schnittstellen](hosting-interfaces.md)
- [CLRRuntimeHost-Co-Klasse](clrruntimehost-coclass.md)
