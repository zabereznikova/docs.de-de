---
title: <disableFusionUpdatesFromADManager>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- disableFusionUpdatesFromADManager element
- <disableFusionUpdatesFromADManager> element
ms.assetid: 58d2866c-37bd-4ffa-abaf-ff35926a2939
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a1923e70143ea2a158447eccdb35d347fe4f51ea
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663767"
---
# <a name="disablefusionupdatesfromadmanager-element"></a>\<disablefusionupdatesfromadmanager-> Element
Gibt an, ob das Standardverhalten deaktiviert wird. Dieses besteht darin, dem Laufzeithost das Außerkraftsetzen von Konfigurationseinstellungen für eine Anwendungsdomäne zu ermöglichen.  
  
 \<Configuration >-Element  
\<Runtime-> Element  
\<disableFusionUpdatesFromADManager>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<disableFusionUpdatesFromADManager enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|enabled|Erforderliches Attribut.<br /><br /> Gibt an, ob die Standard Fähigkeit zum Überschreiben von Fusions Einstellungen deaktiviert ist.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|Description|  
|-----------|-----------------|  
|0|Deaktivieren Sie nicht die Möglichkeit, die Fusion-Einstellungen zu überschreiben. Dies ist das Standardverhalten, beginnend mit dem .NET Framework 4.|  
|1|Deaktivieren Sie die Möglichkeit zum Überschreiben von Fusion-Einstellungen. Dadurch wird das Verhalten früherer Versionen des .NET Framework wieder hergestellt.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Hinweise  
 Beginnend mit dem .NET Framework 4 besteht das Standardverhalten darin, dass das <xref:System.AppDomainManager> -Objekt Konfigurationseinstellungen mithilfe der <xref:System.AppDomainSetup.ConfigurationFile%2A> -Eigenschaft <xref:System.AppDomainSetup> oder der <xref:System.AppDomainSetup.SetConfigurationBytes%2A> -Methode des-Objekts, das an die-Implementierung übermittelt wird, überschreiben kann. der- <xref:System.AppDomainManager>Methode in der Unterklasse von. <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> Bei der Standard Anwendungsdomäne setzen die Einstellungen, die Sie ändern, die Einstellungen außer Kraft, die von der Anwendungs Konfigurationsdatei angegeben wurden. Für andere Anwendungs Domänen überschreiben Sie die Konfigurationseinstellungen, die an die <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> - <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> Methode oder die-Methode übergebenen wurden.  
  
 Sie können entweder neue Konfigurationsinformationen übergeben oder NULL (`Nothing` in Visual Basic) übergeben, um die übergebenen Konfigurationsinformationen auszuschließen.  
  
 Übergeben Sie Konfigurationsinformationen nicht an die <xref:System.AppDomainSetup.ConfigurationFile%2A> -Eigenschaft und die <xref:System.AppDomainSetup.SetConfigurationBytes%2A> -Methode. Wenn Sie Konfigurationsinformationen an beides übergeben, werden die Informationen, die Sie <xref:System.AppDomainSetup.ConfigurationFile%2A> an die-Eigenschaft übergeben, <xref:System.AppDomainSetup.SetConfigurationBytes%2A> ignoriert, da die-Methode Konfigurationsinformationen aus der Anwendungs Konfigurationsdatei überschreibt. <xref:System.AppDomainSetup.ConfigurationFile%2A> Wenn Sie die-Eigenschaft verwenden, können Sie NULL (`Nothing` in Visual Basic) an die <xref:System.AppDomainSetup.SetConfigurationBytes%2A> -Methode übergeben, um alle Konfigurations Bytes zu eliminieren, die im Aufrufe <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> der <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> -oder-Methode angegeben wurden.  
  
 Zusätzlich zu den Konfigurationsinformationen können Sie die <xref:System.AppDomainSetup> folgenden Einstellungen für das-Objekt ändern, das an die Implementierung <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> der-Methode weitergegeben <xref:System.AppDomainSetup.ApplicationBase%2A>wird <xref:System.AppDomainSetup.ApplicationName%2A>: <xref:System.AppDomainSetup.CachePath%2A>, <xref:System.AppDomainSetup.DisallowApplicationBaseProbing%2A>, <xref:System.AppDomainSetup.DisallowBindingRedirects%2A> ,, , <xref:System.AppDomainSetup.DisallowCodeDownload%2A>, <xref:System.AppDomainSetup.DisallowPublisherPolicy%2A>, ,,<xref:System.AppDomainSetup.LoaderOptimization%2A>,, und<xref:System.AppDomainSetup.ShadowCopyDirectories%2A>. <xref:System.AppDomainSetup.PrivateBinPath%2A> <xref:System.AppDomainSetup.PrivateBinPathProbe%2A> <xref:System.AppDomainSetup.DynamicBase%2A> <xref:System.AppDomainSetup.ShadowCopyFiles%2A>  
  
 Als Alternative zur Verwendung des `<disableFusionUpdatesFromADManager>` -Elements können Sie das Standardverhalten deaktivieren, indem Sie eine Registrierungs Einstellung erstellen oder eine Umgebungsvariable festlegen. Erstellen Sie in der Registrierung einen DWORD-Wert `COMPLUS_disableFusionUpdatesFromADManager` namens `HKCU\Software\Microsoft\.NETFramework` unter `HKLM\Software\Microsoft\.NETFramework`oder, und legen Sie den Wert auf 1 fest. Legen Sie in der Befehlszeile die Umgebungsvariable `COMPLUS_disableFusionUpdatesFromADManager` auf 1 fest.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie die Möglichkeit zum Überschreiben von Fusions Einstellungen mithilfe `<disableFusionUpdatesFromADManager>` des-Elements deaktivieren.  
  
```xml  
<configuration>  
   <runtime>  
      <disableFusionUpdatesFromADManager enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch

- [Schema für Laufzeiteinstellungen](index.md)
- [Konfigurationsdateischema](../index.md)
- [So sucht Common Language Runtime nach Assemblys](../../../deployment/how-the-runtime-locates-assemblies.md)
