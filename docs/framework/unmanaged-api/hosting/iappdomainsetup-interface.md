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
ms.openlocfilehash: 0fab64c31d4a73995c16d21767f4569f21c7df9a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126870"
---
# <a name="iappdomainsetup-interface"></a>IAppDomainSetup-Schnittstelle
Stellt Eigenschaften bereit, die es dem Host ermöglichen, einen <xref:System.AppDomain?displayProperty=nameWithType> Typ zu konfigurieren, bevor die [ICorRuntimeHost:: CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) -Methode aufgerufen wird, um ihn zu erstellen.  
  
## <a name="properties"></a>Eigenschaften  
  
|property|Beschreibung|  
|--------------|-----------------|  
|<xref:System.AppDomainSetup.ApplicationBase%2A>|Ruft den Namen des Verzeichnisses ab, das die Anwendung enthält, oder legt diesen fest.|  
|<xref:System.AppDomainSetup.ApplicationName%2A>|Ruft den Namen der Anwendung ab oder legt diesen fest.|  
|<xref:System.AppDomainSetup.CachePath%2A>|Ruft den Namen eines für die Anwendung spezifischen Bereichs ab, in dem Dateien kopiert werden, oder legt diesen fest.|  
|<xref:System.AppDomainSetup.ConfigurationFile%2A>|Ruft den Namen der Konfigurationsdatei für eine Anwendung ab oder legt ihn fest.|  
|<xref:System.AppDomainSetup.DynamicBase%2A>|Ruft den Namen des Verzeichnisses ab, in dem dynamisch generierte Dateien gespeichert und darauf zugegriffen wird, oder legt diesen fest.|  
|<xref:System.AppDomainSetup.LicenseFile%2A>|Ruft den Pfad zu der Lizenzdatei ab, die dieser Domäne zugeordnet ist, oder legt diesen fest.|  
|<xref:System.AppDomainSetup.PrivateBinPath%2A>|Ruft die Liste der Verzeichnisse in Kombination mit dem <xref:System.AppDomainSetup.ApplicationBase%2A> Verzeichnis ab, das nach privaten Assemblys gesucht werden soll|  
|<xref:System.AppDomainSetup.PrivateBinPathProbe%2A>|Ruft einen Zeichen folgen Wert ab, der <xref:System.AppDomainSetup.ApplicationBase%2A> aus dem Suchpfad für die Anwendung einschließt oder ausschließt, oder legt diesen fest.|  
|<xref:System.AppDomainSetup.ShadowCopyDirectories%2A>|Ruft die Namen der Verzeichnisse ab, die die zu Schatten kopierenden Assemblys enthalten, oder legt diese fest.|  
|<xref:System.AppDomainSetup.ShadowCopyFiles%2A>|Ruft eine Zeichenfolge ab, die angibt, ob das Schatten kopieren aktiviert oder deaktiviert ist, oder legt diese fest. Gültige Werte sind "true" oder "false".|  
  
## <a name="remarks"></a>Hinweise  
 Die `IAppDomainSetup`-Schnittstelle entspricht der verwalteten <xref:System.IAppDomainSetup> Schnittstelle, die vom <xref:System.AppDomainSetup> Typ implementiert wird. Ausführliche Beschreibungen der Eigenschaften finden Sie unter <xref:System.IAppDomainSetup?displayProperty=nameWithType>.  
  
 `IAppDomainSetup` stellt Assemblybindungsinformationen dar, die einer <xref:System.AppDomain> Instanz vor deren Erstellung hinzugefügt werden können. Beispielsweise kann ein Host die <xref:System.AppDomainSetup.ApplicationBase%2A>-Eigenschaft festlegen, um ein Stammverzeichnis einzurichten, das von der Common Language Runtime (CLR) für verwaltete Assemblys überprüft wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Mscoree. h  
  
 **Bibliothek:** Als Ressource in Mscoree. dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.AppDomain>
- <xref:System.AppDomainSetup>
- <xref:System.IAppDomainSetup>
- [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
