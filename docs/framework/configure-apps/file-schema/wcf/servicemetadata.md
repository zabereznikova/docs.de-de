---
title: <serviceMetadata>
ms.date: 03/30/2017
ms.assetid: 2b4c3b4c-31d4-4908-a9b7-5bb411c221f2
ms.openlocfilehash: 0b06d61a33cd6a704a5ab0f75d29bde3f72d77fa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59115855"
---
# <a name="servicemetadata"></a>\<serviceMetadata>
Gibt die Veröffentlichung der Dienstmetadaten und der zugeordneten Informationen an.  
  
\<system.serviceModel>  
\<behaviors>  
\<serviceBehaviors>  
\<behavior>  
\<serviceMetadata>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<serviceMetadata externalMetadataLocation="String"
                 httpGetBinding="String"
                 httpGetBindingConfiguration="String"
                 httpGetEnabled="Boolean"
                 httpGetUrl="String"
                 httpsGetBinding="String"
                 httpsGetBindingConfiguration="String"
                 httpsGetEnabled="Boolean"
                 httpsGetUrl="String"
                 policyVersion="Policy12/Policy15" />
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|externalMetadataLocation|Ein URI, der den Speicherort einer WSDL-Datei enthält, die dem Benutzer als Antwort auf WSDL- und MEX-Anforderungen statt der automatisch generierten WSDL-Datei zurückgegeben wird. Wenn dieses Attribut nicht festgelegt wird, wird die WSDL-Standarddatei zurückgegeben. Der Standardwert ist eine leere Zeichenfolge.|  
|httpGetBinding|Eine Zeichenfolge, die den Typ der Bindung angibt, die für den Abruf von Metadaten mit HTTP GET verwendet wird. Diese Einstellung ist optional. Wenn nicht angegeben, werden die Standardbindungen verwendet.<br /><br /> Nur Bindungen mit inneren Bindungselementen, die <xref:System.ServiceModel.Channels.IReplyChannel> unterstützen, werden unterstützt. Darüber hinaus muss die <xref:System.ServiceModel.Channels.MessageVersion>-Eigenschaft der Bindung <xref:System.ServiceModel.Channels.MessageVersion.None%2A> lauten.|  
|httpGetBindingConfiguration|Eine Zeichenfolge mit dem Namen der Bindung, die im `httpGetBinding`-Attribut angegeben ist, das auf die zusätzlichen Konfigurationsinformationen dieser Bindung verweist. Der gleiche Name muss im Abschnitt `<bindings>` definiert werden.|  
|httpGetEnabled|Ein boolescher Wert, der angibt, ob die Dienstmetadaten zum Abrufen anhand einer HTTP/Get-Anforderung veröffentlicht werden sollen. Die Standardeinstellung ist `false`.<br /><br /> Falls das httpGetUrl-Attribut nicht angegeben ist, ist die Adresse, an der die Metadaten veröffentlicht werden, die Dienstadresse plus ein "?wsdl". Wenn die Dienstadresse beispielsweise "http://localhost:8080/CalculatorService", die HTTP/Get-Metadatenadresse"http://localhost:8080/CalculatorService?wsdl".<br /><br /> Wenn diese Eigenschaft `false`, oder die Adresse des Diensts basiert nicht auf HTTP oder HTTPS, "? Wsdl" ignoriert.|  
|httpGetUrl|Ein URI, der die Adresse angibt, an der die Metadaten zum Abrufen anhand einer HTTP/Get-Anforderung veröffentlicht werden. Wenn ein relativer URI angegeben ist, wird er als relativ zur Basisadresse des Diensts behandelt.|  
|httpsGetBinding|Eine Zeichenfolge, die den Typ der Bindung angibt, die für den Abruf von Metadaten mit HTTPS GET verwendet wird. Diese Einstellung ist optional. Wenn nicht angegeben, werden die Standardbindungen verwendet.<br /><br /> Nur Bindungen mit inneren Bindungselementen, die <xref:System.ServiceModel.Channels.IReplyChannel> unterstützen, werden unterstützt. Darüber hinaus muss die <xref:System.ServiceModel.Channels.MessageVersion>-Eigenschaft der Bindung <xref:System.ServiceModel.Channels.MessageVersion.None%2A> lauten.|  
|httpsGetBindingConfiguration|Eine Zeichenfolge mit dem Namen der Bindung, die im `httpsGetBinding`-Attribut angegeben ist, das auf die zusätzlichen Konfigurationsinformationen dieser Bindung verweist. Der gleiche Name muss im Abschnitt `<bindings>` definiert werden.|  
|httpsGetEnabled|Ein boolescher Wert, der angibt, ob die Dienstmetadaten zum Abrufen anhand einer HTTPS/Get-Anforderung veröffentlicht werden sollen. Die Standardeinstellung ist `false`.<br /><br /> Falls das httpsGetUrl-Attribut nicht angegeben ist, ist die Adresse, an der die Metadaten veröffentlicht werden, die Dienstadresse plus ein "?wsdl". Wenn die Dienstadresse beispielsweise "https://localhost:8080/CalculatorService", die HTTP/Get-Metadatenadresse"https://localhost:8080/CalculatorService?wsdl".<br /><br /> Wenn diese Eigenschaft `false`, oder die Adresse des Diensts basiert nicht auf HTTP oder HTTPS, "? Wsdl" ignoriert.|  
|httpsGetUrl|Ein URI, der die Adresse angibt, an der die Metadaten zum Abrufen anhand einer HTTPS/Get-Anforderung veröffentlicht werden.|  
|policyVersion|Eine Zeichenfolge, die angibt, welche Version der WS-Policy-Spezifikation verwendet wird. Dieses Attribut ist vom Typ <xref:System.ServiceModel.Description.PolicyVersion>.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keiner  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<behavior>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Gibt ein Verhaltenselement an.|  
  
## <a name="remarks"></a>Hinweise  
 Mit diesem Konfigurationselement können Sie die Metadatenveröffentlichungs-Funktionen eines Diensts steuern. Um unbeabsichtigtes Offenlegen sicherheitsrelevanter Dienstmetadaten zu verhindern, die Standardkonfiguration für Windows Communication Foundation (WCF)-Dienste die Metadatenveröffentlichung deaktiviert. Dieses Verhalten ist in der Standardeinstellung sicher, bedeutet aber auch, dass man den zum Aufrufen des Diensts erforderlichen Clientcode nicht mithilfe eines Tools zum Importieren von Metadaten (wie Svcutil.exe) generieren kann. Dies ist nur dann möglich, wenn das Verhalten des Diensts zum Veröffentlichen von Metadaten in der Konfiguration explizit aktiviert ist. Wenn Sie dieses Konfigurationselement verwenden, können Sie dieses Veröffentlichungsverhalten für Ihren Dienst aktivieren.  
  
 Ein ausführliches Beispiel für die Konfiguration dieses Verhaltens finden Sie unter [Metadatenveröffentlichungsverhalten](../../../../../docs/framework/wcf/samples/metadata-publishing-behavior.md).  
  
 Das optionale `httpGetBinding`-Attribut und `httpsGetBinding`-Attribut ermöglichen Ihnen das Konfigurieren der zum Abrufen der Metadaten über HTTP-GET (oder HTTPS-GET) verwendeten Bindungen. Wenn sie nicht festgelegt sind, werden die Standardbindungen (`HttpTransportBindingElement` für HTTP und `HttpsTransportBindingElement` für HTTPS) entsprechend zum Abrufen der Metadaten verwendet. Beachten Sie, dass Sie diese Attribute nicht mit den integrierten WCF-Bindungen verwenden können. Nur Bindungen mit inneren Bindungselementen, die <xref:System.ServiceModel.Channels.IReplyChannel> unterstützen, werden unterstützt. Darüber hinaus muss die <xref:System.ServiceModel.Channels.MessageVersion>-Eigenschaft der Bindung <xref:System.ServiceModel.Channels.MessageVersion.None%2A> lauten.  
  
 Damit der Dienst möglichst gut vor böswilligen Benutzern geschützt wird, können Sie für die Übertragung den HTTPS-Mechanismus (SSL über HTTP) verwenden. Hierfür müssen Sie zunächst ein geeignetes X.509-Zertifikat an einen bestimmten Port des Computers, auf dem der Dienst gehostet wird, binden. (Weitere Informationen finden Sie unter [arbeiten mit Zertifikaten](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).) Fügen Sie dann dieses Element der Dienstkonfiguration hinzu, und legen Sie für das `httpsGetEnabled`-Attribut den Wert `true` fest. Setzen Sie abschließend wie im folgenden Beispiel gezeigt das `httpsGetUrl`-Attribut auf den URL des Dienstmetadaten-Endpunkts:  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="NewBehavior">
      <serviceMetadata httpsGetEnabled="true"
                       httpsGetUrl="https://myComputerName/myEndpoint" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel konfigurieren Sie einen Dienst Metadaten verfügbar gemacht, mit der \<ServiceMetadata > Element. Es wird auch ein Endpunkt konfiguriert, mit dem der `IMetadataExchange`-Vertrag als Implementierung eines WS-MetadataExchange (MEX)-Protokolls verfügbar gemacht wird. In dem Beispiel wird `mexHttpBinding` verwendet, eine benutzerfreundliche Standardbindung, die `wsHttpBinding` entspricht und für die der Sicherheitsmodus auf `None` festgelegt ist. Eine relative Adresse von "Mex" wird verwendet, in dem Endpunkt, die bei aufgelöst für die grundlegenden Dienste Adresse führt zu einer Endpunktadresse der `http://localhost/servicemodelsamples/service.svc/mex`.  
  
```xml  
<configuration>
  <system.serviceModel>
    <services>
      <service name="Microsoft.ServiceModel.Samples.CalculatorService"
               behaviorConfiguration="CalculatorServiceBehavior">
        <!-- This endpoint is exposed at the base address provided by the host: http://localhost/servicemodelsamples/service.svc -->
        <endpoint address=""
                  binding="wsHttpBinding"
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />
        <!-- The mex endpoint is exposed at http://localhost/servicemodelsamples/service.svc/mex
             To expose the IMetadataExchange contract, you must enable the serviceMetadata behavior as demonstrated below. -->
        <endpoint address="mex"
                  binding="mexHttpBinding"
                  contract="IMetadataExchange" />
      </service>
    </services>
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->
    <behaviors>
      <serviceBehaviors>
        <behavior name="CalculatorServiceBehavior">
          <!-- The serviceMetadata behavior publishes metadata through the IMetadataExchange contract. When this behavior is
               present, you can expose this contract through an endpoint as shown above. Setting httpGetEnabled to true publishes
               the service's WSDL at the <baseaddress>?wsdl eg. http://localhost/servicemodelsamples/service.svc?wsdl -->
          <serviceMetadata httpGetEnabled="True" />
          <serviceDebug includeExceptionDetailInFaults="False" />
        </behavior>
      </serviceBehaviors>
    </behaviors>
  </system.serviceModel>
</configuration>
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Configuration.ServiceMetadataPublishingElement>
- <xref:System.ServiceModel.Description.ServiceMetadataBehavior>
- [Sicherheitsverhalten](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [Metadatenveröffentlichungsverhalten](../../../../../docs/framework/wcf/samples/metadata-publishing-behavior.md)
