---
title: IAppDomainSetup-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAppDomainSetup
api_location: mscoree.dll
api_type: COM
f1_keywords: IAppDomainSetup
helpviewer_keywords: IAppDomainSetup interface [.NET Framework hosting]
ms.assetid: 1844da85-c031-40bf-bea4-1a3d12a36c8c
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e6ed5ea00799fff70626114257efef2d06b505ae
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iappdomainsetup-interface"></a>IAppDomainSetup-Schnittstelle
Enthält Eigenschaften, mit denen den Host so konfigurieren Sie eine <xref:System.AppDomain?displayProperty=nameWithType> Typ vor dem Aufruf der [ICorRuntimeHost:: CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) Methode, um ihn zu erstellen.  
  
## <a name="properties"></a>Eigenschaften  
  
|Eigenschaft|Beschreibung|  
|--------------|-----------------|  
|<xref:System.AppDomainSetup.ApplicationBase%2A>|Ruft ab oder legt den Namen des Verzeichnisses, das die Anwendung enthält.|  
|<xref:System.AppDomainSetup.ApplicationName%2A>|Ruft den Namen der Anwendung ab oder legt diesen fest.|  
|<xref:System.AppDomainSetup.CachePath%2A>|Ruft ab oder legt den Namen eines Bereichs bestimmte an die Anwendung sind, in denen Dateien Schattenkopie.|  
|<xref:System.AppDomainSetup.ConfigurationFile%2A>|Ruft ab oder legt den Namen der Konfigurationsdatei für eine Anwendung fest.|  
|<xref:System.AppDomainSetup.DynamicBase%2A>|Ruft ab oder legt den Namen des Verzeichnisses, in dem dynamisch generierte Dateien gespeichert und auf die zugegriffen werden.|  
|<xref:System.AppDomainSetup.LicenseFile%2A>|Ruft ab oder legt den Pfad fest, um die Lizenzdatei, die mit dieser Domäne verknüpft ist.|  
|<xref:System.AppDomainSetup.PrivateBinPath%2A>|Ruft ab oder legt die Liste der Verzeichnisse, die zusammen mit den <xref:System.AppDomainSetup.ApplicationBase%2A> Verzeichnis, das nach privaten Assemblys suchen.|  
|<xref:System.AppDomainSetup.PrivateBinPathProbe%2A>|Ruft ab oder legt einen Zeichenfolgenwert, der ein- oder ausschließt <xref:System.AppDomainSetup.ApplicationBase%2A> aus den Suchpfad für die Anwendung.|  
|<xref:System.AppDomainSetup.ShadowCopyDirectories%2A>|Ruft ab oder legt den Namen der Verzeichnisse, die zu Schattenkopien werden Assemblys enthalten.|  
|<xref:System.AppDomainSetup.ShadowCopyFiles%2A>|Ruft ab oder legt eine Zeichenfolge, die angibt, ob die Erstellung von Schattenkopien ein- oder ausgeschaltet ist. Gültige Werte sind "true" oder "false".|  
  
## <a name="remarks"></a>Hinweise  
 Die `IAppDomainSetup` Schnittstelle entspricht der verwalteten <xref:System.IAppDomainSetup> Schnittstelle, die die <xref:System.AppDomainSetup> Typ implementiert. Finden Sie unter <xref:System.IAppDomainSetup?displayProperty=nameWithType> eine ausführliche Beschreibung der Eigenschaften.  
  
 `IAppDomainSetup`Stellt Assembly-Bindungsinformationen, die hinzugefügt werden, kann, ein <xref:System.AppDomain> -Instanz vor ihrer Erstellung. Ein Host kann festlegen, z. B. die <xref:System.AppDomainSetup.ApplicationBase%2A> Eigenschaft, um ein Stammverzeichnis aufbauen, die die common Language Runtime (CLR)-für Prüfpunkte verwaltete Assemblys.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.AppDomain>  
 <xref:System.AppDomainSetup>  
 <xref:System.IAppDomainSetup>  
 [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
