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
ms.openlocfilehash: ec893c898a6cd4abffd525056ed0d0169fcbb288
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59184781"
---
# <a name="icorruntimehost-interface"></a>ICorRuntimeHost-Schnittstelle
Bietet Methoden, mit denen der Host zum Starten und beenden die common Language Runtime (CLR) explizit zum Erstellen und Konfigurieren von Anwendungsdomänen, die Zugriff auf die Standarddomäne und zum Aufzählen von allen Domänen, die im Prozess ausgeführt wird.  
  
 In .NET Framework, Version 2.0, ist diese Schnittstelle durch ersetzt [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md).  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[CloseEnum-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-closeenum-method.md)|Setzt einen Domänenenumerator wieder an den Anfang der Domänenliste aus.|  
|[CreateDomain-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md)|Erstellt eine Anwendungsdomäne. Der Aufrufer empfängt einen Schnittstellenzeiger vom Typ <xref:System._AppDomain> in eine Instanz des Typs <xref:System.AppDomain?displayProperty=nameWithType>.|  
|[CreateDomainEx-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md)|Erstellt eine Anwendungsdomäne. Diese Methode ermöglicht den Aufrufer die Übergabe einer IAppDomainSetup-Instanz zum Konfigurieren der zusätzlichen Features des zurückgegebenen <xref:System._AppDomain> Instanz.|  
|[CreateDomainSetup-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainsetup-method.md)|Ruft einen Schnittstellenzeiger vom Typ `IAppDomainSetup` auf eine <xref:System.AppDomainSetup> Instanz. `IAppDomainSetup` Stellt Methoden zum Aspekte einer Anwendungsdomäne zu konfigurieren, bevor es erstellt wird.|  
|[CreateEvidence-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md)|Ruft einen Schnittstellenzeiger vom Typ <xref:System.Security.Principal.IIdentity>, wodurch den Host Sicherheitsbeweis Übergabe an erstellen [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) oder [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md).|  
|[CreateLogicalThreadState-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createlogicalthreadstate-method.md)|Nicht verwenden.|  
|[CurrentDomain-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-currentdomain-method.md)|Ruft einen Schnittstellenzeiger vom Typ <xref:System._AppDomain> , das die Domäne geladen werden, für den aktuellen Thread darstellt.|  
|[DeleteLogicalThreadState-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-deletelogicalthreadstate-method.md)|Nicht verwenden.|  
|[EnumDomains-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md)|Ruft einen Enumerator für die Domänen im aktuellen Prozess ab.|  
|[GetConfiguration-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-getconfiguration-method.md)|Ruft ein Objekt, das den Host Geben Sie die Rückrufkonfiguration, der die CLR ermöglicht.|  
|[GetDefaultDomain-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-getdefaultdomain-method.md)|Ruft einen Schnittstellenzeiger vom Typ <xref:System._AppDomain> , die die Standarddomäne für den aktuellen Prozess darstellt.|  
|[LocksHeldByLogicalThread-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-locksheldbylogicalthread-method.md)|Nicht verwenden.|  
|[MapFile-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-mapfile-method.md)|Ordnet die angegebene Datei in den Arbeitsspeicher an. Diese Methode ist veraltet.|  
|[NextDomain-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-nextdomain-method.md)|Ruft einen Schnittstellenzeiger auf die nächste Domäne in der Enumeration.|  
|[Start-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-start-method.md)|Startet die CLR.|  
|[Stop-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-stop-method.md)|Beendet die Ausführung von Code in der Runtime für den aktuellen Prozess an.|  
|[SwitchInLogicalThreadState-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-switchinlogicalthreadstate-method.md)|Nicht verwenden.|  
|[SwitchOutLogicalThreadState-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-switchoutlogicalthreadstate-method.md)|Nicht verwenden.|  
|[UnloadDomain-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-unloaddomain-method.md)|Entlädt die angegebene Anwendungsdomäne, die vom aktuellen Prozess an.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** 1.0, 1.1  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.AppDomain>
- [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
- [ICLRRuntimeHost-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
- [Laufzeithosts](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a51xd4ze(v=vs.100))
- [Hostingschnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [CorRuntimeHost-Co-Klasse](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
