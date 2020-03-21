---
title: Benutzerdefinierte WSDL-Veröffentlichung
ms.date: 03/30/2017
ms.assetid: 3b3e8103-2c95-4db3-a05b-46aa8e9d4d29
ms.openlocfilehash: ae6d5fdf243d5000090e993bd3353c6180d0ccaa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79145058"
---
# <a name="custom-wsdl-publication"></a>Benutzerdefinierte WSDL-Veröffentlichung
In diesem Beispiel wird Folgendes veranschaulicht:  
  
- Eine <xref:System.ServiceModel.Description.IWsdlExportExtension?displayProperty=nameWithType> in einem benutzerdefinierten <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType>-Attribut zum Exportieren von Attributeigenschaften als WSDL-Anmerkungen implementieren.  
  
- <xref:System.ServiceModel.Description.IWsdlImportExtension?displayProperty=nameWithType> zum Importieren der benutzerdefinierten WSDL-Anmerkungen implementieren.  
  
- <xref:System.ServiceModel.Description.IServiceContractGenerationExtension?displayProperty=nameWithType> und <xref:System.ServiceModel.Description.IOperationContractGenerationExtension?displayProperty=nameWithType> in einem benutzerdefinierten Vertragsverhalten bzw. Vorgangsverhalten definieren, um importierte Anmerkungen als Anmerkungen in die CodeDom für den importieren Vertrag bzw. Vorgang zu schreiben.  
  
- Verwenden <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> Sie die zum Herunterladen <xref:System.ServiceModel.Description.WsdlImporter?displayProperty=nameWithType> der WSDL, zum Importieren der WSDL <xref:System.ServiceModel.Description.ServiceContractGenerator?displayProperty=nameWithType> mithilfe des benutzerdefinierten WSDL-Importers und zum Generieren von Windows Communication Foundation (WCF)-Clientcode mit den WSDL-Anmerkungen als //- und ''' Kommentare in C' und Visual Basic.  
  
> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
## <a name="service"></a>Dienst  
 Der Dienst in diesem Beispiel ist mit zwei benutzerdefinierten Attributen versehen. Das erste Attribut (`WsdlDocumentationAttribute`) nimmt eine Zeichenfolge im Konstruktor entgegen und kann angewendet werden, um eine Vertragsschnittstelle oder einen -vorgang mit einer Zeichenfolge zur Verfügung zu stellen, die dessen Verwendung beschreibt. Das zweite Attribut (`WsdlParamOrReturnDocumentationAttribute`) kann zum Zurückgeben von Werten oder Parametern verwendet werden, um diese Werte im Vorgang zu beschreiben. Das folgende Beispiel zeigt einen Dienstvertrag (`ICalculator`), der mit diesen Attributen beschrieben wird.  
  
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
  
 Das `WsdlDocumentationAttribute` implementiert <xref:System.ServiceModel.Description.IContractBehavior> und <xref:System.ServiceModel.Description.IOperationBehavior>, daher werden die Attributinstanzen beim Öffnen des Diensts zur entsprechenden <xref:System.ServiceModel.Description.ContractDescription> oder <xref:System.ServiceModel.Description.OperationDescription> hinzugefügt. Außerdem implementiert das Attribut <xref:System.ServiceModel.Description.IWsdlExportExtension>. Beim Aufruf von <xref:System.ServiceModel.Description.IWsdlExportExtension.ExportContract%28System.ServiceModel.Description.WsdlExporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29> werden <xref:System.ServiceModel.Description.WsdlExporter> (das zum Exportieren der Metadaten verwendet wird) und <xref:System.ServiceModel.Description.WsdlContractConversionContext> (das die Dienstbeschreibungsobjekte enthält) als Parameter übergeben, was ermöglicht, die exportierten Metadaten zu ändern.  
  
 In diesem Beispiel wird je nachdem, ob das Exportkontextobjekt über ein <xref:System.ServiceModel.Description.ContractDescription> oder ein <xref:System.ServiceModel.Description.OperationDescription> verfügt, mithilfe der Texteigenschaft eine Anmerkung aus dem Attribut extrahiert und dem WSDL-Anmerkungselement hinzugefügt (wie im folgenden Code gezeigt).  
  
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
  
 Beim Exportieren eines Vorgangs ruft das Beispiel `WsdlParamOrReturnDocumentationAttribute`-Werte für Parameter und Rückgabewerte mittels Reflektion ab und fügt sie den WSDL-Anmerkungselementen hinzu (wie nachfolgend gezeigt).  
  
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
  
 Dann veröffentlicht das Beispiel die Metadaten auf die übliche Weise mit der folgenden Konfigurationsdatei.  
  
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
  
## <a name="svcutil-client"></a>Svcutil-Client  
 In diesem Beispiel wird Svcutil.exe nicht verwendet. Der Vertrag wird in der Datei generatedClient.cs angegeben, so dass nach der Demonstration von benutzerdefiniertem WSDL-Import und Codegenerierung der Dienst aufgerufen werden kann. Wenn Sie den folgenden benutzerdefinierten WSDL-Importer für dieses Beispiel verwenden möchten, können Sie Svcutil.exe ausführen und mit der Option `/svcutilConfig` den Pfad zu der in diesem Beispiel verwendeten Clientkonfigurationsdatei angeben, die auf die Bibliothek `WsdlDocumentation.dll` verweist. Zum Laden des `WsdlDocumentationImporter` muss Svuctil.exe jedoch die Bibliothek `WsdlDocumentation.dll` finden und laden können, was bedeutet, dass sie entweder im globalen Assemblycache oder im Pfad registriert ist oder sich im selben Verzeichnis wie Svcutil.exe befindet. Bei einem so grundlegenden Beispiel wie diesem ist es am einfachsten, wenn man Svcutil.exe und die Clientkonfigurationsdatei in dasselbe Verzeichnis wie `WsdlDocumentation.dll` kopiert und es von dort aus ausführt.  
  
## <a name="the-custom-wsdl-importer"></a>Der benutzerdefinierte WSDL-Importer  
 Das benutzerdefinierte <xref:System.ServiceModel.Description.IWsdlImportExtension>-Objekt `WsdlDocumentationImporter` implementiert auch, dass <xref:System.ServiceModel.Description.IContractBehavior> und <xref:System.ServiceModel.Description.IOperationBehavior> den importierten Dienstendpunkten hinzugefügt und <xref:System.ServiceModel.Description.IServiceContractGenerationExtension> und <xref:System.ServiceModel.Description.IOperationContractGenerationExtension> zum Ändern der Codegenerierung aufgerufen werden, wenn der Vertrags- oder Vorgangscode erstellt wird.  
  
 Zuerst bestimmt das Beispiel in der <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportContract%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29>-Methode, ob sich die WSDL-Anmerkung auf der Vertrags- oder der Vorgangsebene befindet und fügt sich selbst dem entsprechenden Bereich als Verhalten hinzu, wobei der importierte Anmerkungstext an ihren Konstruktor übergeben wird.  
  
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
  
 Wenn der Code dann generiert ist, ruft das System die <xref:System.ServiceModel.Description.IServiceContractGenerationExtension.GenerateContract%28System.ServiceModel.Description.ServiceContractGenerationContext%29>-Methode und die <xref:System.ServiceModel.Description.IOperationContractGenerationExtension.GenerateOperation%28System.ServiceModel.Description.OperationContractGenerationContext%29>-Methode auf, wobei die entsprechenden Kontextinformationen übergeben werden. Die benutzerdefinierten WSDL-Anmerkungen werden formatiert und als Kommentare in das CodeDOM eingefügt.  
  
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
  
## <a name="the-client-application"></a>Die Clientanwendung  
 Die Clientanwendung lädt den benutzerdefinierten WSDL-Importer, indem sie ihn in der Anwendungskonfigurationsdatei angibt.  
  
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
  
 Nachdem der benutzerdefinierte Importer angegeben wurde, lädt das WCF-Metadatensystem den benutzerdefinierten Importer in einen beliebigen <xref:System.ServiceModel.Description.WsdlImporter> Import, der zu diesem Zweck erstellt wurde. In diesem Beispiel werden die Metadaten mithilfe des <xref:System.ServiceModel.Description.MetadataExchangeClient> heruntergeladen, der <xref:System.ServiceModel.Description.WsdlImporter> wird entsprechend konfiguriert, um die Metadaten mit dem in dem Beispiel erstellten benutzerdefinierten Importer zu importieren, und die geänderten Vertragsinformationen werden mithilfe des <xref:System.ServiceModel.Description.ServiceContractGenerator> in Visual Basic- und C#-Clientcode kompiliert, der in Visual Studio verwendet werden kann, um IntelliSense zu unterstützen, oder der in XML-Dokumentation kompiliert werden kann.  
  
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
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Stellen Sie sicher, dass Sie das [einmalige Setupverfahren für die Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)durchgeführt haben.  
  
2. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
3. Um das Beispiel in einer Konfiguration mit einem oder einer maschinellen Konfiguration auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Metadata\WsdlDocumentation`  
