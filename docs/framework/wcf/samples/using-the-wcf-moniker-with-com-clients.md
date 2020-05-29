---
title: Verwenden des WCF-Monikers mit COM-Clients
ms.date: 03/30/2017
ms.assetid: e2799bfe-88bd-49d7-9d6d-ac16a9b16b04
ms.openlocfilehash: c1d5e0c7d7460e207fedba601e991f25281ddb6e
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2020
ms.locfileid: "84202087"
---
# <a name="using-the-wcf-moniker-with-com-clients"></a><span data-ttu-id="ad863-102">Verwenden des WCF-Monikers mit COM-Clients</span><span class="sxs-lookup"><span data-stu-id="ad863-102">Using the WCF Moniker with COM Clients</span></span>
<span data-ttu-id="ad863-103">In diesem Beispiel wird veranschaulicht, wie der Windows Communication Foundation (WCF)-Dienstmoniker verwendet wird, um Webdienste in COM-basierte Entwicklungsumgebungen zu integrieren, z. b. Microsoft Office Visual Basic for Applications (Office VBA) oder Visual Basic 6,0.</span><span class="sxs-lookup"><span data-stu-id="ad863-103">This sample demonstrates how to use the Windows Communication Foundation (WCF) service moniker to integrate Web services into COM-based development environments, such as Microsoft Office Visual Basic for Applications (Office VBA) or Visual Basic 6.0.</span></span> <span data-ttu-id="ad863-104">Das Beispiel umfasst einen Windows Script Host-Client (.vbs), eine unterstützende Clientbibliothek (.dll) und eine Dienstbibliothek (.dll), die von Internetinformationsdienste (IIS) gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="ad863-104">This sample consists of a Windows Script Host client (.vbs), a supporting client library (.dll), and a service library (.dll) hosted by Internet Information Services (IIS).</span></span> <span data-ttu-id="ad863-105">Der Dienst ist ein Rechnerdienst und der COM-Client ruft mathematische Operationen (Addieren, Subtrahieren, Multiplizieren und Dividieren) auf dem Dienst auf.</span><span class="sxs-lookup"><span data-stu-id="ad863-105">The service is a calculator service and the COM client calls math operations—Add, Subtract, Multiply, and Divide—on the service.</span></span> <span data-ttu-id="ad863-106">Die Clientaktivität ist in den Meldungsfeldfenstern sichtbar.</span><span class="sxs-lookup"><span data-stu-id="ad863-106">Client activity is visible in the message box windows.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ad863-107">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="ad863-107">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="ad863-108">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="ad863-108">The samples may already be installed on your computer.</span></span> <span data-ttu-id="ad863-109">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="ad863-109">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="ad863-110">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ad863-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ad863-111">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="ad863-111">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Interop\COM`  
  
 <span data-ttu-id="ad863-112">Der Dienst implementiert einen `ICalculator`-Vertrag, dessen Definition im folgenden Codebeispiel veranschaulicht wird.</span><span class="sxs-lookup"><span data-stu-id="ad863-112">The service implements an `ICalculator` contract defined as shown in the following code example.</span></span>  
  
```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface ICalculator  
{  
    [OperationContract]  
    double Add(double n1, double n2);  
    [OperationContract]  
    double Subtract(double n1, double n2);  
    [OperationContract]  
    double Multiply(double n1, double n2);  
    [OperationContract]  
    double Divide(double n1, double n2);  
}  
```  
  
 <span data-ttu-id="ad863-113">Im Beispiel werden die drei alternativen Ansätze für die Verwendung des Monikers veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="ad863-113">The sample demonstrates the three alternative approaches for using the moniker:</span></span>  
  
- <span data-ttu-id="ad863-114">Typisierter Vertrag: Der Vertrag wird auf dem Clientcomputer als für COM sichtbarer Typ registriert.</span><span class="sxs-lookup"><span data-stu-id="ad863-114">Typed contract – The contract is registered as a COM visible type on the client computer.</span></span>  
  
- <span data-ttu-id="ad863-115">WSDL-Vertrag: Der Vertrag wird in Form eines WSDL-Dokuments angegeben.</span><span class="sxs-lookup"><span data-stu-id="ad863-115">WSDL contract – The contract is supplied in the form of a WSDL document.</span></span>  
  
- <span data-ttu-id="ad863-116">Metadatenaustausch-Vertrag: Der Vertrag wird zur Laufzeit von einem MEX-Endpunkt (Metadata Exchange) abgerufen.</span><span class="sxs-lookup"><span data-stu-id="ad863-116">Metadata Exchange contract – The contract is retrieved at runtime from a Metadata Exchange (MEX) endpoint.</span></span>  
  
## <a name="typed-contract"></a><span data-ttu-id="ad863-117">Typisierter Vertrag</span><span class="sxs-lookup"><span data-stu-id="ad863-117">Typed Contract</span></span>  
 <span data-ttu-id="ad863-118">Um den Moniker mit einem typisierten Vertrag zu verwenden, müssen auf geeignete Weise attributierte Typen für den Dienstvertrag mit COM registriert werden.</span><span class="sxs-lookup"><span data-stu-id="ad863-118">To use the moniker with a typed contract use, appropriately attributed types for the service contract must be registered with COM.</span></span> <span data-ttu-id="ad863-119">Zuerst muss ein Client mit dem [Service Model Metadata Utility-Tool (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)generiert werden.</span><span class="sxs-lookup"><span data-stu-id="ad863-119">First, a client must be generated by using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="ad863-120">Führen Sie den folgenden Befehl an einer Eingabeaufforderung im Clientverzeichnis aus, um den typisierten Proxy zu generieren.</span><span class="sxs-lookup"><span data-stu-id="ad863-120">Run the following command from a command prompt in the client directory to generate the typed proxy.</span></span>  
  
```console  
svcutil.exe /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples http://localhost/servicemodelsamples/service.svc /out:generatedClient.cs  
```  
  
 <span data-ttu-id="ad863-121">Diese Klasse muss in ein Projekt eingebunden werden, und das Projekt sollte so konfiguriert werden, dass es bei der Kompilierung eine für COM sichtbare, signierte Assembly generiert.</span><span class="sxs-lookup"><span data-stu-id="ad863-121">This class must be included in a project and the project should be configured to generate a COM-visible, signed assembly when compiled.</span></span> <span data-ttu-id="ad863-122">Das folgende Attribut muss in der Datei AssemblyInfo.cs enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="ad863-122">The following attribute should be included in the AssemblyInfo.cs file.</span></span>  
  
```csharp
[assembly: ComVisible(true)]  
```  
  
 <span data-ttu-id="ad863-123">Registrieren Sie nach dem Erstellen des Projekts die für COM sichtbaren Typen mit `regasm`, wie im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="ad863-123">After building the project, register the COM-visible types by using `regasm` as shown in the following example.</span></span>  
  
```console  
regasm.exe /tlb:CalcProxy.tlb client.dll  
```  
  
 <span data-ttu-id="ad863-124">Die erstellte Assembly sollte dem globalen Assemblycache hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="ad863-124">The assembly that is created should be added to the Global Assembly Cache.</span></span> <span data-ttu-id="ad863-125">Obwohl nicht streng erforderlich, wird hierdurch der Prozess vereinfacht, bei dem die Laufzeit die Assembly lokalisiert.</span><span class="sxs-lookup"><span data-stu-id="ad863-125">Though not strictly required, this simplifies the process of the runtime locating the assembly.</span></span> <span data-ttu-id="ad863-126">Mit dem folgenden Befehl wird die Assembly dem globalen Assemblycache hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ad863-126">The following command adds the assembly to the Global Assembly Cache.</span></span>  
  
```console  
gacutil.exe /i client.dll  
```  
  
> [!NOTE]
> <span data-ttu-id="ad863-127">Der Dienstmoniker erfordert nur die Typregistrierung und verwendet nicht den Proxy für die Kommunikation mit dem Dienst.</span><span class="sxs-lookup"><span data-stu-id="ad863-127">The service moniker requires only the type registration and does not use the proxy to communicate with the service.</span></span>  
  
 <span data-ttu-id="ad863-128">Die ComCalcClient.vbs-Clientanwendung nutzt die `GetObject`-Funktion, um einen Proxy für den Dienst zu erstellen, wobei die Dienstmonikersyntax für die Festlegung von Adresse, Bindung und Vertrag für den Dienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ad863-128">ComCalcClient.vbs client application uses the `GetObject` function to construct a proxy for the service, using the service moniker syntax to specify the address, binding, and contract for the service.</span></span>  
  
```vbscript
Set typedServiceMoniker = GetObject(  
"service4:address=http://localhost/ServiceModelSamples/service.svc, binding=wsHttpBinding,
contractType={9213C6D2-5A6F-3D26-839B-3BA9B82228D3}")  
```  
  
 <span data-ttu-id="ad863-129">Die vom Moniker verwendeten Parameter legen Folgendes fest:</span><span class="sxs-lookup"><span data-stu-id="ad863-129">The parameters used by the moniker specify:</span></span>  
  
- <span data-ttu-id="ad863-130">Die Adresse des Dienstendpunkts.</span><span class="sxs-lookup"><span data-stu-id="ad863-130">The address of the service endpoint.</span></span>  
  
- <span data-ttu-id="ad863-131">Die Bindung, die der Client verwenden sollte, um eine Verbindung mit diesem Endpunkt herzustellen.</span><span class="sxs-lookup"><span data-stu-id="ad863-131">The binding that the client should use to connect with that endpoint.</span></span> <span data-ttu-id="ad863-132">In diesem Fall wird die vom System definierte wsHttpBinding verwendet. Allerdings können auch benutzerdefinierte Bindungen in den Clientkonfigurationsdateien definiert werden.</span><span class="sxs-lookup"><span data-stu-id="ad863-132">In this case, the system-defined wsHttpBinding is used though custom bindings can be defined in client configuration files.</span></span> <span data-ttu-id="ad863-133">Für die Verwendung mit dem Windows Script Host wird die benutzerdefinierte Bindung in einer „Cscript.exe.config“-Datei im gleichen Verzeichnis wie „Cscript.exe“ definiert.</span><span class="sxs-lookup"><span data-stu-id="ad863-133">For use with the Windows Script Host, the custom binding is defined in a Cscript.exe.config file in the same directory as Cscript.exe.</span></span>  
  
- <span data-ttu-id="ad863-134">Der Typ des Vertrags, der vom Endpunkt unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="ad863-134">The type of the contract that is supported at the endpoint.</span></span> <span data-ttu-id="ad863-135">Dies ist der Typ, der oben generiert und registriert wurde.</span><span class="sxs-lookup"><span data-stu-id="ad863-135">This is the type that was generated and registered above.</span></span> <span data-ttu-id="ad863-136">Da Visual Basic Skript keine stark typisierte com-Umgebung bereitstellt, muss ein Bezeichner für den Vertrag angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ad863-136">Because Visual Basic script does not provide a strongly typed COM environment, an identifier for the contract must be specified.</span></span> <span data-ttu-id="ad863-137">Diese GUID ist die `interfaceID` aus "CalcProxy.tlb", die durch COM-Tools wie OLE/COM-Objektkatalog (OleView.exe) eingesehen werden kann.</span><span class="sxs-lookup"><span data-stu-id="ad863-137">This GUID is the `interfaceID` from CalcProxy.tlb, which can be viewed by using COM tools such as the OLE/COM Object Viewer (OleView.exe).</span></span> <span data-ttu-id="ad863-138">Bei stark typisierten Umgebungen wie Office VBA oder Visual Basic 6,0 können Sie anstelle des Vertrags Parameters einen expliziten Verweis auf die Typbibliothek hinzufügen und dann den Typ des Proxy Objekts deklarieren.</span><span class="sxs-lookup"><span data-stu-id="ad863-138">For strongly typed environments such as Office VBA or Visual Basic 6.0, adding an explicit reference to the type library and then declaring the type of the proxy object can be used in place of the contract parameter.</span></span> <span data-ttu-id="ad863-139">Auf diese Weise wird auch während der Clientanwendungsentwicklung IntelliSense-Unterstützung bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="ad863-139">This also provides IntelliSense support during client application development.</span></span>  
  
 <span data-ttu-id="ad863-140">Durch Erstellung der Proxyinstanz mit dem Dienstmoniker kann die Clientanwendung Methoden auf dem Proxy aufrufen. Dies führt dazu, dass die Dienstmonikerinfrastruktur die entsprechenden Dienstvorgänge aufruft.</span><span class="sxs-lookup"><span data-stu-id="ad863-140">Having constructed the proxy instance with the service moniker, the client application can call methods on the proxy, which results in the service moniker infrastructure calling the corresponding service operations.</span></span>  
  
```vbscript  
' Call the service operations using the moniker object  
WScript.Echo "Typed service moniker: 100 + 15.99 = " & typedServiceMoniker.Add(100, 15.99)  
```  
  
 Wenn Sie das Beispiel ausführen, werden die Antworten für den Vorgang in einem Windows Script Host-Meldungsfeldfenster angezeigt. Dies veranschaulicht, dass ein com-Client COM-Aufrufe durchführt, die den typisierten Moniker für die Kommunikation mit einem WCF-Dienst <span data-ttu-id="ad863-143">Trotz der Verwendung von COM in der Clientanwendung besteht die Kommunikation mit dem Dienst ausschließlich aus Webdienstaufrufen.</span><span class="sxs-lookup"><span data-stu-id="ad863-143">Despite the use of COM in the client application, the communication with the service consists only of Web service calls.</span></span>  
  
## <a name="wsdl-contract"></a><span data-ttu-id="ad863-144">WSDL-Vertrag</span><span class="sxs-lookup"><span data-stu-id="ad863-144">WSDL Contract</span></span>  
 <span data-ttu-id="ad863-145">Um den Moniker mit einem WSDL-Vertrag zu verwenden, ist keine Registrierung der Clientbibliothek erforderlich. Allerdings muss der WSDL-Vertrag für den Dienst über einen Out-of-Band-Mechanismus abgerufen werden, wie beispielsweise die Verwendung eines Browsers für den Zugriff auf den WSDL-Endpunkt des Diensts.</span><span class="sxs-lookup"><span data-stu-id="ad863-145">To use the moniker with a WSDL contract, no client library registration is required but the WSDL contract for the service must be retrieved through an out-of-band mechanism such as using a browser to access the WSDL endpoint for the service.</span></span> <span data-ttu-id="ad863-146">Der Moniker kann dann bei Ausführungszeit auf diesen Vertrag zugreifen.</span><span class="sxs-lookup"><span data-stu-id="ad863-146">The moniker can then access that contract at execution time.</span></span>  
  
 <span data-ttu-id="ad863-147">Die Clientanwendung ComCalcClient.vbs nutzt `FileSystemObject`, um auf die lokal gespeicherte WSDL-Datei zuzugreifen. Anschließend wird mithilfe der `GetObject`-Funktion ein Proxy für den Dienst erstellt.</span><span class="sxs-lookup"><span data-stu-id="ad863-147">The ComCalcClient.vbs client application uses the `FileSystemObject` to access the locally saved WSDL file and then again uses the `GetObject` function to construct a proxy for the service.</span></span>  
  
```vbscript  
' Open the WSDL contract file and read it all into the wsdlContract string  
Const ForReading = 1  
Set objFSO = CreateObject("Scripting.FileSystemObject")  
Set objFile = objFSO.OpenTextFile("serviceWsdl.xml", ForReading)  
wsdlContract = objFile.ReadAll  
objFile.Close  
  
' Create a string for the service moniker including the content of the WSDL contract file  
wsdlMonikerString = "service4:address='http://localhost/ServiceModelSamples/service.svc'"  
wsdlMonikerString = wsdlMonikerString + ", binding=WSHttpBinding_ICalculator, bindingNamespace='http://Microsoft.ServiceModel.Samples'"  
wsdlMonikerString = wsdlMonikerString + ", wsdl='" & wsdlContract & "'"  
wsdlMonikerString = wsdlMonikerString + ", contract=ICalculator, contractNamespace='http://Microsoft.ServiceModel.Samples'"  
  
' Create the service moniker object  
Set wsdlServiceMoniker = GetObject(wsdlMonikerString)  
```  
  
 <span data-ttu-id="ad863-148">Die vom Moniker verwendeten Parameter legen Folgendes fest:</span><span class="sxs-lookup"><span data-stu-id="ad863-148">The parameters used by the moniker specify:</span></span>  
  
- <span data-ttu-id="ad863-149">Die Adresse des Dienstendpunkts.</span><span class="sxs-lookup"><span data-stu-id="ad863-149">The address of the service endpoint.</span></span>  
  
- <span data-ttu-id="ad863-150">Die Bindung, die der Client verwenden sollte, um eine Verbindung mit diesem Endpunkt herzustellen, und der Namespace, in dem diese Bindung definiert ist.</span><span class="sxs-lookup"><span data-stu-id="ad863-150">The binding that the client should use to connect with that endpoint and the namespace in which that binding is defined.</span></span> <span data-ttu-id="ad863-151">In diesem Fall wird `wsHttpBinding_ICalculator` verwendet.</span><span class="sxs-lookup"><span data-stu-id="ad863-151">In this case, the `wsHttpBinding_ICalculator` is used.</span></span>  
  
- <span data-ttu-id="ad863-152">Die WSDL, die den Vertrag definiert.</span><span class="sxs-lookup"><span data-stu-id="ad863-152">The WSDL that defines the contract.</span></span> <span data-ttu-id="ad863-153">In diesem Fall ist dies die Zeichenfolge, die aus der Datei "serviceWsdl.xml" gelesen wurde.</span><span class="sxs-lookup"><span data-stu-id="ad863-153">In this case this is the string that has been read from the serviceWsdl.xml file.</span></span>  
  
- <span data-ttu-id="ad863-154">Der Name und Namespace des Vertrags.</span><span class="sxs-lookup"><span data-stu-id="ad863-154">The name and namespace of the contract.</span></span> <span data-ttu-id="ad863-155">Diese Identifikation ist erforderlich, da die WSDL möglicherweise mehr als einen Vertrag enthält.</span><span class="sxs-lookup"><span data-stu-id="ad863-155">This identification is required because the WSDL may contain more than one contract.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="ad863-156">Standardmäßig generieren WCF-Dienste separate WSDL-Dateien für jeden Namespace, der von verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ad863-156">By default, WCF services generate separate WSDL files for each namespace that the use.</span></span> <span data-ttu-id="ad863-157">Diese werden mit der Verwendung des WSDL-Importkonstrukts verknüpft.</span><span class="sxs-lookup"><span data-stu-id="ad863-157">These are linked with the use of the WSDL import construct.</span></span> <span data-ttu-id="ad863-158">Da der Moniker eine einzige WSDL-Definition erwartet, muss der Dienst entweder einen einzigen Namespace verwenden (wie in diesem Beispiel gezeigt), oder die separaten Dateien müssen manuell zusammengeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ad863-158">Because the moniker expects a single WSDL definition, the service must either use a single namespace as demonstrated in this sample or the separate files must be manually merged.</span></span>  
  
 <span data-ttu-id="ad863-159">Durch Erstellung der Proxyinstanz mit dem Dienstmoniker kann die Clientanwendung Methoden auf dem Proxy aufrufen. Dies führt dazu, dass die Dienstmonikerinfrastruktur die entsprechenden Dienstvorgänge aufruft.</span><span class="sxs-lookup"><span data-stu-id="ad863-159">Having constructed the proxy instance with the service moniker, the client application can call methods on the proxy, which results in the service moniker infrastructure calling the corresponding service operations.</span></span>  
  
```vbscript  
' Call the service operations using the moniker object  
WScript.Echo "WSDL service moniker: 145 - 76.54 = " & wsdlServiceMoniker.Subtract(145, 76.54)  
```  
  
 Wenn Sie das Beispiel ausführen, werden die Antworten für den Vorgang in einem Windows Script Host-Meldungsfeldfenster angezeigt. <span data-ttu-id="ad863-161">Dadurch wird veranschaulicht, wie ein com-Client COM-Aufrufe mithilfe des Monikers mit einem WSDL-Vertrag für die Kommunikation mit einem WCF-Dienst durchführt.</span><span class="sxs-lookup"><span data-stu-id="ad863-161">This demonstrates a COM client making COM calls using the moniker with a WSDL contract to communicate with a WCF service.</span></span>  
  
## <a name="metadata-exchange-contract"></a><span data-ttu-id="ad863-162">Metadatenaustausch-Vertrag</span><span class="sxs-lookup"><span data-stu-id="ad863-162">Metadata Exchange Contract</span></span>  
 <span data-ttu-id="ad863-163">Um den Moniker mit einem MEX-Vertrag zu verwenden, ist wie bei einem WSDL-Vertrag keine Clientregistrierung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ad863-163">To use the moniker with a MEX contract, as with the WSDL contract, no client registration is required.</span></span> <span data-ttu-id="ad863-164">Der Vertrag für den Dienst wird bei Ausführungszeit durch die interne Verwendung von Metadatenaustausch abgerufen.</span><span class="sxs-lookup"><span data-stu-id="ad863-164">The contract for the service is retrieved at execution time through the internal use of Metadata Exchange.</span></span>  
  
 <span data-ttu-id="ad863-165">Die Clientanwendung ComCalcClient.vbs verwendet wieder die `GetObject`-Funktion, um einen Proxy für den Dienst zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ad863-165">The ComCalcClient.vbs client application again uses the `GetObject` function to construct a proxy for the service.</span></span>  
  
```vbscript  
' Create a string for the service moniker specifying the address to retrieve the service metadata from  
mexMonikerString = "service4:mexAddress='http://localhost/servicemodelsamples/service.svc/mex'"  
mexMonikerString = mexMonikerString + ", address='http://localhost/ServiceModelSamples/service.svc'"  
mexMonikerString = mexMonikerString + ", binding=WSHttpBinding_ICalculator, bindingNamespace='http://Microsoft.ServiceModel.Samples'"  
mexMonikerString = mexMonikerString + ", contract=ICalculator, contractNamespace='http://Microsoft.ServiceModel.Samples'"  
  
' Create the service moniker object  
Set mexServiceMoniker = GetObject(mexMonikerString)  
```  
  
 <span data-ttu-id="ad863-166">Die vom Moniker verwendeten Parameter legen Folgendes fest:</span><span class="sxs-lookup"><span data-stu-id="ad863-166">The parameters used by the moniker specify:</span></span>  
  
- <span data-ttu-id="ad863-167">Die Adresse des Metadatenaustausch-Endpunkts des Diensts.</span><span class="sxs-lookup"><span data-stu-id="ad863-167">The address of the service metadata exchange endpoint.</span></span>  
  
- <span data-ttu-id="ad863-168">Die Adresse des Dienstendpunkts.</span><span class="sxs-lookup"><span data-stu-id="ad863-168">The address of the service endpoint.</span></span>  
  
- <span data-ttu-id="ad863-169">Die Bindung, die der Client verwenden sollte, um eine Verbindung mit diesem Endpunkt herzustellen, und der Namespace, in dem diese Bindung definiert ist.</span><span class="sxs-lookup"><span data-stu-id="ad863-169">The binding that the client should use to connect with that endpoint and the namespace in which that binding is defined.</span></span> <span data-ttu-id="ad863-170">In diesem Fall wird `wsHttpBinding_ICalculator` verwendet.</span><span class="sxs-lookup"><span data-stu-id="ad863-170">In this case, the `wsHttpBinding_ICalculator` is used.</span></span>  
  
- <span data-ttu-id="ad863-171">Der Name und Namespace des Vertrags.</span><span class="sxs-lookup"><span data-stu-id="ad863-171">The name and namespace of the contract.</span></span> <span data-ttu-id="ad863-172">Diese Identifikation ist erforderlich, da die WSDL möglicherweise mehr als einen Vertrag enthält.</span><span class="sxs-lookup"><span data-stu-id="ad863-172">This identification is required because the WSDL may contain more than one contract.</span></span>  
  
 <span data-ttu-id="ad863-173">Durch Erstellung der Proxyinstanz mit dem Dienstmoniker kann die Clientanwendung Methoden auf dem Proxy aufrufen. Dies führt dazu, dass die Dienstmonikerinfrastruktur die entsprechenden Dienstvorgänge aufruft.</span><span class="sxs-lookup"><span data-stu-id="ad863-173">Having constructed the proxy instance with the service moniker, the client application can call methods on the proxy, which results in the service moniker infrastructure calling the corresponding service operations.</span></span>  
  
```vbscript  
' Call the service operations using the moniker object  
WScript.Echo "MEX service moniker: 9 * 81.25 = " & mexServiceMoniker.Multiply(9, 81.25)  
```  
  
 Wenn Sie das Beispiel ausführen, werden die Antworten für den Vorgang in einem Windows Script Host-Meldungsfeldfenster angezeigt. <span data-ttu-id="ad863-175">Dadurch wird veranschaulicht, wie ein com-Client COM-Aufrufe mithilfe des Monikers mit einem MEX-Vertrag für die Kommunikation mit einem WCF-Dienst durchführt.</span><span class="sxs-lookup"><span data-stu-id="ad863-175">This demonstrates a COM client making COM calls using the moniker with a MEX contract to communicate with a WCF service.</span></span>  
  
#### <a name="to-set-up-and-build-the-sample"></a><span data-ttu-id="ad863-176">So richten Sie das Beispiel ein und erstellen es</span><span class="sxs-lookup"><span data-stu-id="ad863-176">To set up and build the sample</span></span>  
  
1. <span data-ttu-id="ad863-177">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="ad863-177">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="ad863-178">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="ad863-178">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="ad863-179">Öffnen Sie in einer Developer-Eingabeaufforderung für Visual Studio den Ordner "\client\bin" unter dem sprachspezifischen Ordner.</span><span class="sxs-lookup"><span data-stu-id="ad863-179">From a Developer Command Prompt for Visual Studio, open the \client\bin folder, under the language-specific folder.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="ad863-180">Wenn Sie Windows Vista, Windows Server 2008, Windows 7 oder Windows Server 2008 R2 verwenden, stellen Sie sicher, dass Sie die Eingabeaufforderung mit Administratorrechten ausführen.</span><span class="sxs-lookup"><span data-stu-id="ad863-180">If you are using Windows Vista, Windows Server 2008, Windows 7, or Windows Server 2008 R2, make sure that you run the command prompt with administrator privileges.</span></span>  
  
4. <span data-ttu-id="ad863-181">Geben `tlbexp.exe client.dll /out:CalcProxy.tlb` Sie ein, um die dll in eine TLB-Datei zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="ad863-181">Type in `tlbexp.exe client.dll /out:CalcProxy.tlb` to export the dll to a tlb file.</span></span> <span data-ttu-id="ad863-182">Eventuell wird eine "Typbibliothekexporter-Warnung" ausgegeben. Diese stellt jedoch kein Problem dar, da der generische Typ nicht benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="ad863-182">A "Type library exporter warning" is expected but is not an issue because the generic type is not required.</span></span>  
  
5. <span data-ttu-id="ad863-183">Geben `regasm.exe /tlb:CalcProxy.tlb client.dll` Sie ein, um die Typen bei com zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="ad863-183">Type in `regasm.exe /tlb:CalcProxy.tlb client.dll` to register the types with COM.</span></span> <span data-ttu-id="ad863-184">Eventuell wird eine "Typbibliothekexporter-Warnung" ausgegeben. Diese stellt jedoch kein Problem dar, da der generische Typ nicht benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="ad863-184">A "Type library exporter warning" is expected but is not an issue because the generic type is not required.</span></span>  
  
6. <span data-ttu-id="ad863-185">Geben Sie ein `gacutil.exe /i client.dll` , um die Assembly dem globalen Assemblycache hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="ad863-185">Type in `gacutil.exe /i client.dll` to add the assembly to the Global Assembly Cache.</span></span>  
  
#### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="ad863-186">So führen Sie das Beispiel auf demselben Computer aus</span><span class="sxs-lookup"><span data-stu-id="ad863-186">To run the sample on the same computer</span></span>  
  
1. <span data-ttu-id="ad863-187">Überprüfen Sie, ob Sie über einen Browser auf den Dienst zugreifen können, indem Sie die folgende Adresse eingeben: `http://localhost/servicemodelsamples/service.svc` .</span><span class="sxs-lookup"><span data-stu-id="ad863-187">Test that you can access the service using a browser by typing in the following address: `http://localhost/servicemodelsamples/service.svc`.</span></span> <span data-ttu-id="ad863-188">Als Antwort sollte eine Bestätigungsseite angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ad863-188">A confirmation page should be displayed in response.</span></span>  
  
2. <span data-ttu-id="ad863-189">Führen Sie die Datei "ComCalcClient.vbs" aus dem Ordner "\client" unter dem sprachspezifischen Ordner aus.</span><span class="sxs-lookup"><span data-stu-id="ad863-189">Run ComCalcClient.vbs from \client, from under the language-specific folder.</span></span> <span data-ttu-id="ad863-190">Die Clientaktivität wird in den Meldungsfeldfenstern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ad863-190">Client activity is displayed in message box windows.</span></span>  
  
3. <span data-ttu-id="ad863-191">Wenn der Client und der Dienst nicht kommunizieren können, finden Sie unter [Tipps zur Problembehandlung für WCF-Beispiele](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="ad863-191">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
#### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="ad863-192">So führen Sie das Beispiel computerübergreifend aus</span><span class="sxs-lookup"><span data-stu-id="ad863-192">To run the sample across computers</span></span>  
  
1. <span data-ttu-id="ad863-193">Erstellen Sie auf dem Dienstcomputer ein virtuelles Verzeichnis mit dem Namen ServiceModelSamples.</span><span class="sxs-lookup"><span data-stu-id="ad863-193">On the service computer, create a virtual directory named ServiceModelSamples.</span></span> <span data-ttu-id="ad863-194">Zum Erstellen des Festplattenverzeichnisses und des virtuellen Verzeichnisses kann das im Beispiel enthaltene Skript Setupvroot.bat verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ad863-194">The Setupvroot.bat script included with the sample can be used to create the disk directory and virtual directory.</span></span>  
  
2. <span data-ttu-id="ad863-195">Kopieren Sie die Dienstprogrammdateien aus %SystemDrive%\Inetpub\wwwroot\servicemodelsamples in das virtuelle Verzeichnis ServiceModelSamples auf dem Dienstcomputer.</span><span class="sxs-lookup"><span data-stu-id="ad863-195">Copy the service program files from %SystemDrive%\Inetpub\wwwroot\servicemodelsamples to the ServiceModelSamples virtual directory on the service computer.</span></span> <span data-ttu-id="ad863-196">Stellen Sie sicher, dass Sie die Dateien in das Verzeichnis \bin einfügen.</span><span class="sxs-lookup"><span data-stu-id="ad863-196">Be sure to include the files in the \bin directory.</span></span>  
  
3. <span data-ttu-id="ad863-197">Kopieren Sie die Skriptdatei aus dem Ordner \client (unterhalb des sprachspezifischen Ordners) auf den Clientcomputer.</span><span class="sxs-lookup"><span data-stu-id="ad863-197">Copy the client script file from the \client folder, under the language-specific folder, to the client computer.</span></span>  
  
4. <span data-ttu-id="ad863-198">Ändern Sie in der Skriptdatei den Adresswert der Endpunktdefinition, sodass dieser mit der neuen Adresse Ihres Diensts übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="ad863-198">In the script file, change the address value of the endpoint definition to match the new address of your service.</span></span> <span data-ttu-id="ad863-199">Ersetzen Sie alle Verweise auf localhost in der Adresse durch einen vollqualifizierten Domänennamen.</span><span class="sxs-lookup"><span data-stu-id="ad863-199">Replace any references to "localhost" with a fully-qualified domain name in the address.</span></span>  
  
5. <span data-ttu-id="ad863-200">Kopieren Sie die WSDL-Datei auf den Clientcomputer.</span><span class="sxs-lookup"><span data-stu-id="ad863-200">Copy the WSDL file to the client computer.</span></span> <span data-ttu-id="ad863-201">Ersetzen Sie in der WSDL-Datei serviceWsdl.xml alle Verweise auf localhost in der Adresse durch einen vollqualifizierten Domänennamen.</span><span class="sxs-lookup"><span data-stu-id="ad863-201">In the WSDL file, serviceWsdl.xml, replace any references to "localhost" with a fully-qualified domain name in the address.</span></span>  
  
6. <span data-ttu-id="ad863-202">Kopieren Sie die Bibliothek Client.dll aus dem Ordner \client\bin (unterhalb des sprachspezifischen Ordners) in ein Verzeichnis auf dem Clientcomputer.</span><span class="sxs-lookup"><span data-stu-id="ad863-202">Copy the Client.dll library from the \client\bin folder, under the language-specific folder, to a directory on the client computer.</span></span>  
  
7. <span data-ttu-id="ad863-203">Navigieren Sie an einer Eingabeaufforderung zu diesem Zielverzeichnis auf dem Clientcomputer.</span><span class="sxs-lookup"><span data-stu-id="ad863-203">From a command prompt, navigate to that destination directory on the client computer.</span></span> <span data-ttu-id="ad863-204">Wenn Sie Windows Vista oder Windows Server 2008 verwenden, stellen Sie sicher, dass Sie die Eingabeaufforderung als Administrator ausführen.</span><span class="sxs-lookup"><span data-stu-id="ad863-204">If using Windows Vista or Windows Server 2008, make sure to run the command prompt as Administrator.</span></span>  
  
8. <span data-ttu-id="ad863-205">Geben `tlbexp.exe client.dll /out:CalcProxy.tlb` Sie ein, um die dll in eine TLB-Datei zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="ad863-205">Type in `tlbexp.exe client.dll /out:CalcProxy.tlb` to export the dll to a tlb file.</span></span> <span data-ttu-id="ad863-206">Eventuell wird eine "Typbibliothekexporter-Warnung" ausgegeben. Diese stellt jedoch kein Problem dar, da der generische Typ nicht benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="ad863-206">A "Type library exporter warning" is expected but is not an issue because the generic type is not required.</span></span>  
  
9. <span data-ttu-id="ad863-207">Geben `regasm.exe /tlb:CalcProxy.tlb client.dll` Sie ein, um die Typen bei com zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="ad863-207">Type in `regasm.exe /tlb:CalcProxy.tlb client.dll` to register the types with COM.</span></span> <span data-ttu-id="ad863-208">Stellen Sie sicher, dass der Pfad auf den Ordner festgelegt wurde, der enthält, `regasm.exe` bevor Sie den Befehl ausführen.</span><span class="sxs-lookup"><span data-stu-id="ad863-208">Ensure that path has been set to the folder that contains `regasm.exe` before you run the command.</span></span>  
  
10. <span data-ttu-id="ad863-209">Geben Sie ein `gacutil.exe /i client.dll` , um die Assembly dem globalen Assemblycache hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="ad863-209">Type in `gacutil.exe /i client.dll` to add the assembly to the Global Assembly Cache.</span></span> <span data-ttu-id="ad863-210">Stellen Sie sicher, dass der Pfad auf den Ordner festgelegt wurde, der enthält, `gacutil.exe` bevor Sie den Befehl ausführen.</span><span class="sxs-lookup"><span data-stu-id="ad863-210">Ensure that path has been set to the folder that contains `gacutil.exe` before you run the command.</span></span>  
  
11. <span data-ttu-id="ad863-211">Testen Sie, ob Sie mit einem Browser vom Clientcomputer auf den Dienst zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="ad863-211">Test that you can access the service from the client computer using a browser.</span></span>  
  
12. <span data-ttu-id="ad863-212">Starten Sie auf dem Clientcomputer ComCalcClient.vbs.</span><span class="sxs-lookup"><span data-stu-id="ad863-212">On the client computer, launch ComCalcClient.vbs.</span></span>  
  
#### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="ad863-213">So stellen Sie den Zustand vor Ausführung des Beispiels wieder her</span><span class="sxs-lookup"><span data-stu-id="ad863-213">To clean up after the sample</span></span>  
  
- <span data-ttu-id="ad863-214">Entfernen Sie aus Sicherheitsgründen die Definition des virtuellen Verzeichnisses und die in den Setupschritten gewährten Berechtigungen, wenn Sie die Beispiele abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="ad863-214">For security purposes, remove the virtual directory definition and permissions granted in the setup steps when you are finished with the samples.</span></span>  
