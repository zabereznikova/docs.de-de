---
title: Konfigurieren von Diensten mit Konfigurationsdateien
ms.date: 03/30/2017
helpviewer_keywords:
- configuring services [WCF]
ms.assetid: c9c8cd32-2c9d-4541-ad0d-16dff6bd2a00
ms.openlocfilehash: 29792726567373c907898cf6ced9891577f11588
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141629"
---
# <a name="configuring-services-using-configuration-files"></a>Konfigurieren von Diensten mit Konfigurationsdateien
Wenn Sie einen Windows Communication Foundation (WCF)-Dienst mit einer Konfigurationsdatei konfigurieren, haben Sie die Flexibilität, Endpunkt-und Dienst Verhaltensdaten zum Zeitpunkt der Bereitstellung statt zur Entwurfszeit bereitzustellen. Dieses Thema beschreibt die dafür verfügbaren grundlegenden Verfahren.  
  
 Ein WCF-Dienst kann mit der .NET Framework-Konfigurations Technologie konfiguriert werden. In den meisten Fällen werden XML-Elemente der Datei "Web. config" für eine Internetinformationsdienste (IIS)-Website hinzugefügt, die einen WCF-Dienst hostet. Mithilfe der Elemente können Sie Details ändern, zum Beispiel die Endpunktadressen (die eigentlichen für die Kommunikation mit dem Dienst verwendeten Adressen) für einzelne Computer. Außerdem umfasst WCF mehrere vom System bereitgestellte Elemente, mit denen Sie schnell die grundlegendsten Features für einen Dienst auswählen können. Ab .NET Framework 4 enthält WCF ein neues Standard Konfigurations Modell, das die WCF-Konfigurations Anforderungen vereinfacht. Wenn Sie keine WCF-Konfiguration für einen bestimmten Dienst bereitstellen, konfiguriert die Runtime den Dienst automatisch mit einigen Standard Endpunkten und der Standard Bindung/dem Standardverhalten. In der Praxis ist das Schreiben von Konfigurationen ein wesentlicher Bestandteil der Programmierung von WCF-Anwendungen.  
  
 Weitere Informationen finden Sie unter [Konfigurieren von Bindungen für Dienste](configuring-bindings-for-wcf-services.md). Eine Liste der am häufigsten verwendeten Elemente finden Sie unter vom [System bereitgestellte Bindungen](system-provided-bindings.md). Weitere Informationen über Standardendpunkte, Bindungen und Verhalten finden Sie unter [Simplified Configuration (Vereinfachte Konfiguration)](simplified-configuration.md) und [Simplified Configuration for WCF Services (Vereinfachte Konfiguration für WCF-Dienste)](./samples/simplified-configuration-for-wcf-services.md).  
  
> [!IMPORTANT]
> Beim Bereitstellen paralleler Szenarien, in denen zwei verschiedene Versionen eines Diensts bereitgestellt werden, müssen bei Verweisen in Konfigurationsdateien partielle Assemblynamen angegeben werden. Dies liegt daran, dass die Konfigurationsdatei gemeinsam von allen Versionen eines Diensts verwendet wird und dass diese Dienste ggf. unter unterschiedlichen Versionen von .NET Framework ausgeführt werden.  
  
## <a name="systemconfiguration-webconfig-and-appconfig"></a>System.Configuration: Web.config und App.config  
 WCF verwendet das System. Configuration-Konfigurationssystem der .NET Framework.  
  
 Verwenden Sie beim Konfigurieren eines Diensts in Visual Studio entweder eine Web. config-Datei oder eine APP. config-Datei, um die Einstellungen anzugeben. Die Wahl der Konfigurationsdatei wird durch die Hostumgebung des Diensts bestimmt. Wenn Sie den Dienst in IIS hosten, verwenden Sie eine Web.config-Datei. Bei einer anderen Hostumgebung verwenden Sie eine App.config-Datei.  
  
 In Visual Studio wird die Datei mit dem Namen "App. config" zum Erstellen der endgültigen Konfigurationsdatei verwendet. Der tatsächlich für die Konfigurationsdatei verwendete Name hängt vom Assemblynamen ab. Einer Assembly mit dem Namen "Cohowinery.exe" ist beispielsweise die Konfigurationsdatei namens "Cohowinery.exe.config" zugeordnet. Sie müssen jedoch nur die Datei App.config ändern. An dieser Datei vorgenommene Änderungen werden bei der Kompilierung automatisch an die tatsächliche Anwendungskonfigurationsdatei weitergegeben.  
  
 Bei Verwendung einer App.config-Datei führt das Konfigurationssystem den Inhalt dieser Datei mit dem Inhalt der Datei Machine.config zusammen, sobald die Anwendung gestartet und die Konfiguration übernommen wird. Dieser Mechanismus ermöglicht es, computerweite Einstellungen in der Datei Machine.config zu definieren. Die Datei App.config kann verwendet werden, um Einstellungen in der Datei Machine.config zu überschreiben. Sie können Einstellungen in der Datei Machine.config aber auch sperren, sodass diese verwendet werden. Im Fall der Datei Web.config führt das Konfigurationssystem den Inhalt aller Web.config-Dateien in allen Verzeichnissen zur schließlich verwendeten Konfiguration im Anwendungsverzeichnis zusammen. Weitere Informationen zur Konfiguration und zu den Prioritäts Einstellungen finden Sie in den Themen im <xref:System.Configuration>-Namespace.  
  
## <a name="major-sections-of-the-configuration-file"></a>Hauptabschnitte der Konfigurationsdatei  
 Die Hauptabschnitte der Konfigurationsdatei umfassen folgende Elemente:  
  
```xml  
<system.ServiceModel>  
  
   <services>  
   <!-- Define the service endpoints. This section is optional in the new  
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
> Die Bindungs- und Verhaltensabschnitte sind optional und nur bei Bedarf enthalten.  
  
### <a name="the-services-element"></a>Das \<Services-> Element  
 Das `services` -Element enthält die Spezifikationen aller Dienste, die die Anwendung hostet. Ab dem vereinfachten Konfigurations Modell in .NET Framework 4 ist dieser Abschnitt optional.  
  
 [\<Dienste >](../configure-apps/file-schema/wcf/services.md)  
  
### <a name="the-service-element"></a>Das \<Service >-Element  
 Jeder Dienst verfügt über diese Attribute:  
  
- `name` Gibt den Typ an, der eine Implementierung eines Dienstvertrags bereitstellt. Dies ist ein vollqualifizierter Name, der aus dem Namespace und einem Punkt gefolgt von dem Typnamen besteht. Beispiel: `"MyNameSpace.myServiceType"`.  
  
- `behaviorConfiguration` Gibt den Namen eines `behavior` -Elements an, das im `behaviors` -Element gefunden wurde. Das angegebene Verhalten steuert Aktionen, beispielsweise ob der Dienst Identitätswechsel erlaubt. Wenn der Wert ein leerer Name oder kein `behaviorConfiguration` ist, wird dem Dienst der Standardsatz von Dienstverhalten hinzugefügt.  
  
- [\<Dienst >](../configure-apps/file-schema/wcf/service.md)  
  
### <a name="the-endpoint-element"></a>Das > Element des \<Endpunkts.  
 Jeder Endpunkt benötigt eine Adresse, eine Bindung und einen Vertrag. Diese Elemente werden durch die folgenden Attribute dargestellt:  
  
- `address` Gibt den Uniform Resource Identifier (URI) des Diensts an. Er kann als absolute Adresse oder als eine zur Basisadresse des Diensts relative Adresse angegeben werden. Eine leere Zeichenfolge zeigt an, dass der Endpunkt unter der Basisadresse verfügbar ist. Diese Basisadresse wird bei der Erstellung des <xref:System.ServiceModel.ServiceHost> für den Dienst angegeben.  
  
- `binding` Gibt üblicherweise eine vom System bereitgestellte Bindung, beispielsweise <xref:System.ServiceModel.WSHttpBinding>an, kann aber auch eine benutzerdefinierte Bindung angeben. Die angegebene Bindung bestimmt, welcher Typ von Transport, Sicherheit und Codierung verwendet wird, und ob zuverlässige Sitzungen, Transaktionen oder Streaming unterstützt werden oder aktiviert sind.  
  
- `bindingConfiguration` Müssen die Standardwerte einer Bindung geändert werden, kann dies geschehen, indem das entsprechende `binding` -Element im `bindings` -Element konfiguriert wird. Diesem Attribut sollte derselbe Wert zugewiesen werden, wie dem `name` -Attribut des `binding` -Elements, das verwendet wird, um die Standardwerte zu ändern. Wenn kein Name angegeben wird oder kein `bindingConfiguration` in der Bindung festgelegt ist, wird die Standardbindung des Bindungstyp im Endpunkt verwendet.  
  
- `contract` Gibt die Schnittstelle an, die den Vertrag definiert. Das ist die Schnittstelle, die im CLR-Typ (Common Language Runtime) implementiert ist, der vom `name` -Attribut des `service` -Elements angegeben wird.  
  
- [\<Endpunkt >](../configure-apps/file-schema/wcf/endpoint-element.md)  
  
### <a name="the-bindings-element"></a>Das \<-Bindungs > Element  
 Das `bindings` -Element enthält die Spezifikationen für alle Bindungen, die von jedem in einem Dienst definierten Endpunkt verwendet werden können.  
  
 [\<Bindungen >](../configure-apps/file-schema/wcf/bindings.md)  
  
### <a name="the-binding-element"></a>Das \<Bindungs > Element  
 Das `binding` -Elemente, die im `bindings` -Element enthalten sind, können entweder eine der systemeigenen Bindungen (siehe [System-Provided Bindings](system-provided-bindings.md)) oder eine benutzerdefinierte Bindung (siehe [Custom Bindings](./extending/custom-bindings.md)) sein. Das `binding` -Element verfügt über ein `name` -Attribut, das eine Beziehung zwischen der Bindung und dem Endpunkt herstellt, der im `bindingConfiguration` -Attribut des `endpoint` -Elements angegeben ist. Wenn kein Name angegeben wird, entspricht die Bindung der Standardbindung für diesen Bindungstyp.  
  
Weitere Informationen zum Konfigurieren von Diensten und Clients finden Sie unter [Konfigurieren von WCF-Diensten](configuring-services.md).
  
 [\<Bindungs >](../configure-apps/file-schema/wcf/bindings.md)  
  
### <a name="the-behaviors-element"></a>Das \<Verhalten > Element  
 Dies ist ein Containerelement für die `behavior` -Elemente, die das Verhalten eines Diensts definieren.  
  
 [\<Verhalten >](../configure-apps/file-schema/wcf/behaviors.md)  
  
### <a name="the-behavior-element"></a>Das \<Verhalten > Element  
 Jedes `behavior` Element wird durch ein `name` Attribut identifiziert und stellt entweder ein vom System bereitgestelltes Verhalten dar, z. b. <`throttling`> oder ein benutzerdefiniertes Verhalten. Wenn kein Name angegeben wird, entspricht dieses Verhaltenselement dem standardmäßigen Dienst- oder Endpunktverhalten.  
  
 [\<Verhalten >](../configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md)  
  
## <a name="how-to-use-binding-and-behavior-configurations"></a>Gewusst wie: Verwenden von Bindungs- und Verhaltenskonfigurationen  
 WCF vereinfacht das Freigeben von Konfigurationen zwischen Endpunkten mithilfe eines Referenzsystems in der Konfiguration. Statt einem Endpunkt direkt Konfigurationswerte zuzuweisen, werden bindungsrelevante Konfigurationswerte in `bindingConfiguration` -Elementen des `<binding>` -Abschnitts gruppiert. Eine Bindungskonfiguration ist eine benannte Gruppe von Einstellungen einer Bindung. Endpunkte können dann mithilfe des Namens auf eine `bindingConfiguration` verweisen.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
 <system.serviceModel>  
  <bindings>  
    <basicHttpBinding>  
     <binding name="myBindingConfiguration1" closeTimeout="00:01:00" />  
     <binding name="myBindingConfiguration2" closeTimeout="00:02:00" />  
     <binding closeTimeout="00:03:00" />  <!-- Default binding for basicHttpBinding -->  
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
  
 Das `name` -Attribut der `bindingConfiguration` wird im `<binding>` -Element festgelegt. Der `name` muss eine eindeutige Zeichenfolge im Bereich des Bindungs Typs sein – in diesem Fall das [< BasicHttpBinding-\>](../configure-apps/file-schema/wcf/basichttpbinding.md)oder ein leerer Wert, um auf die Standard Bindung zu verweisen. Der Endpunkt wird mit der Konfiguration verknüpft, indem das `bindingConfiguration` -Attribut auf diese Zeichenfolge festgelegt wird.  
  
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
  
 Beachten Sie, dass dem Dienst der Standardsatz von Dienstverhalten hinzugefügt wird. Dieses System ermöglicht es Endpunkten, allgemeine Konfigurationen gemeinsam zu verwenden, ohne dass die Einstellungen neu definiert werden müssen. Wenn ein Computer weiter Bereich erforderlich ist, erstellen Sie die Bindungs-oder Verhaltens Konfiguration in Machine. config. Die Konfigurationseinstellungen sind in allen APP. config-Dateien verfügbar. Das [Configuration Editor Tool (SvcConfigEditor.exe)](configuration-editor-tool-svcconfigeditor-exe.md) macht es leicht, Konfigurationen zu erstellen.  
  
## <a name="behavior-merge"></a>Verhaltenszusammenführung  
 Die Funktion der Verhaltenszusammenführung erleichtert die Verwaltung von Verhalten, wenn eine Reihe allgemeiner Verhalten einheitlich verwendet werden soll. Mithilfe dieser Funktion können Sie Verhalten auf verschiedenen Ebenen der Konfigurationshierarchie angeben und festlegen, dass Dienste Verhalten von verschiedenen Ebenen der Konfigurationshierarchie erben sollen. Dies soll im Folgenden veranschaulicht werden. Angenommen, in IIS ist das folgende Layout virtueller Verzeichnisse gegeben:  
  
 `~\Web.config~\Service.svc~\Child\Web.config~\Child\Service.svc`
  
 Und ihre `~\Web.config` Datei hat folgenden Inhalt:  
  
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
  
 Sie können Verhaltens Auflistungen auch löschen, indem Sie die \<> Tag löschen und einzelne Verhalten aus der Auflistung entfernen, indem Sie das \<> Tag entfernen verwenden. Die folgenden beiden Konfigurationen führen beispielsweise dazu, dass der untergeordnete Dienst lediglich das serviceMetadata-Verhalten verwendet:  
  
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
  
 Die Verhaltens Zusammenführung funktioniert in der IIS-Hostingumgebung, in der Web. config-Dateien hierarchisch mit der Web. config-Stammdatei und Machine. config zusammengeführt werden. Sie funktioniert jedoch auch in der Anwendungsumgebung, in der Machine. config mit der Datei app. config zusammengeführt werden kann.  
  
 Die Verhaltenszusammenführung wird sowohl auf Endpunktverhalten als auch auf Dienstverhalten in der Konfiguration angewendet.  
  
 Wenn eine untergeordnete Verhaltensauflistung ein Verhalten enthält, das bereits in der übergeordneten Verhaltensauflistung enthalten ist, wird das übergeordnete Verhalten vom untergeordneten überschrieben. Wenn also eine übergeordnete Verhaltens Auflistung `<serviceMetadata httpGetEnabled="False" />` und eine untergeordnete Verhaltens Auflistung `<serviceMetadata httpGetEnabled="True" />`hatte, überschreibt das untergeordnete Verhalten das übergeordnete Verhalten in der Verhaltens Auflistung, und HttpGetEnabled wäre "true".  
  
## <a name="see-also"></a>Siehe auch

- [Vereinfachte Konfiguration](simplified-configuration.md)
- [Konfigurieren von WCF-Diensten](configuring-services.md)
- [\<Dienst >](../configure-apps/file-schema/wcf/service.md)
- [\<Bindungs >](../configure-apps/file-schema/wcf/bindings.md)
