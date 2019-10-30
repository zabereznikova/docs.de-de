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
ms.openlocfilehash: e66e1468a864ec85d88f759c481c7a9707d37f7e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139544"
---
# <a name="icorruntimehost-interface"></a>ICorRuntimeHost-Schnittstelle
Stellt Methoden bereit, die es dem Host ermöglichen, die Common Language Runtime (CLR) explizit zu starten und zu starten, um Anwendungs Domänen zu erstellen und zu konfigurieren, um auf die Standard Domäne zuzugreifen und um alle Domänen aufzulisten, die im Prozess ausgeführt werden.  
  
 In der .NET Framework Version 2,0 wird diese Schnittstelle von [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)ersetzt.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[CloseEnum-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-closeenum-method.md)|Setzt einen Domänen Enumerator auf den Anfang der Domänen Liste zurück.|  
|[CreateDomain-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md)|Erstellt eine Anwendungsdomäne. Der Aufrufer erhält einen Schnittstellen Zeiger vom Typ <xref:System._AppDomain> zu einer Instanz des Typs <xref:System.AppDomain?displayProperty=nameWithType>.|  
|[CreateDomainEx-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md)|Erstellt eine Anwendungsdomäne. Diese Methode ermöglicht es dem Aufrufer, eine IAppDomainSetup-Instanz zu übergeben, um zusätzliche Funktionen der zurückgegebenen <xref:System._AppDomain> Instanz zu konfigurieren.|  
|[CreateDomainSetup-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainsetup-method.md)|Ruft einen Schnittstellen Zeiger vom Typ `IAppDomainSetup` zu einer <xref:System.AppDomainSetup> Instanz ab. `IAppDomainSetup` stellt Methoden bereit, um Aspekte einer Anwendungsdomäne vor der Erstellung zu konfigurieren.|  
|[CreateEvidence-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md)|Ruft einen Schnittstellen Zeiger vom Typ "<xref:System.Security.Principal.IIdentity>" ab, der dem Host das Erstellen von Sicherheits beweisen ermöglicht, die an " [kreatedomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) " oder " [kreatedomainex](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md)" übergeben werden.|  
|[CreateLogicalThreadState-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createlogicalthreadstate-method.md)|Nicht verwenden.|  
|[CurrentDomain-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-currentdomain-method.md)|Ruft einen Schnittstellen Zeiger vom Typ <xref:System._AppDomain> ab, der die Domäne darstellt, die für den aktuellen Thread geladen wurde.|  
|[DeleteLogicalThreadState-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-deletelogicalthreadstate-method.md)|Nicht verwenden.|  
|[EnumDomains-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md)|Ruft einen Enumerator für die Domänen im aktuellen Prozess ab.|  
|[GetConfiguration-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-getconfiguration-method.md)|Ruft ein Objekt ab, mit dem der Host die Rückruf Konfiguration der CLR angeben kann.|  
|[GetDefaultDomain-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-getdefaultdomain-method.md)|Ruft einen Schnittstellen Zeiger vom Typ <xref:System._AppDomain> ab, der die Standard Domäne für den aktuellen Prozess darstellt.|  
|[LocksHeldByLogicalThread-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-locksheldbylogicalthread-method.md)|Nicht verwenden.|  
|[MapFile-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-mapfile-method.md)|Ordnet die angegebene Datei dem Arbeitsspeicher zu. Diese Methode ist veraltet.|  
|[NextDomain-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-nextdomain-method.md)|Ruft einen Schnittstellen Zeiger auf die nächste Domäne in der-Enumeration ab.|  
|[Start-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-start-method.md)|Startet die CLR.|  
|[Stop-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-stop-method.md)|Beendet die Ausführung von Code in der Laufzeit für den aktuellen Prozess.|  
|[SwitchInLogicalThreadState-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-switchinlogicalthreadstate-method.md)|Nicht verwenden.|  
|[SwitchOutLogicalThreadState-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-switchoutlogicalthreadstate-method.md)|Nicht verwenden.|  
|[UnloadDomain-Methode](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-unloaddomain-method.md)|Entlädt die angegebene Anwendungsdomäne aus dem aktuellen Prozess.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework Versionen:** 1,0, 1,1  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.AppDomain>
- [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
- [ICLRRuntimeHost-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
- [Laufzeithosts](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a51xd4ze(v=vs.100))
- [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [CorRuntimeHost-Co-Klasse](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
