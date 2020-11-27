---
title: Benutzerdefinierte WSDL-Veröffentlichung
ms.date: 03/30/2017
ms.assetid: 3b3e8103-2c95-4db3-a05b-46aa8e9d4d29
ms.openlocfilehash: 83377e1c72ef5774c909729abd1312cce5364ab0
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96262865"
---
# <a name="custom-wsdl-publication"></a><span data-ttu-id="c9d2a-102">Benutzerdefinierte WSDL-Veröffentlichung</span><span class="sxs-lookup"><span data-stu-id="c9d2a-102">Custom WSDL Publication</span></span>

<span data-ttu-id="c9d2a-103">In diesem Beispiel wird Folgendes veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="c9d2a-103">This sample demonstrates how to:</span></span>  
  
- <span data-ttu-id="c9d2a-104">Eine <xref:System.ServiceModel.Description.IWsdlExportExtension?displayProperty=nameWithType> in einem benutzerdefinierten <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType>-Attribut zum Exportieren von Attributeigenschaften als WSDL-Anmerkungen implementieren.</span><span class="sxs-lookup"><span data-stu-id="c9d2a-104">Implement a <xref:System.ServiceModel.Description.IWsdlExportExtension?displayProperty=nameWithType> on a custom <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> attribute to export attribute properties as WSDL annotations.</span></span>  
  
- <span data-ttu-id="c9d2a-105"><xref:System.ServiceModel.Description.IWsdlImportExtension?displayProperty=nameWithType> zum Importieren der benutzerdefinierten WSDL-Anmerkungen implementieren.</span><span class="sxs-lookup"><span data-stu-id="c9d2a-105">Implement <xref:System.ServiceModel.Description.IWsdlImportExtension?displayProperty=nameWithType> to import the custom WSDL annotations.</span></span>  
  
- <span data-ttu-id="c9d2a-106"><xref:System.ServiceModel.Description.IServiceContractGenerationExtension?displayProperty=nameWithType> und <xref:System.ServiceModel.Description.IOperationContractGenerationExtension?displayProperty=nameWithType> in einem benutzerdefinierten Vertragsverhalten bzw. Vorgangsverhalten definieren, um importierte Anmerkungen als Anmerkungen in die CodeDom für den importieren Vertrag bzw. Vorgang zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="c9d2a-106">Implement <xref:System.ServiceModel.Description.IServiceContractGenerationExtension?displayProperty=nameWithType> and <xref:System.ServiceModel.Description.IOperationContractGenerationExtension?displayProperty=nameWithType> on a custom contract behavior and a custom operation behavior, respectively, to write imported annotations as comments in the CodeDom for the imported contract and operation.</span></span>  
  
- <span data-ttu-id="c9d2a-107">Verwenden <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> Sie zum Herunterladen der WSDL-Datei (a) <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType> zum Importieren der WSDL-Datei mithilfe des benutzerdefinierten WSDL-Importierens und zum <xref:System.ServiceModel.Description.ServiceContractGenerator?displayProperty=nameWithType> Generieren von Windows Communication Foundation (WCF)-Client Code mit den WSDL-Anmerkungen in c# und Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="c9d2a-107">Use the <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> to download the WSDL, a <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType> to import the WSDL using the custom WSDL importer, and the <xref:System.ServiceModel.Description.ServiceContractGenerator?displayProperty=nameWithType> to generate Windows Communication Foundation (WCF) client code with the WSDL annotations as /// and ''' comments in C# and Visual Basic.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c9d2a-108">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="c9d2a-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
## <a name="service"></a><span data-ttu-id="c9d2a-109">Dienst</span><span class="sxs-lookup"><span data-stu-id="c9d2a-109">Service</span></span>  

 <span data-ttu-id="c9d2a-110">Der Dienst in diesem Beispiel ist mit zwei benutzerdefinierten Attributen versehen.</span><span class="sxs-lookup"><span data-stu-id="c9d2a-110">The service in this sample is marked with two custom attributes.</span></span> <span data-ttu-id="c9d2a-111">Das erste Attribut (`WsdlDocumentationAttribute`) nimmt eine Zeichenfolge im Konstruktor entgegen und kann angewendet werden, um eine Vertragsschnittstelle oder einen -vorgang mit einer Zeichenfolge zur Verfügung zu stellen, die dessen Verwendung beschreibt.</span><span class="sxs-lookup"><span data-stu-id="c9d2a-111">The first, the `WsdlDocumentationAttribute`, accepts a string in the constructor and can be applied to provide a contract interface or operation with a string that describes its usage.</span></span> <span data-ttu-id="c9d2a-112">Das zweite Attribut (`WsdlParamOrReturnDocumentationAttribute`) kann zum Zurückgeben von Werten oder Parametern verwendet werden, um diese Werte im Vorgang zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="c9d2a-112">The second, `WsdlParamOrReturnDocumentationAttribute`, can be applied to return values or parameters to describe those values in the operation.</span></span> <span data-ttu-id="c9d2a-113">Das folgende Beispiel zeigt einen Dienstvertrag (`ICalculator`), der mit diesen Attributen beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="c9d2a-113">The following example shows a service contract, `ICalculator`, described using these attributes.</span></span>  
  
```csharp  
// Define a service contract.
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
// Document it.  
[WsdlDocumentation("The ICalculator contract performs basic calculation services.")]  
public interface ICalculator  
{  
    [OperationContract]  
    [WsdlDocumentation("The Add operation adds two numbers and returns the result.")]  
    [return:WsdlParamOrReturnDocumentation("The result of adding the two arguments together.")]  
    double Add(  
      [WsdlParamOrReturnDocumentation("The first value to add.")]double n1,
      [WsdlParamOrReturnDocumentation("The second value to add.")]double n2  
    );  
  
    [OperationContract]  
    [WsdlDocumentation("The Subtract operation subtracts the second argument from the first.")]  
    [return:WsdlParamOrReturnDocumentation("The result of the second argument subtracted from the first.")]  
    double Subtract(  
      [WsdlParamOrReturnDocumentation("The value from which the second is subtracted.")]double n1,
      [WsdlParamOrReturnDocumentation("The value that is subtracted from the first.")]double n2  
    );  
  
    [OperationContract]  
    [WsdlDocumentation("The Multiply operation multiplies two values.")]  
    [return:WsdlParamOrReturnDocumentation("The result of multiplying the first and second arguments.")]  
    double Multiply(  
      [WsdlParamOrReturnDocumentation("The first value to multiply.")]double n1,
      [WsdlParamOrReturnDocumentation("The second value to multiply.")]double n2  
    );  
  
    [OperationContract]  
    [WsdlDocumentation("The Divide operation returns the value of the first argument divided by the second argument.")]  
    [return:WsdlParamOrReturnDocumentation("The result of dividing the first argument by the second.")]  
    double Divide(  
      [WsdlParamOrReturnDocumentation("The numerator.")]double n1,
      [WsdlParamOrReturnDocumentation("The denominator.")]double n2  
    );  
}  
```  
  
 <span data-ttu-id="c9d2a-114">Das `WsdlDocumentationAttribute` implementiert <xref:System.ServiceModel.Description.IContractBehavior> und <xref:System.ServiceModel.Description.IOperationBehavior>, daher werden die Attributinstanzen beim Öffnen des Diensts zur entsprechenden <xref:System.ServiceModel.Description.ContractDescription> oder <xref:System.ServiceModel.Description.OperationDescription> hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="c9d2a-114">The `WsdlDocumentationAttribute` implements <xref:System.ServiceModel.Description.IContractBehavior> and <xref:System.ServiceModel.Description.IOperationBehavior>, so the attribute instances are added to the corresponding <xref:System.ServiceModel.Description.ContractDescription> or <xref:System.ServiceModel.Description.OperationDescription> when the service is opened.</span></span> <span data-ttu-id="c9d2a-115">Außerdem implementiert das Attribut <xref:System.ServiceModel.Description.IWsdlExportExtension>.</span><span class="sxs-lookup"><span data-stu-id="c9d2a-115">The attribute also implements <xref:System.ServiceModel.Description.IWsdlExportExtension>.</span></span> <span data-ttu-id="c9d2a-116">Beim Aufruf von <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportContract%28System.ServiceModel.Description.WsdlExporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29> werden <xref:System.ServiceModel.Description.WsdlExporter> (das zum Exportieren der Metadaten verwendet wird) und <xref:System.ServiceModel.Description.WsdlContractConversionContext> (das die Dienstbeschreibungsobjekte enthält) als Parameter übergeben, was ermöglicht, die exportierten Metadaten zu ändern.</span><span class="sxs-lookup"><span data-stu-id="c9d2a-116">When <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportContract%28System.ServiceModel.Description.WsdlExporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29> is called, the <xref:System.ServiceModel.Description.WsdlExporter> that is used to export the metadata and the <xref:System.ServiceModel.Description.WsdlContractConversionContext> that contains the service description objects are passed in as parameters enabling the modification of the exported metadata.</span></span>  
  
 <span data-ttu-id="c9d2a-117">In diesem Beispiel wird je nachdem, ob das Exportkontextobjekt über ein <xref:System.ServiceModel.Description.ContractDescription> oder ein <xref:System.ServiceModel.Description.OperationDescription> verfügt, mithilfe der Texteigenschaft eine Anmerkung aus dem Attribut extrahiert und dem WSDL-Anmerkungselement hinzugefügt (wie im folgenden Code gezeigt).</span><span class="sxs-lookup"><span data-stu-id="c9d2a-117">In this sample, depending upon whether the export context object has a <xref:System.ServiceModel.Description.ContractDescription> or an <xref:System.ServiceModel.Description.OperationDescription>, a comment is extracted from the attribute using the text property and is added to the WSDL annotation element as shown in the following code.</span></span>  
  
```csharp
public void ExportContract(WsdlExporter exporter, WsdlContractConversionContext context)
{
    if (contractDescription != null)
    {
        // Inside this block it is the contract-level comment attribute.
        // This.Text returns the string for the contract attribute.
        // Set the doc element; if this isn't done first, there is no XmlElement in the
        // DocumentElement property.
        context.WsdlPortType.Documentation = string.Empty;
        // Contract comments.
        XmlDocument owner = context.WsdlPortType.DocumentationElement.OwnerDocument;
        XmlElement summaryElement = owner.CreateElement("summary");
        summaryElement.InnerText = this.Text;
        context.WsdlPortType.DocumentationElement.AppendChild(summaryElement);
    }
    else
    {
        Operation operation = context.GetOperation(operationDescription);
        if (operation != null)
        {
            // We are dealing strictly with the operation here.
            // This.Text returns the string for the operation-level attributes.
            // Set the doc element; if this isn't done first, there is no XmlElement in the
            // DocumentElement property.
            operation.Documentation = String.Empty;

            // Operation C# triple comments.
            XmlDocument owner = operation.DocumentationElement.OwnerDocument;
            XmlElement newSummaryElement = owner.CreateElement("summary");
            newSummaryElement.InnerText = this.Text;
            operation.DocumentationElement.AppendChild(newSummaryElement);
        }
    }
}
```  
  
 <span data-ttu-id="c9d2a-118">Beim Exportieren eines Vorgangs ruft das Beispiel `WsdlParamOrReturnDocumentationAttribute`-Werte für Parameter und Rückgabewerte mittels Reflektion ab und fügt sie den WSDL-Anmerkungselementen hinzu (wie nachfolgend gezeigt).</span><span class="sxs-lookup"><span data-stu-id="c9d2a-118">If an operation is being exported, the sample uses reflection to obtain any `WsdlParamOrReturnDocumentationAttribute` values for parameters and return values and adds them to the WSDL annotation elements for that operation as follows.</span></span>  
  
```csharp
// Get returns information  
ParameterInfo returnValue = operationDescription.SyncMethod.ReturnParameter;  
object[] returnAttrs = returnValue.GetCustomAttributes(typeof(WsdlParamOrReturnDocumentationAttribute), false);  
if (returnAttrs.Length != 0)  
{  
    // <returns>text.</returns>  
    XmlElement returnsElement = owner.CreateElement("returns");  
    returnsElement.InnerText = ((WsdlParamOrReturnDocumentationAttribute)returnAttrs[0]).ParamComment;  
    operation.DocumentationElement.AppendChild(returnsElement);  
}  
  
// Get parameter information.  
ParameterInfo[] args = operationDescription.SyncMethod.GetParameters();  
for (int i = 0; i < args.Length; i++)  
{  
    object[] docAttrs = args[i].GetCustomAttributes(typeof(WsdlParamOrReturnDocumentationAttribute), false);  
    if (docAttrs.Length == 1)  
    {  
        // <param name="Int1">Text.</param>  
        XmlElement newParamElement = owner.CreateElement("param");  
        XmlAttribute paramName = owner.CreateAttribute("name");  
        paramName.Value = args[i].Name;  
        newParamElement.InnerText = ((WsdlParamOrReturnDocumentationAttribute)docAttrs[0]).ParamComment;  
        newParamElement.Attributes.Append(paramName);  
        operation.DocumentationElement.AppendChild(newParamElement);  
    }  
}  
```  
  
 <span data-ttu-id="c9d2a-119">Dann veröffentlicht das Beispiel die Metadaten auf die übliche Weise mit der folgenden Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="c9d2a-119">The sample then publishes metadata in the standard way, using the following configuration file.</span></span>  
  
```xml  
<services>  
  <service
      name="Microsoft.ServiceModel.Samples.CalculatorService"  
      behaviorConfiguration="CalculatorServiceBehavior">  
    <!-- ICalculator is exposed at the base address provided by host: http://localhost/servicemodelsamples/service.svc  -->  
    <endpoint address=""  
              binding="wsHttpBinding"  
              contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    <!-- the mex endpoint is exposed at http://localhost/servicemodelsamples/service.svc/mex -->  
    <endpoint address="mex"  
              binding="mexHttpBinding"  
              contract="IMetadataExchange" />  
  </service>  
</services>  
  
<!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      <serviceMetadata httpGetEnabled="True"/>  
      <serviceDebug includeExceptionDetailInFaults="False" />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="svcutil-client"></a><span data-ttu-id="c9d2a-120">Svcutil-Client</span><span class="sxs-lookup"><span data-stu-id="c9d2a-120">Svcutil client</span></span>  

 <span data-ttu-id="c9d2a-121">In diesem Beispiel wird Svcutil.exe nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="c9d2a-121">This sample does not use Svcutil.exe.</span></span> <span data-ttu-id="c9d2a-122">Der Vertrag wird in der Datei generatedClient.cs angegeben, so dass nach der Demonstration von benutzerdefiniertem WSDL-Import und Codegenerierung der Dienst aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="c9d2a-122">The contract is provided in the generatedClient.cs file so that after the sample demonstrates custom WSDL import and code generation, the service can be invoked.</span></span> <span data-ttu-id="c9d2a-123">Wenn Sie den folgenden benutzerdefinierten WSDL-Importer für dieses Beispiel verwenden möchten, können Sie Svcutil.exe ausführen und mit der Option `/svcutilConfig` den Pfad zu der in diesem Beispiel verwendeten Clientkonfigurationsdatei angeben, die auf die Bibliothek `WsdlDocumentation.dll` verweist.</span><span class="sxs-lookup"><span data-stu-id="c9d2a-123">To use the following custom WSDL importer for this example, you can run Svcutil.exe and specify the `/svcutilConfig` option, giving the path to the client configuration file used in this sample, which references the `WsdlDocumentation.dll` library.</span></span> <span data-ttu-id="c9d2a-124">Zum Laden des `WsdlDocumentationImporter` muss Svuctil.exe jedoch die Bibliothek `WsdlDocumentation.dll` finden und laden können, was bedeutet, dass sie entweder im globalen Assemblycache oder im Pfad registriert ist oder sich im selben Verzeichnis wie Svcutil.exe befindet.</span><span class="sxs-lookup"><span data-stu-id="c9d2a-124">To load the `WsdlDocumentationImporter`, however, Svuctil.exe must be able to locate and load the `WsdlDocumentation.dll` library, which means either that it is registered in the global assembly cache, in the path, or is in the same directory as Svcutil.exe.</span></span> <span data-ttu-id="c9d2a-125">Bei einem so grundlegenden Beispiel wie diesem ist es am einfachsten, wenn man Svcutil.exe und die Clientkonfigurationsdatei in dasselbe Verzeichnis wie `WsdlDocumentation.dll` kopiert und es von dort aus ausführt.</span><span class="sxs-lookup"><span data-stu-id="c9d2a-125">For a basic sample such as this, the easiest thing to do is to copy Svcutil.exe and the client configuration file into the same directory as `WsdlDocumentation.dll` and run it from there.</span></span>  
  
## <a name="the-custom-wsdl-importer"></a><span data-ttu-id="c9d2a-126">Der benutzerdefinierte WSDL-Importer</span><span class="sxs-lookup"><span data-stu-id="c9d2a-126">The Custom WSDL Importer</span></span>  

 <span data-ttu-id="c9d2a-127">Das benutzerdefinierte <xref:System.ServiceModel.Description.IWsdlImportExtension>-Objekt `WsdlDocumentationImporter` implementiert auch, dass <xref:System.ServiceModel.Description.IContractBehavior> und <xref:System.ServiceModel.Description.IOperationBehavior> den importierten Dienstendpunkten hinzugefügt und <xref:System.ServiceModel.Description.IServiceContractGenerationExtension> und <xref:System.ServiceModel.Description.IOperationContractGenerationExtension> zum Ändern der Codegenerierung aufgerufen werden, wenn der Vertrags- oder Vorgangscode erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="c9d2a-127">The custom <xref:System.ServiceModel.Description.IWsdlImportExtension> object `WsdlDocumentationImporter` also implements <xref:System.ServiceModel.Description.IContractBehavior> and <xref:System.ServiceModel.Description.IOperationBehavior> to be added to the imported ServiceEndpoints and <xref:System.ServiceModel.Description.IServiceContractGenerationExtension> and <xref:System.ServiceModel.Description.IOperationContractGenerationExtension> to be invoked to modify the code generation when the contract or operation code is being created.</span></span>  
  
 <span data-ttu-id="c9d2a-128">Zuerst bestimmt das Beispiel in der <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportContract%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29>-Methode, ob sich die WSDL-Anmerkung auf der Vertrags- oder der Vorgangsebene befindet und fügt sich selbst dem entsprechenden Bereich als Verhalten hinzu, wobei der importierte Anmerkungstext an ihren Konstruktor übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="c9d2a-128">First, in the <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportContract%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29> method, the sample determines whether the WSDL annotation is at the contract or operation level, and adds itself as a behavior at the appropriate scope, passing the imported annotation text to its constructor.</span></span>  
  
```csharp
public void ImportContract(WsdlImporter importer, WsdlContractConversionContext context)  
{  
    // Contract Documentation  
    if (context.WsdlPortType.Documentation != null)  
    {  
        // System examines the contract behaviors to see whether any implement IWsdlImportExtension.  
        context.Contract.Behaviors.Add(new WsdlDocumentationImporter(context.WsdlPortType.Documentation));  
    }  
    // Operation Documentation  
    foreach (Operation operation in context.WsdlPortType.Operations)  
    {  
        if (operation.Documentation != null)  
        {  
            OperationDescription operationDescription = context.Contract.Operations.Find(operation.Name);  
            if (operationDescription != null)  
            {  
                // System examines the operation behaviors to see whether any implement IWsdlImportExtension.  
                operationDescription.Behaviors.Add(new WsdlDocumentationImporter(operation.Documentation));  
            }  
        }  
    }  
}  
```  
  
 <span data-ttu-id="c9d2a-129">Wenn der Code dann generiert ist, ruft das System die <xref:System.ServiceModel.Description.IServiceContractGenerationExtension.GenerateContract%28System.ServiceModel.Description.ServiceContractGenerationContext%29>-Methode und die <xref:System.ServiceModel.Description.IOperationContractGenerationExtension.GenerateOperation%28System.ServiceModel.Description.OperationContractGenerationContext%29>-Methode auf, wobei die entsprechenden Kontextinformationen übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="c9d2a-129">Then, when the code is generated, the system invokes the <xref:System.ServiceModel.Description.IServiceContractGenerationExtension.GenerateContract%28System.ServiceModel.Description.ServiceContractGenerationContext%29> and <xref:System.ServiceModel.Description.IOperationContractGenerationExtension.GenerateOperation%28System.ServiceModel.Description.OperationContractGenerationContext%29> methods, passing the appropriate context information.</span></span> <span data-ttu-id="c9d2a-130">Die benutzerdefinierten WSDL-Anmerkungen werden formatiert und als Kommentare in das CodeDOM eingefügt.</span><span class="sxs-lookup"><span data-stu-id="c9d2a-130">The sample formats the custom WSDL annotations and inserts them as comments into the CodeDom.</span></span>  
  
```csharp
public void GenerateContract(ServiceContractGenerationContext context)  
{  
    Debug.WriteLine("In generate contract.");  
    context.ContractType.Comments.AddRange(FormatComments(text));  
}  
  
public void GenerateOperation(OperationContractGenerationContext context)  
{  
    context.SyncMethod.Comments.AddRange(FormatComments(text));  
    Debug.WriteLine("In generate operation.");  
}  
```  
  
## <a name="the-client-application"></a><span data-ttu-id="c9d2a-131">Die Clientanwendung</span><span class="sxs-lookup"><span data-stu-id="c9d2a-131">The Client Application</span></span>  

 <span data-ttu-id="c9d2a-132">Die Clientanwendung lädt den benutzerdefinierten WSDL-Importer, indem sie ihn in der Anwendungskonfigurationsdatei angibt.</span><span class="sxs-lookup"><span data-stu-id="c9d2a-132">The client application loads the custom WSDL importer by specifying it in the application configuration file.</span></span>  
  
```xml  
<client>  
  <endpoint address="http://localhost/servicemodelsamples/service.svc"
  binding="wsHttpBinding"
  contract="ICalculator" />  
  <metadata>  
    <wsdlImporters>  
      <extension type="Microsoft.ServiceModel.Samples.WsdlDocumentationImporter, WsdlDocumentation"/>  
    </wsdlImporters>  
  </metadata>  
</client>  
```  
  
 <span data-ttu-id="c9d2a-133">Nachdem das benutzerdefinierte Import Programm angegeben wurde, lädt das WCF-Metadatensystem den benutzerdefinierten Import in alle <xref:System.ServiceModel.Description.WsdlImporter> zu diesem Zweck erstellten.</span><span class="sxs-lookup"><span data-stu-id="c9d2a-133">Once the custom importer has been specified, the WCF metadata system loads the custom importer into any <xref:System.ServiceModel.Description.WsdlImporter> created for that purpose.</span></span> <span data-ttu-id="c9d2a-134">In diesem Beispiel werden die Metadaten mithilfe des <xref:System.ServiceModel.Description.MetadataExchangeClient> heruntergeladen, der <xref:System.ServiceModel.Description.WsdlImporter> wird entsprechend konfiguriert, um die Metadaten mit dem in dem Beispiel erstellten benutzerdefinierten Importer zu importieren, und die geänderten Vertragsinformationen werden mithilfe des <xref:System.ServiceModel.Description.ServiceContractGenerator> in Visual Basic- und C#-Clientcode kompiliert, der in Visual Studio verwendet werden kann, um IntelliSense zu unterstützen, oder der in XML-Dokumentation kompiliert werden kann.</span><span class="sxs-lookup"><span data-stu-id="c9d2a-134">This sample uses the <xref:System.ServiceModel.Description.MetadataExchangeClient> to download the metadata, the <xref:System.ServiceModel.Description.WsdlImporter> properly configured to import the metadata using the custom importer the sample creates, and the <xref:System.ServiceModel.Description.ServiceContractGenerator> to compile the modified contract information into both Visual Basic and C# client code that can be used in Visual Studio to support Intellisense or compiled into XML documentation.</span></span>  
  
```csharp
/// From WSDL Documentation:  
///
/// <summary>The ICalculator contract performs basic calculation
/// services.</summary>
///
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.ServiceContractAttribute(Namespace="http://Microsoft.ServiceModel.Samples", ConfigurationName="ICalculator")]  
public interface ICalculator  
{  
  
    /// From WSDL Documentation:  
    ///
    /// <summary>The Add operation adds two numbers and returns the
    /// result.</summary><returns>The result of adding the two arguments
    /// together.</returns><param name="n1">The first value to add.</param><param
    /// name="n2">The second value to add.</param>
    ///
    [System.ServiceModel.OperationContractAttribute(Action="http://Microsoft.ServiceModel.Samples/ICalculator/Add", ReplyAction="http://Microsoft.ServiceModel.Samples/ICalculator/AddResponse")]  
    double Add(double n1, double n2);  
  
    /// From WSDL Documentation:  
    ///
    /// <summary>The Subtract operation subtracts the second argument from the
    /// first.</summary><returns>The result of the second argument subtracted from the
    /// first.</returns><param name="n1">The value from which the second is
    /// subtracted.</param><param name="n2">The value that is subtracted from the
    /// first.</param>
    ///
    [System.ServiceModel.OperationContractAttribute(Action="http://Microsoft.ServiceModel.Samples/ICalculator/Subtract", ReplyAction="http://Microsoft.ServiceModel.Samples/ICalculator/SubtractResponse")]  
    double Subtract(double n1, double n2);  
  
    /// From WSDL Documentation:  
    ///
    /// <summary>The Multiply operation multiplies two values.</summary><returns>The
    /// result of multiplying the first and second arguments.</returns><param
    /// name="n1">The first value to multiply.</param><param name="n2">The second value
    /// to multiply.</param>
    ///
    [System.ServiceModel.OperationContractAttribute(Action="http://Microsoft.ServiceModel.Samples/ICalculator/Multiply", ReplyAction="http://Microsoft.ServiceModel.Samples/ICalculator/MultiplyResponse")]  
    double Multiply(double n1, double n2);  
  
    /// From WSDL Documentation:  
    ///
    /// <summary>The Divide operation returns the value of the first argument divided
    /// by the second argument.</summary><returns>The result of dividing the first
    /// argument by the second.</returns><param name="n1">The numerator.</param><param
    /// name="n2">The denominator.</param>
    ///
    [System.ServiceModel.OperationContractAttribute(Action="http://Microsoft.ServiceModel.Samples/ICalculator/Divide", ReplyAction="http://Microsoft.ServiceModel.Samples/ICalculator/DivideResponse")]  
    double Divide(double n1, double n2);  
}  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="c9d2a-135">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="c9d2a-135">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="c9d2a-136">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="c9d2a-136">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="c9d2a-137">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="c9d2a-137">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="c9d2a-138">Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="c9d2a-138">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="c9d2a-139">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="c9d2a-139">The samples may already be installed on your machine.</span></span> <span data-ttu-id="c9d2a-140">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="c9d2a-140">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="c9d2a-141">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c9d2a-141">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c9d2a-142">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="c9d2a-142">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Metadata\WsdlDocumentation`  
