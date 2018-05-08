---
title: 'Vorgehensweise: Migrieren von ASP.NET-Webdienstcode zu Windows Communication Foundation'
ms.date: 03/30/2017
ms.assetid: e528c64f-c027-4f2e-ada6-d8f3994cf8d6
ms.openlocfilehash: 90a6109a56299ec1bcaff4a35141abc194484772
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-migrate-aspnet-web-service-code-to-the-windows-communication-foundation"></a>Vorgehensweise: Migrieren von ASP.NET-Webdienstcode zu Windows Communication Foundation
Das folgende Verfahren beschreibt, wie ein ASP.NET-Webdienst zu Windows Communication Foundation (WCF) migrieren.  
  
## <a name="procedure"></a>Prozedur  
  
#### <a name="to-migrate-aspnet-web-service-code-to-wcf"></a>So migrieren Sie ASP.NET-Webdienstcode zu WCF  
  
1.  Stellen Sie sicher, dass für den Dienst ein umfassender Satz von Tests vorhanden ist.  
  
2.  Generieren Sie die WSDL für den Dienst, und speichern Sie eine Kopie in dem Ordner, in dem sich auch die ASMX-Datei des Diensts befindet.  
  
3.  Aktualisieren Sie den ASP.NET-Webdienst für die Verwendung von .NET 2.0. Zuerst .NET Framework 2.0 für die Anwendung in IIS bereitzustellen, und verwenden Sie Visual Studio 2005 den codeumwandlungsprozess automatisieren, wie im [Step Guide to Converting Web Projects aus Visual Studio .NET 2002/2003 to Visual Studio 2005](http://go.microsoft.com/fwlink/?LinkId=96492). Führen Sie die Tests aus.  
  
4.  Geben Sie explizite Werte für den `Namespace` und die `Name`-Parameter der <xref:System.Web.Services.WebService>-Attribute an, sofern diese nicht bereits vorhanden sind. Führen Sie die gleichen Schritte für die `MessageName`-Parameter von <xref:System.Web.Services.WebMethodAttribute> aus. Sind für die SOAPAction-HTTP-Header, gemäß denen Anforderungen zu Methoden geroutet werden, noch keine expliziten Werte angegeben, geben Sie explizit den Standardwert für den `Action`-Parameter mit einem <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute> an.  
  
    ```  
    [WebService(Namespace = "http://tempuri.org/", Name = "Adder")]  
    public class Adder  
    {  
         [WebMethod(MessageName = "Add")]  
         [SoapDocumentMethod(Action = "http://tempuri.org/Add")]  
         public double Add(SumInput input)  
         {  
              double sum = 0.00;  
              foreach (double inputValue in input.Input)  
              {  
                  sum += inputValue;  
              }  
          return sum;  
         }  
    }  
    ```  
  
5.  Testen Sie die Änderung.  
  
6.  Verschieben Sie sämtlichen substanziellen Code im Textkörper der Methoden der Klasse in eine separate Klasse, die von der ursprünglichen Klasse verwendet wird.  
  
    ```  
    [WebService(Namespace = "http://tempuri.org/", Name = "Adder")]  
    public class Adder  
    {  
         [WebMethod(MessageName = "Add")]  
         [SoapDocumentMethod(Action = "http://tempuri.org/Add")]  
         public double Add(SumInput input)  
         {  
              return new ActualAdder().Add(input);  
         }  
    }  
  
    internal class ActualAdder  
    {  
         internal double Add(SumInput input)  
         {  
              double sum = 0.00;  
              foreach (double inputValue in input.Input)  
              {  
                  sum += inputValue;  
              }  
          return sum;  
         }  
    }  
    ```  
  
7.  Testen Sie die Änderung.  
  
8.  Fügen Sie der ASP.NET Web Service-Projekt Verweise auf WCF-Assemblys System.ServiceModel und System.Runtime.Serialization hinzu.  
  
9. Führen Sie [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) aus WSDL eine WCF-Clientklasse generiert. Fügen Sie der Lösung das generierte Klassenmodul hinzu.  
  
10. Das im vorangehenden Schritt generierte Klassenmodul enthält die Definition einer Schnittstelle.  
  
    ```  
    [System.ServiceModel.ServiceContractAttribute()]  
    public interface AdderSoap  
    {  
         [System.ServiceModel.OperationContractAttribute(  
          Action="http://tempuri.org/Add",   
          ReplyAction="http://tempuri.org/Add")]  
         AddResponse Add(AddRequest request);  
    }  
    ```  
  
     Passen Sie die Definition der ASP.NET-Webdienstklasse so an, dass für die Klasse die Implementierung dieser Schnittstelle festgelegt ist. Im Folgenden finden Sie ein entsprechendes Codebeispiel.  
  
    ```  
    [WebService(Namespace = "http://tempuri.org/", Name = "Adder")]  
    public class Adder: AdderSoap  
    {  
         [WebMethod(MessageName = "Add")]  
         [SoapDocumentMethod(Action = "http://tempuri.org/Add")]  
         public double Add(SumInput input)  
         {  
              return new ActualAdder().Add(input);  
         }  
  
         public AddResponse Add(AddRequest request)  
         {  
            return new AddResponse(  
            new AddResponseBody(  
            this.Add(request.Body.input)));  
         }  
    }  
    ```  
  
11. Kompilieren Sie das Projekt. Aufgrund des in Schritt9 generierten Codes treten möglicherweise einige Fehler auf, da einige Typdefinitionen dupliziert wurden. Beheben Sie diese Fehler. In der Regel ist hierzu das Löschen der bereits vorhandenen Typendefinitionen ausreichend. Testen Sie die Änderung.  
  
12. Entfernen Sie die ASP.NET-spezifischen Attribute. Beispiele: <xref:System.Web.Services.WebService>, <xref:System.Web.Services.WebMethodAttribute> und <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute>.  
  
    ```  
    public class Adder: AdderSoap  
    {  
         public double Add(SumInput input)  
         {  
              return new ActualAdder().Add(input);  
         }  
  
         public AddResponse Add(AddRequest request)  
         {  
              return new AddResponse(  
             new AddResponseBody(  
            this.Add(request.Body.input)));  
         }  
    }  
    ```  
  
13. Konfigurieren Sie die Klasse, die jetzt einen WCF-Diensttyp ASP.NET-Kompatibilitätsmodus von WCF erforderlich ist, wenn der ASP.NET-Webdienst auf eine der folgenden zugegriffen wird:  
  
    -   Der <xref:System.Web.HttpContext>-Klasse.  
  
    -   Den ASP.NET-Profilen.  
  
    -   Den ACLs für ASMX-Dateien.  
  
    -   Den IIS-Authentifizierungsoptionen.  
  
    -   Den Identitätswechseloptionen von ASP.NET.  
  
    -   Der ASP.NET-Globalisierung.  
  
    ```  
    [System.ServiceModel.AspNetCompatibilityRequirements(  
      RequirementsMode=AspNetCompatbilityRequirementsMode.Required)]  
    public class Adder: AdderSoap  
    ```  
  
14. Benennen Sie die ursprüngliche ASMX-Datei zu .asmx.old um.  
  
15. Erstellen Sie eine WCF-Dienst-Datei für den Dienst, versehen Sie sie mit der Erweiterung .asmx, und speichern Sie ihn in das Stammverzeichnis der Anwendung in IIS.  
  
    ```xml  
    <%@Service Class="MyOrganization.Adder" %>  
    <%@Assembly Name="MyServiceAssembly" %>   
    ```  
  
16. Fügen Sie einen WCF-Konfiguration für den Dienst zur Datei "Web.config" hinzu. Konfigurieren Sie den Dienst verwendet die [ \<BasicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md), zum Verwenden der Service-Datei mit der Erweiterung .asmx, die in den vorherigen Schritten erstellt und WSDL nicht für sich selbst zu generieren, aber die WSDL-Datei aus Schritt 2 verwendet. Konfigurieren Sie den Dienst zudem für die Verwendung des ASP.NET-Kompatibilitätsmodus (sofern erforderlich).  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
     <system.web>  
      <compilation>  
      <buildProviders>  
       <remove extension=".asmx" />  
       <add extension=".asmx"   
        type=  
        "System.ServiceModel.Activation.ServiceBuildProvider,  
        T:System.ServiceModel, Version=2.0.0.0,   
       Culture=neutral,   
       PublicKeyToken=b77a5c561934e089" />  
      </buildProviders>  
      </compilation>  
     </system.web>  
     <system.serviceModel>  
      <services>  
      <service name="MyOrganization.Adder "  
        behaviorConfiguration="AdderBehavior">  
       <endpoint   
        address=""  
        binding="basicHttpBinding"  
        contract="AdderSoap "/>  
       </service>  
      </services>  
      <behaviors>  
      <behavior name="AdderBehavior">  
       <metadataPublishing   
        enableMetadataExchange="true"   
        enableGetWsdl="true"   
        enableHelpPage="true"   
        metadataLocation=  
        "http://MyHost.com/AdderService/Service.WSDL"/>  
      </behavior>  
      </behaviors>  
      <serviceHostingEnvironment   
       aspNetCompatibilityEnabled ="true"/>  
     </system.serviceModel>  
    </configuration>  
    ```  
  
17. Speichern Sie die Konfiguration.  
  
18. Kompilieren Sie das Projekt.  
  
19. Vergewissern Sie sich durch Ausführen der Tests, dass alle Änderungen ordnungsgemäß funktionieren.  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Migrieren von ASP.NET-Webdienst-Clientcode zu Windows Communication Foundation](../../../../docs/framework/wcf/feature-details/migrate-asp-net-web-service-client-to-wcf.md)
