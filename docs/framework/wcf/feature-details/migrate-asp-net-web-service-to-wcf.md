---
title: 'Vorgehensweise: Migrieren von ASP.NET-Webdienstcode zu Windows Communication Foundation'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e528c64f-c027-4f2e-ada6-d8f3994cf8d6
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e56d2481785a9a8486174e611001b9d800c7c869
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-migrate-aspnet-web-service-code-to-the-windows-communication-foundation"></a><span data-ttu-id="cf959-102">Vorgehensweise: Migrieren von ASP.NET-Webdienstcode zu Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="cf959-102">How to: Migrate ASP.NET Web Service Code to the Windows Communication Foundation</span></span>
<span data-ttu-id="cf959-103">Die folgende Prozedur beschreibt, wie ein ASP.NET-Webdienst zu [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] migriert wird.</span><span class="sxs-lookup"><span data-stu-id="cf959-103">The following procedure describes how to migrate an ASP.NET Web Service to [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="cf959-104">Verfahren</span><span class="sxs-lookup"><span data-stu-id="cf959-104">Procedure</span></span>  
  
#### <a name="to-migrate-aspnet-web-service-code-to-wcf"></a><span data-ttu-id="cf959-105">So migrieren Sie ASP.NET-Webdienstcode zu WCF</span><span class="sxs-lookup"><span data-stu-id="cf959-105">To migrate ASP.NET Web service code to WCF</span></span>  
  
1.  <span data-ttu-id="cf959-106">Stellen Sie sicher, dass für den Dienst ein umfassender Satz von Tests vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="cf959-106">Ensure that a comprehensive set of tests exist for the service.</span></span>  
  
2.  <span data-ttu-id="cf959-107">Generieren Sie die WSDL für den Dienst, und speichern Sie eine Kopie in dem Ordner, in dem sich auch die ASMX-Datei des Diensts befindet.</span><span class="sxs-lookup"><span data-stu-id="cf959-107">Generate the WSDL for the service and save a copy in the same folder as the service’s .asmx file.</span></span>  
  
3.  <span data-ttu-id="cf959-108">Aktualisieren Sie den ASP.NET-Webdienst für die Verwendung von .NET 2.0.</span><span class="sxs-lookup"><span data-stu-id="cf959-108">Upgrade the ASP.NET Web service to use .NET 2.0.</span></span> <span data-ttu-id="cf959-109">Zuerst .NET Framework 2.0 für die Anwendung in IIS bereitzustellen, und verwenden Sie Visual Studio 2005 den codeumwandlungsprozess automatisieren, wie im [Step Guide to Converting Web Projects aus Visual Studio .NET 2002/2003 to Visual Studio 2005](http://go.microsoft.com/fwlink/?LinkId=96492).</span><span class="sxs-lookup"><span data-stu-id="cf959-109">First deploy the .NET Framework 2.0 to the application in IIS, and then use Visual Studio 2005 to automate the code conversion process, as documented in [Step-By-Step Guide to Converting Web Projects from Visual Studio .NET 2002/2003 to Visual Studio 2005](http://go.microsoft.com/fwlink/?LinkId=96492).</span></span> <span data-ttu-id="cf959-110">Führen Sie die Tests aus.</span><span class="sxs-lookup"><span data-stu-id="cf959-110">Run the set of tests.</span></span>  
  
4.  <span data-ttu-id="cf959-111">Geben Sie explizite Werte für den `Namespace` und die `Name`-Parameter der <xref:System.Web.Services.WebService>-Attribute an, sofern diese nicht bereits vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="cf959-111">Provide explicit values for the `Namespace` and `Name` parameters of the <xref:System.Web.Services.WebService> attributes if they are not provided already.</span></span> <span data-ttu-id="cf959-112">Führen Sie die gleichen Schritte für die `MessageName`-Parameter von <xref:System.Web.Services.WebMethodAttribute> aus.</span><span class="sxs-lookup"><span data-stu-id="cf959-112">Do the same for the `MessageName` parameter of the <xref:System.Web.Services.WebMethodAttribute>.</span></span> <span data-ttu-id="cf959-113">Sind für die SOAPAction-HTTP-Header, gemäß denen Anforderungen zu Methoden geroutet werden, noch keine expliziten Werte angegeben, geben Sie explizit den Standardwert für den `Action`-Parameter mit einem <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute> an.</span><span class="sxs-lookup"><span data-stu-id="cf959-113">If explicit values are not already provided for the SOAPAction HTTP headers by which requests are routed to methods, then explicitly specify the default value of the `Action` parameter with a <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute>.</span></span>  
  
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
  
5.  <span data-ttu-id="cf959-114">Testen Sie die Änderung.</span><span class="sxs-lookup"><span data-stu-id="cf959-114">Test the change.</span></span>  
  
6.  <span data-ttu-id="cf959-115">Verschieben Sie sämtlichen substanziellen Code im Textkörper der Methoden der Klasse in eine separate Klasse, die von der ursprünglichen Klasse verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="cf959-115">Move any substantive code in the bodies of the methods of the class to a separate class that the original class is made to use.</span></span>  
  
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
  
7.  <span data-ttu-id="cf959-116">Testen Sie die Änderung.</span><span class="sxs-lookup"><span data-stu-id="cf959-116">Test the change.</span></span>  
  
8.  <span data-ttu-id="cf959-117">Fügen Sie dem ASP.NET-Webdienstprojekt Verweise auf die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Assemblys System.ServiceModel und System.Runtime.Serialization hinzu.</span><span class="sxs-lookup"><span data-stu-id="cf959-117">Add references to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] assemblies System.ServiceModel and System.Runtime.Serialization to the ASP.NET Web service project.</span></span>  
  
9. <span data-ttu-id="cf959-118">Führen Sie [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) zum Generieren einer [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] aus der WSDL-Client-Klasse.</span><span class="sxs-lookup"><span data-stu-id="cf959-118">Run [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to generate a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client class from the WSDL.</span></span> <span data-ttu-id="cf959-119">Fügen Sie der Lösung das generierte Klassenmodul hinzu.</span><span class="sxs-lookup"><span data-stu-id="cf959-119">Add the generated class module to the solution.</span></span>  
  
10. <span data-ttu-id="cf959-120">Das im vorangehenden Schritt generierte Klassenmodul enthält die Definition einer Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="cf959-120">The class module generated in the preceding step contains the definition of an interface.</span></span>  
  
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
  
     <span data-ttu-id="cf959-121">Passen Sie die Definition der ASP.NET-Webdienstklasse so an, dass für die Klasse die Implementierung dieser Schnittstelle festgelegt ist. Im Folgenden finden Sie ein entsprechendes Codebeispiel.</span><span class="sxs-lookup"><span data-stu-id="cf959-121">Modify the definition of the ASP.NET Web service class so that the class is defined as implementing that interface, as shown in the following sample code.</span></span>  
  
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
  
11. <span data-ttu-id="cf959-122">Kompilieren Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="cf959-122">Compile the project.</span></span> <span data-ttu-id="cf959-123">Aufgrund des in Schritt9 generierten Codes treten möglicherweise einige Fehler auf, da einige Typdefinitionen dupliziert wurden.</span><span class="sxs-lookup"><span data-stu-id="cf959-123">There may be some errors due to the code generated in step nine that duplicated some type definitions.</span></span> <span data-ttu-id="cf959-124">Beheben Sie diese Fehler. In der Regel ist hierzu das Löschen der bereits vorhandenen Typendefinitionen ausreichend.</span><span class="sxs-lookup"><span data-stu-id="cf959-124">Repair those errors, usually by deleting the pre-existing definitions of the types.</span></span> <span data-ttu-id="cf959-125">Testen Sie die Änderung.</span><span class="sxs-lookup"><span data-stu-id="cf959-125">Test the change.</span></span>  
  
12. <span data-ttu-id="cf959-126">Entfernen Sie die ASP.NET-spezifischen Attribute. Beispiele: <xref:System.Web.Services.WebService>, <xref:System.Web.Services.WebMethodAttribute> und <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute>.</span><span class="sxs-lookup"><span data-stu-id="cf959-126">Remove the ASP.NET-specific attributes, such as the <xref:System.Web.Services.WebService>, <xref:System.Web.Services.WebMethodAttribute> and <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute>.</span></span>  
  
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
  
13. <span data-ttu-id="cf959-127">Konfigurieren Sie die Klasse, bei der es sich nun um eine [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienstklasse handelt, sodass der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-ASP.NET-Kompatibilitätsmodus verwendet wird, wenn der ASP.NET-Webdienst auf einem der folgenden Elemente beruht:</span><span class="sxs-lookup"><span data-stu-id="cf959-127">Configure the class, which is now a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service type, to require [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ASP.NET compatibility mode if the ASP.NET Web service relied on any of the following:</span></span>  
  
    -   <span data-ttu-id="cf959-128">Der <xref:System.Web.HttpContext>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="cf959-128">The <xref:System.Web.HttpContext> class.</span></span>  
  
    -   <span data-ttu-id="cf959-129">Den ASP.NET-Profilen.</span><span class="sxs-lookup"><span data-stu-id="cf959-129">The ASP.NET Profiles.</span></span>  
  
    -   <span data-ttu-id="cf959-130">Den ACLs für ASMX-Dateien.</span><span class="sxs-lookup"><span data-stu-id="cf959-130">ACLs on .asmx files.</span></span>  
  
    -   <span data-ttu-id="cf959-131">Den IIS-Authentifizierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="cf959-131">IIS authentication options.</span></span>  
  
    -   <span data-ttu-id="cf959-132">Den Identitätswechseloptionen von ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="cf959-132">ASP.NET impersonation options.</span></span>  
  
    -   <span data-ttu-id="cf959-133">Der ASP.NET-Globalisierung.</span><span class="sxs-lookup"><span data-stu-id="cf959-133">ASP.NET globalization.</span></span>  
  
    ```  
    [System.ServiceModel.AspNetCompatibilityRequirements(  
      RequirementsMode=AspNetCompatbilityRequirementsMode.Required)]  
    public class Adder: AdderSoap  
    ```  
  
14. <span data-ttu-id="cf959-134">Benennen Sie die ursprüngliche ASMX-Datei zu .asmx.old um.</span><span class="sxs-lookup"><span data-stu-id="cf959-134">Rename the original .asmx file to .asmx.old.</span></span>  
  
15. <span data-ttu-id="cf959-135">Erstellen Sie für den Dienst eine [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienstdatei, versehen Sie sie mit der Erweiterung .asmx, und speichern Sie sie im Anwendungsstammverzeichnis der IIS.</span><span class="sxs-lookup"><span data-stu-id="cf959-135">Create a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service file for the service, give it the extension, .asmx, and save it into the application root in IIS.</span></span>  
  
    ```xml  
    <%@Service Class="MyOrganization.Adder" %>  
    <%@Assembly Name="MyServiceAssembly" %>   
    ```  
  
16. <span data-ttu-id="cf959-136">Fügen Sie der entsprechenden Web.config-Datei eine [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Konfiguration hinzu.</span><span class="sxs-lookup"><span data-stu-id="cf959-136">Add a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] configuration for the service to its Web.config file.</span></span> <span data-ttu-id="cf959-137">Konfigurieren Sie den Dienst verwendet die [ \<BasicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md), zum Verwenden der Service-Datei mit der Erweiterung .asmx, die in den vorherigen Schritten erstellt und WSDL nicht für sich selbst zu generieren, aber die WSDL-Datei aus Schritt 2 verwendet.</span><span class="sxs-lookup"><span data-stu-id="cf959-137">Configure the service to use the [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md), to use the service file with the .asmx extension created in the preceding steps, and to not generate WSDL for itself, but to use the WSDL from step two.</span></span> <span data-ttu-id="cf959-138">Konfigurieren Sie den Dienst zudem für die Verwendung des ASP.NET-Kompatibilitätsmodus (sofern erforderlich).</span><span class="sxs-lookup"><span data-stu-id="cf959-138">Also configure it to use ASP.NET compatibility mode if necessary.</span></span>  
  
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
  
17. <span data-ttu-id="cf959-139">Speichern Sie die Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="cf959-139">Save the configuration.</span></span>  
  
18. <span data-ttu-id="cf959-140">Kompilieren Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="cf959-140">Compile the project.</span></span>  
  
19. <span data-ttu-id="cf959-141">Vergewissern Sie sich durch Ausführen der Tests, dass alle Änderungen ordnungsgemäß funktionieren.</span><span class="sxs-lookup"><span data-stu-id="cf959-141">Run the set of tests to make sure all the changes work.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf959-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cf959-142">See Also</span></span>  
 [<span data-ttu-id="cf959-143">Vorgehensweise: Migrieren von ASP.NET-Webdienst-Clientcode zu Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="cf959-143">How to: Migrate ASP.NET Web Service Client Code to the Windows Communication Foundation</span></span>](../../../../docs/framework/wcf/feature-details/migrate-asp-net-web-service-client-to-wcf.md)
