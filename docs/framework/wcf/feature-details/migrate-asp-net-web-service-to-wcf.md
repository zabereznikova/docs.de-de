---
title: 'Vorgehensweise: Migrieren von ASP.NET-Webdienstcode zu Windows Communication Foundation'
ms.date: 03/30/2017
ms.assetid: e528c64f-c027-4f2e-ada6-d8f3994cf8d6
ms.openlocfilehash: 90a6109a56299ec1bcaff4a35141abc194484772
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33496698"
---
# <a name="how-to-migrate-aspnet-web-service-code-to-the-windows-communication-foundation"></a><span data-ttu-id="2c7ef-102">Vorgehensweise: Migrieren von ASP.NET-Webdienstcode zu Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="2c7ef-102">How to: Migrate ASP.NET Web Service Code to the Windows Communication Foundation</span></span>
<span data-ttu-id="2c7ef-103">Das folgende Verfahren beschreibt, wie ein ASP.NET-Webdienst zu Windows Communication Foundation (WCF) migrieren.</span><span class="sxs-lookup"><span data-stu-id="2c7ef-103">The following procedure describes how to migrate an ASP.NET Web Service to Windows Communication Foundation (WCF).</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="2c7ef-104">Prozedur</span><span class="sxs-lookup"><span data-stu-id="2c7ef-104">Procedure</span></span>  
  
#### <a name="to-migrate-aspnet-web-service-code-to-wcf"></a><span data-ttu-id="2c7ef-105">So migrieren Sie ASP.NET-Webdienstcode zu WCF</span><span class="sxs-lookup"><span data-stu-id="2c7ef-105">To migrate ASP.NET Web service code to WCF</span></span>  
  
1.  <span data-ttu-id="2c7ef-106">Stellen Sie sicher, dass für den Dienst ein umfassender Satz von Tests vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="2c7ef-106">Ensure that a comprehensive set of tests exist for the service.</span></span>  
  
2.  <span data-ttu-id="2c7ef-107">Generieren Sie die WSDL für den Dienst, und speichern Sie eine Kopie in dem Ordner, in dem sich auch die ASMX-Datei des Diensts befindet.</span><span class="sxs-lookup"><span data-stu-id="2c7ef-107">Generate the WSDL for the service and save a copy in the same folder as the service’s .asmx file.</span></span>  
  
3.  <span data-ttu-id="2c7ef-108">Aktualisieren Sie den ASP.NET-Webdienst für die Verwendung von .NET 2.0.</span><span class="sxs-lookup"><span data-stu-id="2c7ef-108">Upgrade the ASP.NET Web service to use .NET 2.0.</span></span> <span data-ttu-id="2c7ef-109">Zuerst .NET Framework 2.0 für die Anwendung in IIS bereitzustellen, und verwenden Sie Visual Studio 2005 den codeumwandlungsprozess automatisieren, wie im [Step Guide to Converting Web Projects aus Visual Studio .NET 2002/2003 to Visual Studio 2005](http://go.microsoft.com/fwlink/?LinkId=96492).</span><span class="sxs-lookup"><span data-stu-id="2c7ef-109">First deploy the .NET Framework 2.0 to the application in IIS, and then use Visual Studio 2005 to automate the code conversion process, as documented in [Step-By-Step Guide to Converting Web Projects from Visual Studio .NET 2002/2003 to Visual Studio 2005](http://go.microsoft.com/fwlink/?LinkId=96492).</span></span> <span data-ttu-id="2c7ef-110">Führen Sie die Tests aus.</span><span class="sxs-lookup"><span data-stu-id="2c7ef-110">Run the set of tests.</span></span>  
  
4.  <span data-ttu-id="2c7ef-111">Geben Sie explizite Werte für den `Namespace` und die `Name`-Parameter der <xref:System.Web.Services.WebService>-Attribute an, sofern diese nicht bereits vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="2c7ef-111">Provide explicit values for the `Namespace` and `Name` parameters of the <xref:System.Web.Services.WebService> attributes if they are not provided already.</span></span> <span data-ttu-id="2c7ef-112">Führen Sie die gleichen Schritte für die `MessageName`-Parameter von <xref:System.Web.Services.WebMethodAttribute> aus.</span><span class="sxs-lookup"><span data-stu-id="2c7ef-112">Do the same for the `MessageName` parameter of the <xref:System.Web.Services.WebMethodAttribute>.</span></span> <span data-ttu-id="2c7ef-113">Sind für die SOAPAction-HTTP-Header, gemäß denen Anforderungen zu Methoden geroutet werden, noch keine expliziten Werte angegeben, geben Sie explizit den Standardwert für den `Action`-Parameter mit einem <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute> an.</span><span class="sxs-lookup"><span data-stu-id="2c7ef-113">If explicit values are not already provided for the SOAPAction HTTP headers by which requests are routed to methods, then explicitly specify the default value of the `Action` parameter with a <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute>.</span></span>  
  
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
  
5.  <span data-ttu-id="2c7ef-114">Testen Sie die Änderung.</span><span class="sxs-lookup"><span data-stu-id="2c7ef-114">Test the change.</span></span>  
  
6.  <span data-ttu-id="2c7ef-115">Verschieben Sie sämtlichen substanziellen Code im Textkörper der Methoden der Klasse in eine separate Klasse, die von der ursprünglichen Klasse verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2c7ef-115">Move any substantive code in the bodies of the methods of the class to a separate class that the original class is made to use.</span></span>  
  
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
  
7.  <span data-ttu-id="2c7ef-116">Testen Sie die Änderung.</span><span class="sxs-lookup"><span data-stu-id="2c7ef-116">Test the change.</span></span>  
  
8.  <span data-ttu-id="2c7ef-117">Fügen Sie der ASP.NET Web Service-Projekt Verweise auf WCF-Assemblys System.ServiceModel und System.Runtime.Serialization hinzu.</span><span class="sxs-lookup"><span data-stu-id="2c7ef-117">Add references to WCF assemblies System.ServiceModel and System.Runtime.Serialization to the ASP.NET Web service project.</span></span>  
  
9. <span data-ttu-id="2c7ef-118">Führen Sie [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) aus WSDL eine WCF-Clientklasse generiert.</span><span class="sxs-lookup"><span data-stu-id="2c7ef-118">Run [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to generate a WCF client class from the WSDL.</span></span> <span data-ttu-id="2c7ef-119">Fügen Sie der Lösung das generierte Klassenmodul hinzu.</span><span class="sxs-lookup"><span data-stu-id="2c7ef-119">Add the generated class module to the solution.</span></span>  
  
10. <span data-ttu-id="2c7ef-120">Das im vorangehenden Schritt generierte Klassenmodul enthält die Definition einer Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="2c7ef-120">The class module generated in the preceding step contains the definition of an interface.</span></span>  
  
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
  
     <span data-ttu-id="2c7ef-121">Passen Sie die Definition der ASP.NET-Webdienstklasse so an, dass für die Klasse die Implementierung dieser Schnittstelle festgelegt ist. Im Folgenden finden Sie ein entsprechendes Codebeispiel.</span><span class="sxs-lookup"><span data-stu-id="2c7ef-121">Modify the definition of the ASP.NET Web service class so that the class is defined as implementing that interface, as shown in the following sample code.</span></span>  
  
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
  
11. <span data-ttu-id="2c7ef-122">Kompilieren Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="2c7ef-122">Compile the project.</span></span> <span data-ttu-id="2c7ef-123">Aufgrund des in Schritt9 generierten Codes treten möglicherweise einige Fehler auf, da einige Typdefinitionen dupliziert wurden.</span><span class="sxs-lookup"><span data-stu-id="2c7ef-123">There may be some errors due to the code generated in step nine that duplicated some type definitions.</span></span> <span data-ttu-id="2c7ef-124">Beheben Sie diese Fehler. In der Regel ist hierzu das Löschen der bereits vorhandenen Typendefinitionen ausreichend.</span><span class="sxs-lookup"><span data-stu-id="2c7ef-124">Repair those errors, usually by deleting the pre-existing definitions of the types.</span></span> <span data-ttu-id="2c7ef-125">Testen Sie die Änderung.</span><span class="sxs-lookup"><span data-stu-id="2c7ef-125">Test the change.</span></span>  
  
12. <span data-ttu-id="2c7ef-126">Entfernen Sie die ASP.NET-spezifischen Attribute. Beispiele: <xref:System.Web.Services.WebService>, <xref:System.Web.Services.WebMethodAttribute> und <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute>.</span><span class="sxs-lookup"><span data-stu-id="2c7ef-126">Remove the ASP.NET-specific attributes, such as the <xref:System.Web.Services.WebService>, <xref:System.Web.Services.WebMethodAttribute> and <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute>.</span></span>  
  
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
  
13. <span data-ttu-id="2c7ef-127">Konfigurieren Sie die Klasse, die jetzt einen WCF-Diensttyp ASP.NET-Kompatibilitätsmodus von WCF erforderlich ist, wenn der ASP.NET-Webdienst auf eine der folgenden zugegriffen wird:</span><span class="sxs-lookup"><span data-stu-id="2c7ef-127">Configure the class, which is now a WCF service type, to require WCF ASP.NET compatibility mode if the ASP.NET Web service relied on any of the following:</span></span>  
  
    -   <span data-ttu-id="2c7ef-128">Der <xref:System.Web.HttpContext>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="2c7ef-128">The <xref:System.Web.HttpContext> class.</span></span>  
  
    -   <span data-ttu-id="2c7ef-129">Den ASP.NET-Profilen.</span><span class="sxs-lookup"><span data-stu-id="2c7ef-129">The ASP.NET Profiles.</span></span>  
  
    -   <span data-ttu-id="2c7ef-130">Den ACLs für ASMX-Dateien.</span><span class="sxs-lookup"><span data-stu-id="2c7ef-130">ACLs on .asmx files.</span></span>  
  
    -   <span data-ttu-id="2c7ef-131">Den IIS-Authentifizierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="2c7ef-131">IIS authentication options.</span></span>  
  
    -   <span data-ttu-id="2c7ef-132">Den Identitätswechseloptionen von ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="2c7ef-132">ASP.NET impersonation options.</span></span>  
  
    -   <span data-ttu-id="2c7ef-133">Der ASP.NET-Globalisierung.</span><span class="sxs-lookup"><span data-stu-id="2c7ef-133">ASP.NET globalization.</span></span>  
  
    ```  
    [System.ServiceModel.AspNetCompatibilityRequirements(  
      RequirementsMode=AspNetCompatbilityRequirementsMode.Required)]  
    public class Adder: AdderSoap  
    ```  
  
14. <span data-ttu-id="2c7ef-134">Benennen Sie die ursprüngliche ASMX-Datei zu .asmx.old um.</span><span class="sxs-lookup"><span data-stu-id="2c7ef-134">Rename the original .asmx file to .asmx.old.</span></span>  
  
15. <span data-ttu-id="2c7ef-135">Erstellen Sie eine WCF-Dienst-Datei für den Dienst, versehen Sie sie mit der Erweiterung .asmx, und speichern Sie ihn in das Stammverzeichnis der Anwendung in IIS.</span><span class="sxs-lookup"><span data-stu-id="2c7ef-135">Create a WCF service file for the service, give it the extension, .asmx, and save it into the application root in IIS.</span></span>  
  
    ```xml  
    <%@Service Class="MyOrganization.Adder" %>  
    <%@Assembly Name="MyServiceAssembly" %>   
    ```  
  
16. <span data-ttu-id="2c7ef-136">Fügen Sie einen WCF-Konfiguration für den Dienst zur Datei "Web.config" hinzu.</span><span class="sxs-lookup"><span data-stu-id="2c7ef-136">Add a WCF configuration for the service to its Web.config file.</span></span> <span data-ttu-id="2c7ef-137">Konfigurieren Sie den Dienst verwendet die [ \<BasicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md), zum Verwenden der Service-Datei mit der Erweiterung .asmx, die in den vorherigen Schritten erstellt und WSDL nicht für sich selbst zu generieren, aber die WSDL-Datei aus Schritt 2 verwendet.</span><span class="sxs-lookup"><span data-stu-id="2c7ef-137">Configure the service to use the [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md), to use the service file with the .asmx extension created in the preceding steps, and to not generate WSDL for itself, but to use the WSDL from step two.</span></span> <span data-ttu-id="2c7ef-138">Konfigurieren Sie den Dienst zudem für die Verwendung des ASP.NET-Kompatibilitätsmodus (sofern erforderlich).</span><span class="sxs-lookup"><span data-stu-id="2c7ef-138">Also configure it to use ASP.NET compatibility mode if necessary.</span></span>  
  
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
  
17. <span data-ttu-id="2c7ef-139">Speichern Sie die Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="2c7ef-139">Save the configuration.</span></span>  
  
18. <span data-ttu-id="2c7ef-140">Kompilieren Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="2c7ef-140">Compile the project.</span></span>  
  
19. <span data-ttu-id="2c7ef-141">Vergewissern Sie sich durch Ausführen der Tests, dass alle Änderungen ordnungsgemäß funktionieren.</span><span class="sxs-lookup"><span data-stu-id="2c7ef-141">Run the set of tests to make sure all the changes work.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c7ef-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2c7ef-142">See Also</span></span>  
 [<span data-ttu-id="2c7ef-143">Vorgehensweise: Migrieren von ASP.NET-Webdienst-Clientcode zu Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="2c7ef-143">How to: Migrate ASP.NET Web Service Client Code to the Windows Communication Foundation</span></span>](../../../../docs/framework/wcf/feature-details/migrate-asp-net-web-service-client-to-wcf.md)
