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
ms.openlocfilehash: 9fcb5e189af9f72de7635aad550a5e8ab5522dbd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720619"
---
# <a name="icorruntimehost-interface"></a>ICorRuntimeHost-Schnittstelle

Stellt Methoden bereit, die es dem Host ermöglichen, die Common Language Runtime (CLR) explizit zu starten und zu starten, um Anwendungs Domänen zu erstellen und zu konfigurieren, um auf die Standard Domäne zuzugreifen und um alle Domänen aufzulisten, die im Prozess ausgeführt werden.  
  
 In der .NET Framework Version 2,0 wird diese Schnittstelle von [ICLRRuntimeHost](iclrruntimehost-interface.md)ersetzt.  
  
## <a name="methods"></a>Methoden  
  
|Methode|BESCHREIBUNG|  
|------------|-----------------|  
|[CloseEnum-Methode](icorruntimehost-closeenum-method.md)|Setzt einen Domänen Enumerator auf den Anfang der Domänen Liste zurück.|  
|[CreateDomain-Methode](icorruntimehost-createdomain-method.md)|Erstellt eine Anwendungsdomäne. Der Aufrufer erhält einen Schnittstellen Zeiger vom Typ <xref:System._AppDomain> auf eine Instanz vom Typ <xref:System.AppDomain?displayProperty=nameWithType> .|  
|[CreateDomainEx-Methode](icorruntimehost-createdomainex-method.md)|Erstellt eine Anwendungsdomäne. Diese Methode ermöglicht es dem Aufrufer, eine IAppDomainSetup-Instanz zu übergeben, um zusätzliche Funktionen der zurückgegebenen Instanz zu konfigurieren <xref:System._AppDomain> .|  
|[CreateDomainSetup-Methode](icorruntimehost-createdomainsetup-method.md)|Ruft einen Schnittstellen Zeiger vom Typ `IAppDomainSetup` auf eine- <xref:System.AppDomainSetup> Instanz ab. `IAppDomainSetup` stellt Methoden bereit, um Aspekte einer Anwendungsdomäne vor der Erstellung zu konfigurieren.|  
|[CreateEvidence-Methode](icorruntimehost-createevidence-method.md)|Ruft einen Schnittstellen Zeiger vom Typ ab <xref:System.Security.Principal.IIdentity> , der dem Host das Erstellen von Sicherheits beweisen ermöglicht, die an " [kreatedomain](icorruntimehost-createdomain-method.md) " oder " [kreatedomainex](icorruntimehost-createdomainex-method.md)" übergeben werden.|  
|[CreateLogicalThreadState-Methode](icorruntimehost-createlogicalthreadstate-method.md)|Darf nicht verwendet werden.|  
|[CurrentDomain-Methode](icorruntimehost-currentdomain-method.md)|Ruft einen Schnittstellen Zeiger vom Typ ab <xref:System._AppDomain> , der die Domäne darstellt, die für den aktuellen Thread geladen wurde.|  
|[DeleteLogicalThreadState-Methode](icorruntimehost-deletelogicalthreadstate-method.md)|Darf nicht verwendet werden.|  
|[EnumDomains-Methode](icorruntimehost-enumdomains-method.md)|Ruft einen Enumerator für die Domänen im aktuellen Prozess ab.|  
|[GetConfiguration-Methode](icorruntimehost-getconfiguration-method.md)|Ruft ein Objekt ab, mit dem der Host die Rückruf Konfiguration der CLR angeben kann.|  
|[GetDefaultDomain-Methode](icorruntimehost-getdefaultdomain-method.md)|Ruft einen Schnittstellen Zeiger vom Typ ab <xref:System._AppDomain> , der die Standard Domäne für den aktuellen Prozess darstellt.|  
|[LocksHeldByLogicalThread-Methode](icorruntimehost-locksheldbylogicalthread-method.md)|Darf nicht verwendet werden.|  
|[MapFile-Methode](icorruntimehost-mapfile-method.md)|Ordnet die angegebene Datei dem Arbeitsspeicher zu. Diese Methode ist veraltet.|  
|[NextDomain-Methode](icorruntimehost-nextdomain-method.md)|Ruft einen Schnittstellen Zeiger auf die nächste Domäne in der-Enumeration ab.|  
|[Start-Methode](icorruntimehost-start-method.md)|Startet die CLR.|  
|[Stop-Methode](icorruntimehost-stop-method.md)|Beendet die Ausführung von Code in der Laufzeit für den aktuellen Prozess.|  
|[SwitchInLogicalThreadState-Methode](icorruntimehost-switchinlogicalthreadstate-method.md)|Darf nicht verwendet werden.|  
|[SwitchOutLogicalThreadState-Methode](icorruntimehost-switchoutlogicalthreadstate-method.md)|Darf nicht verwendet werden.|  
|[UnloadDomain-Methode](icorruntimehost-unloaddomain-method.md)|Entlädt die angegebene Anwendungsdomäne aus dem aktuellen Prozess.|  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:** 1,0, 1,1  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.AppDomain>
- [Hosting](index.md)
- [ICLRRuntimeHost-Schnittstelle](iclrruntimehost-interface.md)
- [Laufzeithosts](/previous-versions/dotnet/netframework-4.0/a51xd4ze(v=vs.100))
- [Hosten von Schnittstellen](hosting-interfaces.md)
- [CorRuntimeHost-Co-Klasse](corruntimehost-coclass.md)
