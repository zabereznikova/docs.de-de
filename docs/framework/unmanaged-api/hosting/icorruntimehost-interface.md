---
title: ICorRuntimeHost-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost
helpviewer_keywords:
- ICorRuntimeHost interface [.NET Framework hosting]
ms.assetid: 4369533d-7834-4497-bc37-bfea0ad737b1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: facc756061e7eb381abecc544ca4b15bfdde6343
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440046"
---
# <a name="icorruntimehost-interface"></a>ICorRuntimeHost-Schnittstelle
Enthält Methoden, mit denen der Host zum Starten und beenden die common Language Runtime (CLR) explizit erstellen und Konfigurieren von Anwendungsdomänen, die auf die Standarddomäne zugreifen und zum Aufzählen aller Domänen im Prozess ausgeführt.  
  
 In .NET Framework, Version 2.0, ist diese Schnittstelle vom ersetzt [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md).  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[CloseEnum-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-closeenum-method.md)|Setzt einen Domänenenumerator wieder an den Anfang der Domänenliste aus.|  
|[CreateDomain-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md)|Erstellt eine Anwendungsdomäne. Der Aufrufer empfängt einen Schnittstellenzeiger vom Typ <xref:System._AppDomain> mit einer Instanz des Typs <xref:System.AppDomain?displayProperty=nameWithType>.|  
|[CreateDomainEx-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md)|Erstellt eine Anwendungsdomäne. Diese Methode ermöglicht den Aufrufer die Übergabe einer IAppDomainSetup-Instanz so konfigurieren zusätzliche Funktionen des zurückgegebenen <xref:System._AppDomain> Instanz.|  
|[CreateDomainSetup-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainsetup-method.md)|Ruft einen Schnittstellenzeiger vom Typ `IAppDomainSetup` auf eine <xref:System.AppDomainSetup> Instanz. `IAppDomainSetup` Stellt Methoden zum Konfigurieren der Aspekte einer Anwendungsdomäne vor Erstellung.|  
|[CreateEvidence-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md)|Ruft einen Schnittstellenzeiger vom Typ <xref:System.Security.Principal.IIdentity>, dadurch wird den Host für die Übergabe an den Sicherheitsbeweis erstellen [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) oder [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md).|  
|[CreateLogicalThreadState-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createlogicalthreadstate-method.md)|Nicht verwenden.|  
|[CurrentDomain-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-currentdomain-method.md)|Ruft einen Schnittstellenzeiger vom Typ <xref:System._AppDomain> , die die Domäne geladen wird, für den aktuellen Thread darstellt.|  
|[DeleteLogicalThreadState-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-deletelogicalthreadstate-method.md)|Nicht verwenden.|  
|[EnumDomains-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md)|Ruft einen Enumerator für die Domänen im aktuellen Prozess ab.|  
|[GetConfiguration-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-getconfiguration-method.md)|Ruft ein Objekt, das den Host an, die Rückrufkonfiguration der CLR ermöglicht.|  
|[GetDefaultDomain-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-getdefaultdomain-method.md)|Ruft einen Schnittstellenzeiger vom Typ <xref:System._AppDomain> , die die Standarddomäne für den aktuellen Prozess darstellt.|  
|[LocksHeldByLogicalThread-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-locksheldbylogicalthread-method.md)|Nicht verwenden.|  
|[MapFile-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-mapfile-method.md)|Ordnet die angegebene Datei in den Arbeitsspeicher an. Diese Methode ist veraltet.|  
|[NextDomain-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-nextdomain-method.md)|Ruft einen Schnittstellenzeiger auf die nächste Domäne in der Enumeration.|  
|[Start-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-start-method.md)|Startet die CLR.|  
|[Stop-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-stop-method.md)|Beendet die Ausführung von Code in der Common Language Runtime für den aktuellen Prozess an.|  
|[SwitchInLogicalThreadState-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-switchinlogicalthreadstate-method.md)|Nicht verwenden.|  
|[SwitchOutLogicalThreadState-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-switchoutlogicalthreadstate-method.md)|Nicht verwenden.|  
|[UnloadDomain-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-unloaddomain-method.md)|Entlädt die angegebene Anwendungsdomäne vom aktuellen Prozess an.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** 1.0, 1.1  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.AppDomain>  
 [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 [ICLRRuntimeHost-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)  
 [Laufzeithosts](http://msdn.microsoft.com/library/99d9246a-b994-4fe5-985c-8588d1d59998)  
 [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [CorRuntimeHost-Co-Klasse](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
