---
title: Konfigurieren von Diensten mit Konfigurationsdateien
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring services [WCF]
ms.assetid: c9c8cd32-2c9d-4541-ad0d-16dff6bd2a00
caps.latest.revision: 29
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e5ad91fa70a743b7135648cb10c7c519e3559bdb
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="configuring-services-using-configuration-files"></a>Konfigurieren von Diensten mit Konfigurationsdateien
Das Konfigurieren eines [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] -Diensts mit einer Konfigurationsdatei bietet Ihnen eine flexible Möglichkeit, die Endpunkt- und Dienstverhaltensdaten zum Zeitpunkt der Bereitstellung statt zur Entwurfszeit anzugeben. Dieses Thema beschreibt die dafür verfügbaren grundlegenden Verfahren.  
  
 Sie können einen [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] -Dienst mithilfe der [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] -Konfigurationstechnologie konfigurieren. Am häufigsten werden XML-Elemente der Web.config-Datei für eine Internetinformationsdienste (IIS)-Website hinzugefügt, die einen [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] -Dienst hostet. Mithilfe der Elemente können Sie Details ändern, zum Beispiel die Endpunktadressen (die eigentlichen für die Kommunikation mit dem Dienst verwendeten Adressen) für einzelne Computer. Zusätzlich umfasst [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] mehrere vom System bereitgestellte Elemente, mit deren Hilfe Sie die grundlegendsten Funktionen eines Diensts auswählen können. Ab [!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)]stellt [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] ein neues Standardkonfigurationsmodell bereit, das die [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] -Konfigurationsanforderungen vereinfacht. Wenn Sie keine [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] -Konfiguration für einen bestimmten Dienst bereitstellen, konfiguriert die Runtime den Dienst automatisch mit Standardendpunkten, -bindungen und -verhalten. In der Praxis ist das Schreiben einer Konfiguration ein wesentlicher Bestandteil beim Programmieren von [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] -Anwendungen.  
  
 [!INCLUDE[crdefault](../../../includes/crdefault-md.md)] [Konfigurieren von Bindungen für Dienste](../../../docs/framework/wcf/configuring-bindings-for-wcf-services.md). Eine Liste von der äußersten häufig Elemente verwendet, finden Sie unter [sicherheitsbindungsarten Bindungen](../../../docs/framework/wcf/system-provided-bindings.md). [!INCLUDE[crabout](../../../includes/crabout-md.md)] zu Standardendpunkten, Bindungen und Verhaltensweisen finden Sie unter [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) und [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
> [!IMPORTANT]
>  Beim Bereitstellen paralleler Szenarien, in denen zwei verschiedene Versionen eines Diensts bereitgestellt werden, müssen bei Verweisen in Konfigurationsdateien partielle Assemblynamen angegeben werden. Dies liegt daran, dass die Konfigurationsdatei gemeinsam von allen Versionen eines Diensts verwendet wird und dass diese Dienste ggf. unter unterschiedlichen Versionen von .NET Framework ausgeführt werden.  
  
## <a name="systemconfiguration-webconfig-and-appconfig"></a>System.Configuration: Web.config und App.config  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] verwendet das Konfigurationssystem System.Configuration des [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]-Namespaces.  
  
 Verwenden Sie für die Konfiguration eines Diensts in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]entweder die Konfigurationsdatei Web.config oder App.config, um die Einstellungen anzugeben. Die Wahl der Konfigurationsdatei wird durch die Hostumgebung des Diensts bestimmt. Wenn Sie den Dienst in IIS hosten, verwenden Sie eine Web.config-Datei. Bei einer anderen Hostumgebung verwenden Sie eine App.config-Datei.  
  
 In [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]werden die gültigen Konfigurationseinstellungen in einer Datei namens App.config gespeichert. Der tatsächlich für die Konfigurationsdatei verwendete Name hängt vom Assemblynamen ab. Einer Assembly mit dem Namen "Cohowinery.exe" ist beispielsweise die Konfigurationsdatei namens "Cohowinery.exe.config" zugeordnet. Sie müssen jedoch nur die Datei App.config ändern. An dieser Datei vorgenommene Änderungen werden bei der Kompilierung automatisch an die tatsächliche Anwendungskonfigurationsdatei weitergegeben.  
  
 Bei Verwendung einer App.config-Datei führt das Konfigurationssystem den Inhalt dieser Datei mit dem Inhalt der Datei Machine.config zusammen, sobald die Anwendung gestartet und die Konfiguration übernommen wird. Dieser Mechanismus ermöglicht es, computerweite Einstellungen in der Datei Machine.config zu definieren. Die Datei App.config kann verwendet werden, um Einstellungen in der Datei Machine.config zu überschreiben. Sie können Einstellungen in der Datei Machine.config aber auch sperren, sodass diese verwendet werden. Im Fall der Datei Web.config führt das Konfigurationssystem den Inhalt aller Web.config-Dateien in allen Verzeichnissen zur schließlich verwendeten Konfiguration im Anwendungsverzeichnis zusammen. [!INCLUDE[crabout](../../../includes/crabout-md.md)] zur Konfiguration und der Priorität der Einstellungen finden Sie in den Themen des <xref:System.Configuration> -Namespaces.  
  
## <a name="major-sections-of-the-configuration-file"></a>Hauptabschnitte der Konfigurationsdatei  
 Die Hauptabschnitte der Konfigurationsdatei umfassen folgende Elemente:  
  
```xml  
<system.ServiceModel>  
  
   <services>  
   <!—- Define the service endpoints. This section is optional in the new  
    default configuration model in .NET Framework 4. -->  
      <service>  
         <endpoint/>  
      </service>  
   </services>  
  
   <bindings>  
   <!-- Specify one or more of the system-provided binding elements,  
    for example, <basicHttpBinding> -->   
   <!-- Alternatively, <customBinding> elements. -->  
      <binding>  
      <!-- For example, a <BasicHttpBinding> element. -->  
      </binding>  
   </bindings>  
  
   <behaviors>  
   <!-- One or more of the system-provided or custom behavior elements. -->  
      <behavior>  
      <!-- For example, a <throttling> element. -->  
      </behavior>  
   </behaviors>  
  
</system.ServiceModel>  
```  
  
> [!NOTE]
>  Die Bindungs- und Verhaltensabschnitte sind optional und nur bei Bedarf enthalten.  
  
### <a name="the-services-element"></a>Die \<Services >-Element  
 Das `services` -Element enthält die Spezifikationen aller Dienste, die die Anwendung hostet. Wenn das vereinfachte Konfigurationsmodell in [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)]verwendet wird, ist dieser Abschnitt optional.  
  
 [\<services>](../../../docs/framework/configure-apps/file-schema/wcf/services.md)  
  
### <a name="the-service-element"></a>Die \<Service >-Element  
 Jeder Dienst verfügt über diese Attribute:  
  
-   `name`. Gibt den Typ an, der eine Implementierung eines Dienstvertrags bereitstellt. Dies ist ein vollqualifizierter Name, der aus dem Namespace und einem Punkt gefolgt von dem Typnamen besteht. Beispiel: `"MyNameSpace.myServiceType"`.  
  
-   `behaviorConfiguration`. Gibt den Namen eines `behavior` -Elements an, das im `behaviors` -Element gefunden wurde. Das angegebene Verhalten steuert Aktionen, beispielsweise ob der Dienst Identitätswechsel erlaubt. Wenn der Wert ein leerer Name oder kein `behaviorConfiguration` ist, wird dem Dienst der Standardsatz von Dienstverhalten hinzugefügt.  
  
-   [\<service>](../../../docs/framework/configure-apps/file-schema/wcf/service.md)  
  
### <a name="the-endpoint-element"></a>Die \<Endpoint >-Element  
 Jeder Endpunkt benötigt eine Adresse, eine Bindung und einen Vertrag. Diese Elemente werden durch die folgenden Attribute dargestellt:  
  
-   `address`. Gibt den Uniform Resource Identifier (URI) des Diensts an. Er kann als absolute Adresse oder als eine zur Basisadresse des Diensts relative Adresse angegeben werden. Eine leere Zeichenfolge zeigt an, dass der Endpunkt unter der Basisadresse verfügbar ist. Diese Basisadresse wird bei der Erstellung des <xref:System.ServiceModel.ServiceHost> für den Dienst angegeben.  
  
-   `binding`. Gibt üblicherweise eine vom System bereitgestellte Bindung, beispielsweise <xref:System.ServiceModel.WSHttpBinding>an, kann aber auch eine benutzerdefinierte Bindung angeben. Die angegebene Bindung bestimmt, welcher Typ von Transport, Sicherheit und Codierung verwendet wird, und ob zuverlässige Sitzungen, Transaktionen oder Streaming unterstützt werden oder aktiviert sind.  
  
-   `bindingConfiguration`. Müssen die Standardwerte einer Bindung geändert werden, kann dies geschehen, indem das entsprechende `binding` -Element im `bindings` -Element konfiguriert wird. Diesem Attribut sollte derselbe Wert zugewiesen werden, wie dem `name` -Attribut des `binding` -Elements, das verwendet wird, um die Standardwerte zu ändern. Wenn kein Name angegeben wird oder kein `bindingConfiguration` in der Bindung festgelegt ist, wird die Standardbindung des Bindungstyp im Endpunkt verwendet.  
  
-   `contract`. Gibt die Schnittstelle an, die den Vertrag definiert. Das ist die Schnittstelle, die im CLR-Typ (Common Language Runtime) implementiert ist, der vom `name` -Attribut des `service` -Elements angegeben wird.  
  
-   [\<Endpunkt >-Elementverweis](http://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017)  
  
### <a name="the-bindings-element"></a>Die \<Bindings >-Element  
 Das `bindings` -Element enthält die Spezifikationen für alle Bindungen, die von jedem in einem Dienst definierten Endpunkt verwendet werden können.  
  
 [\<bindings>](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)  
  
### <a name="the-binding-element"></a>Die \<Bindung >-Element  
 Das `binding` -Elemente, die im `bindings` -Element enthalten sind, können entweder eine der systemeigenen Bindungen (siehe [System-Provided Bindings](../../../docs/framework/wcf/system-provided-bindings.md)) oder eine benutzerdefinierte Bindung (siehe [Custom Bindings](../../../docs/framework/wcf/extending/custom-bindings.md)) sein. Das `binding` -Element verfügt über ein `name` -Attribut, das eine Beziehung zwischen der Bindung und dem Endpunkt herstellt, der im `bindingConfiguration` -Attribut des `endpoint` -Elements angegeben ist. Wenn kein Name angegeben wird, entspricht die Bindung der Standardbindung für diesen Bindungstyp.  
  
 [!INCLUDE[crabout](../../../includes/crabout-md.md)] Konfigurieren von Diensten und Clients, finden Sie unter [Konfigurieren von Windows Communication Foundation-Anwendungen](http://msdn.microsoft.com/library/13cb368e-88d4-4c61-8eed-2af0361c6d7a).  
  
 [\<binding>](../../../docs/framework/misc/binding.md)  
  
### <a name="the-behaviors-element"></a>Die \<Behaviors >-Element  
 Dies ist ein Containerelement für die `behavior` -Elemente, die das Verhalten eines Diensts definieren.  
  
 [\<behaviors>](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)  
  
### <a name="the-behavior-element"></a>Die \<Verhalten >-Element  
 Jedes `behavior`-Element wird durch ein `name`-Attribut identifiziert und stellt entweder ein vom System definiertes Verhalten, beispielsweise <`throttling`>, oder ein benutzerdefiniertes Verhalten bereit. Wenn kein Name angegeben wird, entspricht dieses Verhaltenselement dem standardmäßigen Dienst- oder Endpunktverhalten.  
  
 [\<behavior>](../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md)  
  
## <a name="how-to-use-binding-and-behavior-configurations"></a>Gewusst wie: Verwenden von Bindungs- und Verhaltenskonfigurationen  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] macht es mithilfe eines Verweissystems in der Konfiguration leicht, dass Endpunkte die gleiche Konfiguration verwenden können. Statt einem Endpunkt direkt Konfigurationswerte zuzuweisen, werden bindungsrelevante Konfigurationswerte in `bindingConfiguration` -Elementen des `<binding>` -Abschnitts gruppiert. Eine Bindungskonfiguration ist eine benannte Gruppe von Einstellungen einer Bindung. Endpunkte können dann mithilfe des Namens auf eine `bindingConfiguration` verweisen.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
 <system.serviceModel>  
  <bindings>  
    <basicHttpBinding>  
     <binding name="myBindingConfiguration1" closeTimeout="00:01:00" />  
     <binding name="myBindingConfiguration2" closeTimeout="00:02:00" />  
     <binding closeTimeout="00:03:00" />  <!—- Default binding for basicHttpBinding -->  
    </basicHttpBinding>  
     </bindings>  
     <services>  
      <service name="MyNamespace.myServiceType">  
       <endpoint   
          address="myAddress" binding="basicHttpBinding"   
          bindingConfiguration="myBindingConfiguration1"  
          contract="MyContract"  />  
       <endpoint   
          address="myAddress2" binding="basicHttpBinding"   
          bindingConfiguration="myBindingConfiguration2"  
          contract="MyContract" />  
       <endpoint   
          address="myAddress3" binding="basicHttpBinding"   
          contract="MyContract" />  
       </service>  
      </services>  
    </system.serviceModel>  
</configuration>  
```  
  
 Das `name` -Attribut der `bindingConfiguration` wird im `<binding>` -Element festgelegt. Die `name` muss eine eindeutige Zeichenfolge im Bereich des Bindungstyps sein – in diesem Fall die [< BasicHttpBinding\>](../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md), oder ein leerer Wert, um auf die standardbindung zu verweisen. Der Endpunkt wird mit der Konfiguration verknüpft, indem das `bindingConfiguration` -Attribut auf diese Zeichenfolge festgelegt wird.  
  
 Eine `behaviorConfiguration` wird genauso implementiert, wie das folgende Beispiel zeigt.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="myBehavior">  
           <callbackDebug includeExceptionDetailInFaults="true" />  
         </behavior>  
      </endpointBehaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="true" />  
        </behavior>  
      </serviceBehaviors>  
  
    </behaviors>  
    <services>  
     <service name="NewServiceType">  
       <endpoint   
          address="myAddress3" behaviorConfiguration="myBehavior"  
          binding="basicHttpBinding"  
          contract="MyContract" />  
      </service>  
    </services>  
   </system.serviceModel>  
</configuration>  
```  
  
 Beachten Sie, dass dem Dienst der Standardsatz von Dienstverhalten hinzugefügt wird. Dieses System ermöglicht es Endpunkten, allgemeine Konfigurationen gemeinsam zu verwenden, ohne dass die Einstellungen neu definiert werden müssen. Wenn ein computerweiter Bereich erforderlich ist, erstellen Sie die Bindungs- oder Verhaltenskonfiguration in Machine.config. Die Konfigurationseinstellungen sind in allen App.config-Dateien verfügbar. Das [Configuration Editor Tool (SvcConfigEditor.exe)](../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) macht es leicht, Konfigurationen zu erstellen.  
  
## <a name="behavior-merge"></a>Verhaltenszusammenführung  
 Die Funktion der Verhaltenszusammenführung erleichtert die Verwaltung von Verhalten, wenn eine Reihe allgemeiner Verhalten einheitlich verwendet werden soll. Mithilfe dieser Funktion können Sie Verhalten auf verschiedenen Ebenen der Konfigurationshierarchie angeben und festlegen, dass Dienste Verhalten von verschiedenen Ebenen der Konfigurationshierarchie erben sollen. Dies soll im Folgenden veranschaulicht werden. Angenommen, in IIS ist das folgende Layout virtueller Verzeichnisse gegeben:  
  
 ~\Web.config~\Service.svc~\Child\Web.config~\Child\Service.svc  
  
 Die Datei ~\Web.config hat folgenden Inhalt:  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceDebug includeExceptionDetailInFaults="True" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
 Außerdem ist eine untergeordnete Datei Web.config mit folgendem Inhalt unter ~\Child\Web.config vorhanden:  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
 Der Dienst unter ~\Child\Service.svc wird sowohl das serviceDebug-Verhalten als auch das serviceMetadata-Verhalten berücksichtigen. Der Dienst unter ~\Service.svc berücksichtigt lediglich das serviceDebug-Verhalten. Die beiden Verhaltensauflistungen mit demselben Namen (in diesem Fall einer leeren Zeichenfolge) werden zusammengeführt.  
  
 Sie können verhaltensauflistungen auch löschen, indem die \<deaktivieren >-Tag oder einzelne Verhaltensweisen aus der Auflistung mithilfe der \<entfernen > Tag. Die folgenden beiden Konfigurationen führen beispielsweise dazu, dass der untergeordnete Dienst lediglich das serviceMetadata-Verhalten verwendet:  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <remove name="serviceDebug"/>  
          <serviceMetadata httpGetEnabled="True" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <clear/>  
          <serviceMetadata httpGetEnabled="True" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
 Die Verhaltenszusammenführung erfolgt für unbenannte Verhaltensauflistungen (wie oben veranschaulicht) sowie für benannte Verhaltensauflistungen.  
  
 Die Verhaltenszusammenführung wird in der IIS-Hostingumgebung unterstützt, in der Web.config-Dateien hierarchisch mit den Stammdateien Web.config und machine.config zusammengeführt werden. Sie funktioniert jedoch auch in der Anwendungsumgebung, in der machine.config mit der Datei App.config zusammengeführt werden kann.  
  
 Die Verhaltenszusammenführung wird sowohl auf Endpunktverhalten als auch auf Dienstverhalten in der Konfiguration angewendet.  
  
 Wenn eine untergeordnete Verhaltensauflistung ein Verhalten enthält, das bereits in der übergeordneten Verhaltensauflistung enthalten ist, wird das übergeordnete Verhalten vom untergeordneten überschrieben. Wenn eine übergeordnete verhaltensauflistung `<serviceMetadata httpGetEnabled="False" />` und eine untergeordnete verhaltensauflistung `<serviceMetadata httpGetEnabled="True" />`, überschreibt das untergeordnete Verhalten das übergeordnete Verhalten in der verhaltensauflistung, und HttpGetEnabled wird auf "true".  
  
## <a name="see-also"></a>Siehe auch  
 [Vereinfachte Konfiguration](../../../docs/framework/wcf/simplified-configuration.md)  
 [Konfigurieren von Windows Communication Foundation-Anwendungen](http://msdn.microsoft.com/library/13cb368e-88d4-4c61-8eed-2af0361c6d7a)  
 [\<service>](../../../docs/framework/configure-apps/file-schema/wcf/service.md)  
 [\<binding>](../../../docs/framework/misc/binding.md)
