---
title: Vorgangsformatierer und Vorgangsauswahl
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1c27e9fe-11f8-4377-8140-828207b98a0e
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a10be10687f03b5de45846faa9ca832ead193e19
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="operation-formatter-and-operation-selector"></a>Vorgangsformatierer und Vorgangsauswahl
Dieses Beispiel zeigt, wie [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Erweiterungspunkte verwendet werden können, um Nachrichtendaten in einem anderen Format als in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] erwartet zuzulassen. Standardmäßig erwarten [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Formatierer, dass Methodenparameter unter dem `soap:body`-Element enthalten sind. Das Beispiel zeigt, wie ein benutzerdefinierter Vorgangsformatierer implementiert wird, der Parameterdaten aus einer HTTP-GET-Abfragezeichenfolge stattdessen analysiert und mit diesen Daten dann Methoden aufruft.  
  
 Das Beispiel basiert auf der [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md), implementiert die `ICalculator` Dienstvertrag. Es zeigt, wie Add-, Subtract-, Multiply- und Divide-Nachrichten so geändert werden können, dass für Client-an-Server-Anforderungen HTTP GET und für Server-zu-Client-Antworten HTTP POST mit POX-Nachrichten verwendet werden.  
  
 Zu diesem Zweck enthält das Beispiel Folgendes:  
  
-   `QueryStringFormatter`, der <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> und <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter> für den Client bzw. den Server implementiert und die Daten in der Abfragezeichenfolge verarbeitet.  
  
-   `UriOperationSelector`, die <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> auf dem Server implementiert, um die Vorgangsverteilung anhand des Vorgangsnamens in der GET-Anforderung zu verteilen.  
  
-   `EnableHttpGetRequestsBehavior`-Endpunktverhalten (und entsprechende Konfiguration), das die erforderliche Vorgangsauswahl der Laufzeit hinzufügt.  
  
-   Zeigt, wie ein neuer Vorgangsformatierer in die Laufzeit eingefügt wird.  
  
-   In diesem Beispiel sind sowohl der Client als auch der Dienst Konsolenanwendungen (.exe).  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
## <a name="key-concepts"></a>Grundbegriffe  
 `QueryStringFormatter` - Der Vorgangsformatierer ist die Komponente in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], die für das Umwandeln einer Nachricht in ein Array von Parameterobjekten und eines Arrays von Parameterobjekten in eine Nachricht verantwortlich ist. Auf dem Client erfolgt dies mithilfe der <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter>-Schnittstelle, und auf dem Server mit der <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter>-Schnittstelle. Mit diesen Schnittstellen können Benutzer die Anforderungs- und Antwortnachrichten aus der `Serialize`-Methode und der `Deserialize`-Methode abrufen.  
  
 In diesem Beispiel implementiert `QueryStringFormatter` beide Schnittstellen und wird sowohl auf dem Client als auch auf dem Server implementiert.  
  
 Anforderung:  
  
-   Das Beispiel verwendet die <xref:System.ComponentModel.TypeConverter>-Klasse, um Parameterdaten in der Anforderungsnachricht in und aus Zeichenfolgen zu konvertieren. Wenn ein <xref:System.ComponentModel.TypeConverter> für einen bestimmten Typ nicht verfügbar ist, löst der Beispielformatierer eine Ausnahme aus.  
  
-   In der `IClientMessageFormatter.SerializeRequest`-Methode auf dem Client erstellt der Formatierer einen URI mit der entsprechenden Empfängeradresse und fügt den Vorgangsnamen als Suffix an. Dieser Name dient dann zum Verteilen zum entsprechenden Vorgang auf dem Server. Dann nimmt er das Array mit Parameterobjekten und serialisiert die Parameterdaten mithilfe von Parameternamen und den von der <xref:System.ComponentModel.TypeConverter>-Klasse konvertierten Werten in die URI-Abfragezeichenfolge. Die <xref:System.ServiceModel.Channels.MessageHeaders.To%2A>-Eigenschaft und die <xref:System.ServiceModel.Channels.MessageProperties.Via%2A>-Eigenschaft werden dann auf diesen URI festgelegt. Auf <xref:System.ServiceModel.Channels.MessageProperties> wird über die <xref:System.ServiceModel.Channels.Message.Properties%2A>-Eigenschaft zugegriffen.  
  
-   In der `IDispatchMessageFormatter.DeserializeRequest`-Methode auf dem Server ruft der Formatierer den `Via`-URI in den Eigenschaften der eingehenden Anforderungsnachricht ab. Er analysiert die Name-Wert-Paare in der URI-Abfragezeichenfolge in Parameternamen und Werte und füllt mit diesen Parameternamen und Werten das an die Methode übergebene Parameterarray auf. Beachten Sie, dass die Vorgangsverteilung bereits stattgefunden hat; daher wird das Namenssuffix in dieser Methode ignoriert.  
  
 Antwort:  
  
-   In diesem Beispiel wird HTTP GET nur für die Anforderung verwendet. Der Formatierer delegiert das Senden der Antwort an den ursprünglichen Formatierer, von dem XML-Nachrichten generiert worden wären. Eines der Ziele dieses Beispiels besteht darin, zu zeigen, wie solch ein delegierender Formatierer implementiert werden kann.  
  
### <a name="uripathsuffixoperationselector-class"></a>UriPathSuffixOperationSelector-Klasse  
 Mit der <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector>-Schnittstelle können Benutzer ihre eigene Logik für die Entscheidung implementieren, für welchen Vorgang eine bestimmte Nachricht weitergeleitet werden soll.  
  
 In diesem Beispiel muss `UriPathSuffixOperationSelector` zum Auswählen des entsprechenden Vorgangs auf dem Server implementiert werden, da anstelle eines Aktionsheaders in der Nachricht der Vorgangsname in dem HTTP-GET-URI eingetragen wird. Das Beispiel ist so eingerichtet, dass bei Vorgangsnamen die Groß- und Kleinschreibung nicht beachtet werden muss.  
  
 Die `SelectOperation`-Methode nimmt die eingehende Nachricht entgegen und schlägt den `Via`-URI in deren Nachrichteneigenschaften nach. Sie extrahiert das Vorgangsnamenssuffix aus dem URI, schlägt in einer internen Tabelle den Namen des Vorgangs nach, an den die Nachricht weitergeleitet werden soll, und gibt diesen Vorgangsnamen dann zurück.  
  
### <a name="enablehttpgetrequestsbehavior-class"></a>EnableHttpGetRequestsBehavior-Klasse  
 Die `UriPathSuffixOperationSelector`-Komponente kann programmgesteuert oder über ein Endpunktverhalten eingerichtet werden. Das Beispiel implementiert das `EnableHttpGetRequestsBehavior`-Verhalten, das in der Anwendungskonfigurationsdatei des Diensts angegeben wird.  
  
 Auf dem Server:  
  
 Der <xref:System.ServiceModel.Dispatcher.DispatchRuntime.OperationSelector%2A> wird auf die <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector>-Implementierung festgelegt.  
  
 Standardmäßig verwendet [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] einen Adressfilter mit exakter Übereinstimmung. Der URI in der eingehenden Nachricht enthält ein Vorgangsnamenssuffix, gefolgt von einer Abfragezeichenfolge, die Parameterdaten enthält. Daher ändert das Endpunktverhalten auch den Adressfilter in einen Präfixübereinstimmungsfilter. Er verwendet die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] <xref:System.ServiceModel.Dispatcher.PrefixEndpointAddressMessageFilter> für diesen Zweck.  
  
### <a name="installing-operation-formatters"></a>Installieren von Vorgangsformatierern  
 Vorgangsverhaltensweisen, die Formatierer angeben, sind eindeutig. Standardmäßig wird ein solches Verhalten für jeden Vorgang stets zum Erstellen des erforderlichen Vorgangsformatierers implementiert. Auch wenn diese Verhaltensweisen wie noch ein weiteres Vorgangsverhalten aussehen mögen, sind sie nicht durch andere Attribute zu identifizieren. Zum Installieren eines Ersatzverhaltens muss die Implementierung zuerst nach speziellen, vom [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Typladeprogramm standardmäßig installierten Formatiererverhalten suchen, und das dann entweder ersetzen oder ein kompatibles Verhalten so hinzufügen, dass es nach dem Standardverhalten ausgeführt wird.  
  
 Diese Vorgangsformatiererverhalten können programmgesteuert vor dem Aufruf von <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A?displayProperty=nameWithType> eingerichtet werden, oder indem man ein Vorgangsverhalten angibt, das nach dem Standardverhalten ausgeführt wird. Es kann jedoch nicht einfach wie ein Endpunktverhalten (und damit per Konfiguration) eingerichtet werden, da das Verhaltensmodell das Ersetzen eines Verhaltens durch ein anderes oder sonstiges Ändern der Beschreibungsstruktur nicht zulässt.  
  
 Auf dem Client:  
  
 Die <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter>-Implementierung muss implementiert werden, damit sie die Anforderungen in HTTP-GET-Anforderungen konvertieren und für Antworten an den ursprünglichen Formatierer delegieren kann. Dies erfolgt durch Aufrufen der `EnableHttpGetRequestsBehavior.ReplaceFormatterBehavior`-Hilfsmethode.  
  
 Es muss vor dem Aufruf von `CreateChannel` durchgeführt werden.  
  
```  
void ReplaceFormatterBehavior(OperationDescription operationDescription, EndpointAddress address)  
{  
    // Remove the DataContract behavior if it is present.  
    IOperationBehavior formatterBehavior = operationDescription.Behaviors.Remove<DataContractSerializerOperationBehavior>();  
    if (formatterBehavior == null)  
    {  
        // Remove the XmlSerializer behavior if it is present.  
        formatterBehavior = operationDescription.Behaviors.Remove<XmlSerializerOperationBehavior>();  
        ...  
    }  
  
    // Remember what the innerFormatterBehavior was.  
    DelegatingFormatterBehavior delegatingFormatterBehavior = new DelegatingFormatterBehavior(address);  
    delegatingFormatterBehavior.InnerFormatterBehavior = formatterBehavior;  
   operationDescription.Behaviors.Add(delegatingFormatterBehavior);  
}  
```  
  
 Auf dem Server:  
  
-   Die <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter>-Schnittstelle muss implementiert werden, damit sie HTTP-GET-Anforderungen lesen und zum Schreiben von Antworten an den ursprünglichen Formatierer delegieren kann. Dies erfolgt durch Aufrufen derselben `EnableHttpGetRequestsBehavior.ReplaceFormatterBehavior`-Hilfsmethode wie beim Client (siehe vorheriges Codebeispiel).  
  
-   Das muss erfolgen, bevor <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> aufgerufen wird. In diesem Beispiel wird gezeigt, wie der Formatierer manuell geändert wird, bevor <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> aufgerufen wird. Dasselbe lässt sich auch erreichen, indem man eine Klasse von <xref:System.ServiceModel.ServiceHost> ableitet, die vor dem Öffnen `EnableHttpGetRequestsBehavior.ReplaceFormatterBehavior` aufruft (Beispiel dazu finden Sie in der Hostingdokumentation).  
  
### <a name="user-experience"></a>Benutzerfreundlichkeit  
 Auf dem Server:  
  
-   Die `ICalculator`-Serverimplementierung muss nicht geändert werden.  
  
-   Die App.config-Datei für den Dienst muss eine benutzerdefinierte POX-Bindung verwenden, die für das `messageVersion`-Attribut des `textMessageEncoding`-Elements `None` festlegt.  
  
    ```xml  
    <bindings>  
      <customBinding>  
        <binding name="poxBinding">  
          <textMessageEncoding messageVersion="None" />  
          <httpTransport />  
        </binding>  
      </customBinding>  
    </bindings>  
    ```  
  
-   Außerdem muss die App.config-Datei für den Dienst das benutzerdefinierte `EnableHttpGetRequestsBehavior` angeben, indem sie es dem Abschnitt mit den Verhaltenserweiterungen hinzufügt und verwendet.  
  
    ```xml  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="enableHttpGetRequestsBehavior">  
          <enableHttpGetRequests />  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
  
    <extensions>  
      <behaviorExtensions>  
        <!-- Enabling HTTP GET requests: Behavior Extension -->  
        <add   
          name="enableHttpGetRequests"           type="Microsoft.ServiceModel.Samples.EnableHttpGetRequestsBehaviorElement, QueryStringFormatter, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
      </behaviorExtensions>  
    </extensions>  
    ```  
  
-   Fügen Sie Vorgangsformatierer vor dem Aufrufen von <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> hinzu.  
  
 Auf dem Client:  
  
-   Die Clientimplementierung muss nicht geändert werden.  
  
-   Die App.config-Datei für den Client muss eine benutzerdefinierte POX-Bindung verwenden, die für das `messageVersion`-Attribut des `textMessageEncoding`-Elements `None` festlegt. Ein Unterschied zum Dienst besteht darin, dass der Client die manuelle Adressierung aktivieren muss, damit die Empfängeradresse der ausgehenden Nachricht geändert werden kann.  
  
    ```xml  
    <bindings>  
      <customBinding>  
        <binding name="poxBinding">  
          <textMessageEncoding messageVersion="None" />  
          <httpTransport manualAddressing="True" />  
        </binding>  
      </customBinding>  
    </bindings>  
    ```  
  
-   Die App.config für den Client muss dasselbe benutzerdefinierte `EnableHttpGetRequestsBehavior` wie der Server angeben.  
  
-   Fügen Sie Vorgangsformatierer vor dem Aufrufen von <xref:System.ServiceModel.ChannelFactory%601.CreateChannel> hinzu.  
  
 Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt. Alle vier Vorgänge (Add, Subtract, Multiply und Divide) müssen erfolgreich sein.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Formatters\QuieryStringFormatter`  
  
##### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Stellen Sie sicher, dass Sie ausgeführt haben die [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Führen Sie zum Erstellen der Projektmappe die Anweisungen im [Erstellen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
## <a name="see-also"></a>Siehe auch
