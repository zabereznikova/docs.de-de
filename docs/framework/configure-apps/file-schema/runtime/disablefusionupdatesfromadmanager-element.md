---
title: <disableFusionUpdatesFromADManager>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- disableFusionUpdatesFromADManager element
- <disableFusionUpdatesFromADManager> element
ms.assetid: 58d2866c-37bd-4ffa-abaf-ff35926a2939
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8c96d5aea150c0dbb55889e9fc26417e7803a155
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66487661"
---
# <a name="disablefusionupdatesfromadmanager-element"></a>\<disableFusionUpdatesFromADManager> Element
Gibt an, ob das Standardverhalten deaktiviert wird. Dieses besteht darin, dem Laufzeithost das Außerkraftsetzen von Konfigurationseinstellungen für eine Anwendungsdomäne zu ermöglichen.  
  
 \<Configuration >-Element  
\<Common Language Runtime >-Element  
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
|enabled|Erforderliches Attribut.<br /><br /> Gibt an, ob die Möglichkeit Standardwert zum Außerkraftsetzen von Fusion-Einstellungen deaktiviert ist.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|Description|  
|-----------|-----------------|  
|0|Deaktivieren Sie nicht die Möglichkeit, die Fusion-Einstellungen außer Kraft gesetzt. Dies ist das Standardverhalten, beginnend mit .NET Framework 4.|  
|1|Deaktivieren Sie die Möglichkeit, die Fusion-Einstellungen außer Kraft gesetzt. Dadurch wird das Verhalten von früheren Versionen von .NET Framework wieder.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Hinweise  
 Ab .NET Framework 4, das Standardverhalten ist, können die <xref:System.AppDomainManager> Objekt, das mithilfe von Konfigurationseinstellungen zu überschreiben die <xref:System.AppDomainSetup.ConfigurationFile%2A> Eigenschaft oder die <xref:System.AppDomainSetup.SetConfigurationBytes%2A> Methode der <xref:System.AppDomainSetup> -Objekt, das für Ihre Implementierung übergeben wird von der <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> -Methode, in die Unterklasse von <xref:System.AppDomainManager>. Für die Standardanwendungsdomäne überschreiben die Einstellungen, die Sie ändern die Einstellungen, die von der Konfigurationsdatei der Anwendung angegeben wurden. Für andere Anwendungsdomänen, überschreiben sie die Konfigurationseinstellungen, die übergeben wurden, die <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> oder <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> Methode.  
  
 Sie können neue Konfigurationsinformationen zu übergeben, oder übergeben Sie null (`Nothing` in Visual Basic), Konfigurationsinformationen zu beseitigen, die übergeben wurde.  
  
 Übergeben Sie Konfigurationsinformationen nicht an beide die <xref:System.AppDomainSetup.ConfigurationFile%2A> Eigenschaft und die <xref:System.AppDomainSetup.SetConfigurationBytes%2A> Methode. Wenn Sie Konfigurationsinformationen für beide übergeben, die Informationen, übergeben die <xref:System.AppDomainSetup.ConfigurationFile%2A> Eigenschaft wird ignoriert, da die <xref:System.AppDomainSetup.SetConfigurationBytes%2A> Methode überschreibt, Konfigurationsinformationen aus der Anwendungskonfigurationsdatei befindet. Bei Verwendung der <xref:System.AppDomainSetup.ConfigurationFile%2A> -Eigenschaft, Sie können null übergeben (`Nothing` in Visual Basic), die <xref:System.AppDomainSetup.SetConfigurationBytes%2A> Methode, um jede Konfigurationsbytes zu vermeiden, die im Aufruf angegeben wurden die <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> oder <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> Methode.  
  
 Neben Informationen zu Konfigurationen können Sie die folgenden Einstellungen ändern, auf die <xref:System.AppDomainSetup> -Objekt, das für Ihre Implementierung der übergeben wird die <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> Methode: <xref:System.AppDomainSetup.ApplicationBase%2A>, <xref:System.AppDomainSetup.ApplicationName%2A>, <xref:System.AppDomainSetup.CachePath%2A>, <xref:System.AppDomainSetup.DisallowApplicationBaseProbing%2A>, <xref:System.AppDomainSetup.DisallowBindingRedirects%2A> , <xref:System.AppDomainSetup.DisallowCodeDownload%2A>, <xref:System.AppDomainSetup.DisallowPublisherPolicy%2A>, <xref:System.AppDomainSetup.DynamicBase%2A>, <xref:System.AppDomainSetup.LoaderOptimization%2A>, <xref:System.AppDomainSetup.PrivateBinPath%2A>, <xref:System.AppDomainSetup.PrivateBinPathProbe%2A>, <xref:System.AppDomainSetup.ShadowCopyDirectories%2A>, und <xref:System.AppDomainSetup.ShadowCopyFiles%2A>.  
  
 Als Alternative zur Verwendung der `<disableFusionUpdatesFromADManager>` -Element, Sie können das standardmäßige Verhalten deaktivieren, durch das Erstellen einer registrierungseinstellung oder durch Festlegen einer Umgebungsvariablen. Erstellen Sie in der Registrierung einen DWORD-Wert, der mit dem Namen `COMPLUS_disableFusionUpdatesFromADManager` unter `HKCU\Software\Microsoft\.NETFramework` oder `HKLM\Software\Microsoft\.NETFramework`, und den Wert auf 1 festgelegt. Legen Sie in der Befehlszeile die Umgebungsvariable `COMPLUS_disableFusionUpdatesFromADManager` auf 1.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie So deaktivieren Sie die Möglichkeit, Fusion-Einstellungen mithilfe der `<disableFusionUpdatesFromADManager>` Element.  
  
```xml  
<configuration>  
   <runtime>  
      <disableFusionUpdatesFromADManager enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch

- [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [So sucht Common Language Runtime nach Assemblys](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
