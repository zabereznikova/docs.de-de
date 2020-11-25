---
title: IAppDomainSetup-Schnittstelle
ms.date: 03/30/2017
api_name:
- IAppDomainSetup
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IAppDomainSetup
helpviewer_keywords:
- IAppDomainSetup interface [.NET Framework hosting]
ms.assetid: 1844da85-c031-40bf-bea4-1a3d12a36c8c
topic_type:
- apiref
ms.openlocfilehash: d504101747995557ba526c88de451ebab7b3c556
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95698558"
---
# <a name="iappdomainsetup-interface"></a>IAppDomainSetup-Schnittstelle

Stellt Eigenschaften bereit, die es dem Host ermöglichen, einen <xref:System.AppDomain?displayProperty=nameWithType> Typ vor dem Aufrufen der [ICorRuntimeHost:: CreateDomainEx](icorruntimehost-createdomainex-method.md) -Methode zum Erstellen zu konfigurieren.  
  
## <a name="properties"></a>Eigenschaften  
  
|Eigenschaft|BESCHREIBUNG|  
|--------------|-----------------|  
|<xref:System.AppDomainSetup.ApplicationBase%2A>|Ruft den Namen des Verzeichnisses ab, das die Anwendung enthält, oder legt diesen fest.|  
|<xref:System.AppDomainSetup.ApplicationName%2A>|Ruft den Namen der Anwendung ab oder legt diesen fest.|  
|<xref:System.AppDomainSetup.CachePath%2A>|Ruft den Namen eines für die Anwendung spezifischen Bereichs ab, in dem Dateien kopiert werden, oder legt diesen fest.|  
|<xref:System.AppDomainSetup.ConfigurationFile%2A>|Ruft den Namen der Konfigurationsdatei für eine Anwendung ab oder legt ihn fest.|  
|<xref:System.AppDomainSetup.DynamicBase%2A>|Ruft den Namen des Verzeichnisses ab, in dem dynamisch generierte Dateien gespeichert und darauf zugegriffen wird, oder legt diesen fest.|  
|<xref:System.AppDomainSetup.LicenseFile%2A>|Ruft den Pfad zu der Lizenzdatei ab, die dieser Domäne zugeordnet ist, oder legt diesen fest.|  
|<xref:System.AppDomainSetup.PrivateBinPath%2A>|Ruft die Liste der Verzeichnisse in Kombination mit dem <xref:System.AppDomainSetup.ApplicationBase%2A> Verzeichnis ab, für das nach privaten Assemblys gesucht werden soll|  
|<xref:System.AppDomainSetup.PrivateBinPathProbe%2A>|Ruft einen Zeichen folgen Wert <xref:System.AppDomainSetup.ApplicationBase%2A> ab, der den Suchpfad für die Anwendung einschließt oder ausschließt, oder legt diesen fest.|  
|<xref:System.AppDomainSetup.ShadowCopyDirectories%2A>|Ruft die Namen der Verzeichnisse ab, die die zu Schatten kopierenden Assemblys enthalten, oder legt diese fest.|  
|<xref:System.AppDomainSetup.ShadowCopyFiles%2A>|Ruft eine Zeichenfolge ab, die angibt, ob das Schatten kopieren aktiviert oder deaktiviert ist, oder legt diese fest. Gültige Werte sind "true" oder "false".|  
  
## <a name="remarks"></a>Hinweise  

 Die- `IAppDomainSetup` Schnittstelle entspricht der verwalteten <xref:System.IAppDomainSetup> Schnittstelle, die vom <xref:System.AppDomainSetup> Typ implementiert wird. <xref:System.IAppDomainSetup?displayProperty=nameWithType>Ausführliche Beschreibungen der Eigenschaften finden Sie unter.  
  
 `IAppDomainSetup` stellt Assemblybindungsinformationen dar, die einer- <xref:System.AppDomain> Instanz vor deren Erstellung hinzugefügt werden können. Ein Host kann z. b. die-Eigenschaft festlegen, <xref:System.AppDomainSetup.ApplicationBase%2A> um ein Stammverzeichnis einzurichten, das die Common Language Runtime-Überprüfungen (CLR) für verwaltete Assemblys durchführen.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  

 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework Versionen:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.AppDomain>
- <xref:System.AppDomainSetup>
- <xref:System.IAppDomainSetup>
- [Hosten von Schnittstellen](hosting-interfaces.md)
