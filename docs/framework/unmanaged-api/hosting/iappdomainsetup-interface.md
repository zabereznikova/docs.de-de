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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bbde873481aea9de94862117a99079301965f33c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59220070"
---
# <a name="iappdomainsetup-interface"></a>IAppDomainSetup-Schnittstelle
Enthält Eigenschaften, die dem Host so konfigurieren Sie eine <xref:System.AppDomain?displayProperty=nameWithType> Typ vor dem Aufruf der [ICorRuntimeHost:: CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) Methode, um es zu erstellen.  
  
## <a name="properties"></a>Eigenschaften  
  
|Eigenschaft|Beschreibung|  
|--------------|-----------------|  
|<xref:System.AppDomainSetup.ApplicationBase%2A>|Übernimmt oder bestimmt den Namen des Verzeichnisses, das die Anwendung enthält.|  
|<xref:System.AppDomainSetup.ApplicationName%2A>|Ruft den Namen der Anwendung ab oder legt diesen fest.|  
|<xref:System.AppDomainSetup.CachePath%2A>|Übernimmt oder bestimmt den Namen eines Bereichs bestimmte für die Anwendung, in denen Dateien Schattenkopien sind.|  
|<xref:System.AppDomainSetup.ConfigurationFile%2A>|Ruft ab oder legt den Namen der Konfigurationsdatei für eine Anwendung fest.|  
|<xref:System.AppDomainSetup.DynamicBase%2A>|Übernimmt oder bestimmt den Namen des Verzeichnisses, in dem dynamisch generierte Dateien gespeichert und auf die zugegriffen werden.|  
|<xref:System.AppDomainSetup.LicenseFile%2A>|Übernimmt oder bestimmt den Pfad zu der Lizenzdatei, die mit dieser Domäne verbunden ist.|  
|<xref:System.AppDomainSetup.PrivateBinPath%2A>|Übernimmt oder bestimmt die Liste der Verzeichnisse, die in Kombination mit der <xref:System.AppDomainSetup.ApplicationBase%2A> Verzeichnis nach privaten Assemblys suchen.|  
|<xref:System.AppDomainSetup.PrivateBinPathProbe%2A>|Übernimmt oder bestimmt die Zeichenfolge zurück, das ein- oder ausschließt <xref:System.AppDomainSetup.ApplicationBase%2A> in den Suchpfad für die Anwendung.|  
|<xref:System.AppDomainSetup.ShadowCopyDirectories%2A>|Übernimmt oder bestimmt den Namen der Verzeichnisse, die Assemblys werden Schattenkopien enthalten.|  
|<xref:System.AppDomainSetup.ShadowCopyFiles%2A>|Ruft ab oder legt eine Zeichenfolge, die angibt, ob die Erstellung von Schattenkopien aktiviert oder deaktiviert ist. Gültige Werte sind "true" oder "false".|  
  
## <a name="remarks"></a>Hinweise  
 Die `IAppDomainSetup` Schnittstelle entspricht der verwalteten <xref:System.IAppDomainSetup> Schnittstelle, die die <xref:System.AppDomainSetup> Typ implementiert. Finden Sie unter <xref:System.IAppDomainSetup?displayProperty=nameWithType> ausführliche Beschreibungen der Eigenschaften.  
  
 `IAppDomainSetup` Stellt Assembly-Bindungsinformationen, die hinzugefügt werden, kann, ein <xref:System.AppDomain> Instanz vor ihrer Erstellung. Ein Host kann festlegen, z. B. die <xref:System.AppDomainSetup.ApplicationBase%2A> Eigenschaft ein Stammverzeichnis, zu ermitteln, welche die Tests die common Language Runtime (CLR) für verwaltete Assemblys.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** Als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.AppDomain>
- <xref:System.AppDomainSetup>
- <xref:System.IAppDomainSetup>
- [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
