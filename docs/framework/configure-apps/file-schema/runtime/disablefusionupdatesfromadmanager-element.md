---
title: '&lt;DisableFusionUpdatesFromADManager&gt; Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- disableFusionUpdatesFromADManager element
- <disableFusionUpdatesFromADManager> element
ms.assetid: 58d2866c-37bd-4ffa-abaf-ff35926a2939
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1d3a1214b4aecf56c9a6440e31459573a5922676
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltdisablefusionupdatesfromadmanagergt-element"></a>&lt;DisableFusionUpdatesFromADManager&gt; Element
Gibt an, ob das Standardverhalten deaktiviert wird. Dieses besteht darin, dem Laufzeithost das Außerkraftsetzen von Konfigurationseinstellungen für eine Anwendungsdomäne zu ermöglichen.  
  
 \<Konfiguration >-Element  
\<Common Language Runtime >-Element  
\<DisableFusionUpdatesFromADManager >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<disableFusionUpdatesFromADManager enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|enabled|Erforderliches Attribut.<br /><br /> Gibt an, ob die Standard-Fähigkeit Fusion-Einstellungen außer Kraft gesetzt deaktiviert ist.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|0|Deaktivieren Sie nicht die Möglichkeit, Fusion-Einstellungen außer Kraft gesetzt. Dies ist das Standardverhalten, beginnend mit der [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)].|  
|1|Deaktivieren Sie die Möglichkeit, Fusion-Einstellungen außer Kraft gesetzt. Dadurch wird das Verhalten von früheren Versionen von .NET Framework wieder.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Hinweise  
 Beginnend mit der [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], das Standardverhalten besteht, um zu ermöglichen die <xref:System.AppDomainManager> Objekt, das mit Konfigurationseinstellungen zu überschreiben die <xref:System.AppDomainSetup.ConfigurationFile%2A> Eigenschaft oder die <xref:System.AppDomainSetup.SetConfigurationBytes%2A> Methode der <xref:System.AppDomainSetup> Objekt, um Ihre Implementierung übergeben wird, von der <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> Methode in der Unterklasse von <xref:System.AppDomainManager>. Für die Standardanwendungsdomäne überschreiben die Einstellungen, die Sie ändern die Einstellungen, die von der Konfigurationsdatei der Anwendung angegeben wurden. Für andere Anwendungsdomänen, überschreiben sie die Konfigurationseinstellungen, die übergeben wurden, die <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> oder <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> Methode.  
  
 Sie können neue Konfigurationsinformationen übergeben, oder übergeben Sie null (`Nothing` in Visual Basic) Konfigurationsinformationen zu vermeiden, die im übergeben wurde.  
  
 Übergeben Sie Konfigurationsinformationen nicht sowohl die <xref:System.AppDomainSetup.ConfigurationFile%2A> Eigenschaft und die <xref:System.AppDomainSetup.SetConfigurationBytes%2A> Methode. Wenn Sie Konfigurationsinformationen für beide übergeben, die Informationen, übergeben die <xref:System.AppDomainSetup.ConfigurationFile%2A> Eigenschaft wird ignoriert, da die <xref:System.AppDomainSetup.SetConfigurationBytes%2A> Methode überschreibt die Konfigurationsinformationen aus der Anwendungskonfigurationsdatei. Bei Verwendung der <xref:System.AppDomainSetup.ConfigurationFile%2A> -Eigenschaft, Sie können null übergeben (`Nothing` in Visual Basic), die <xref:System.AppDomainSetup.SetConfigurationBytes%2A> Methode, um alle Konfigurationsbytes auszuschließen, die im Aufruf angegeben wurden die <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> oder <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> Methode.  
  
 Zusätzlich zu den Konfigurationsinformationen, können Sie die folgenden Einstellungen ändern, auf die <xref:System.AppDomainSetup> Objekt, auf Ihre Implementierung übergeben wird, die <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> Methode: <xref:System.AppDomainSetup.ApplicationBase%2A>, <xref:System.AppDomainSetup.ApplicationName%2A>, <xref:System.AppDomainSetup.CachePath%2A>, <xref:System.AppDomainSetup.DisallowApplicationBaseProbing%2A>, <xref:System.AppDomainSetup.DisallowBindingRedirects%2A> , <xref:System.AppDomainSetup.DisallowCodeDownload%2A>, <xref:System.AppDomainSetup.DisallowPublisherPolicy%2A>, <xref:System.AppDomainSetup.DynamicBase%2A>, <xref:System.AppDomainSetup.LoaderOptimization%2A>, <xref:System.AppDomainSetup.PrivateBinPath%2A>, <xref:System.AppDomainSetup.PrivateBinPathProbe%2A>, <xref:System.AppDomainSetup.ShadowCopyDirectories%2A>, und <xref:System.AppDomainSetup.ShadowCopyFiles%2A>.  
  
 Als Alternative zur Verwendung der `<disableFusionUpdatesFromADManager>` -Element, Sie können das Standardverhalten deaktivieren, erstellen Sie eine Einstellung in der Registrierung oder durch Festlegen einer Umgebungsvariablen. Erstellen Sie in der Registrierung einen DWORD-Wert, der mit dem Namen `COMPLUS_disableFusionUpdatesFromADManager` unter `HKCU\Software\Microsoft\.NETFramework` oder `HKLM\Software\Microsoft\.NETFramework`, und den Wert auf 1 festgelegt. Legen Sie in der Befehlszeile die Umgebungsvariable `COMPLUS_disableFusionUpdatesFromADManager` auf 1.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie die Möglichkeit, mithilfe von Fusion-Einstellungen überschreiben Deaktivieren der `<disableFusionUpdatesFromADManager>` Element.  
  
```xml  
<configuration>  
   <runtime>  
      <disableFusionUpdatesFromADManager enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [So sucht Common Language Runtime nach Assemblys](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
