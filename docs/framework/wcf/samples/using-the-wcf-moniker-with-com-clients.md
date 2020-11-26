---
title: Verwenden des WCF-Monikers mit COM-Clients
ms.date: 03/30/2017
ms.assetid: e2799bfe-88bd-49d7-9d6d-ac16a9b16b04
ms.openlocfilehash: eb2f14db8b58fd182bbe711bf559055659a02652
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96243689"
---
# <a name="using-the-wcf-moniker-with-com-clients"></a>Verwenden des WCF-Monikers mit COM-Clients

In diesem Beispiel wird veranschaulicht, wie der Windows Communication Foundation (WCF)-Dienstmoniker verwendet wird, um Webdienste in COM-basierte Entwicklungsumgebungen zu integrieren, z. b. Microsoft Office Visual Basic for Applications (Office VBA) oder Visual Basic 6,0. Das Beispiel umfasst einen Windows Script Host-Client (.vbs), eine unterstützende Clientbibliothek (.dll) und eine Dienstbibliothek (.dll), die von Internetinformationsdienste (IIS) gehostet werden. Der Dienst ist ein Rechnerdienst und der COM-Client ruft mathematische Operationen (Addieren, Subtrahieren, Multiplizieren und Dividieren) auf dem Dienst auf. Die Clientaktivität ist in den Meldungsfeldfenstern sichtbar.  
  
> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Interop\COM`  
  
 Der Dienst implementiert einen `ICalculator`-Vertrag, dessen Definition im folgenden Codebeispiel veranschaulicht wird.  
  
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
  
 Im Beispiel werden die drei alternativen Ansätze für die Verwendung des Monikers veranschaulicht:  
  
- Typisierter Vertrag: Der Vertrag wird auf dem Clientcomputer als für COM sichtbarer Typ registriert.  
  
- WSDL-Vertrag: Der Vertrag wird in Form eines WSDL-Dokuments angegeben.  
  
- Metadatenaustausch-Vertrag: Der Vertrag wird zur Laufzeit von einem MEX-Endpunkt (Metadata Exchange) abgerufen.  
  
## <a name="typed-contract"></a>Typisierter Vertrag  

 Um den Moniker mit einem typisierten Vertrag zu verwenden, müssen auf geeignete Weise attributierte Typen für den Dienstvertrag mit COM registriert werden. Zuerst muss ein Client mit dem [Service Model Metadata Utility-Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md)generiert werden. Führen Sie den folgenden Befehl an einer Eingabeaufforderung im Clientverzeichnis aus, um den typisierten Proxy zu generieren.  
  
```console  
svcutil.exe /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples http://localhost/servicemodelsamples/service.svc /out:generatedClient.cs  
```  
  
 Diese Klasse muss in ein Projekt eingebunden werden, und das Projekt sollte so konfiguriert werden, dass es bei der Kompilierung eine für COM sichtbare, signierte Assembly generiert. Das folgende Attribut muss in der Datei AssemblyInfo.cs enthalten sein.  
  
```csharp
[assembly: ComVisible(true)]  
```  
  
 Registrieren Sie nach dem Erstellen des Projekts die für COM sichtbaren Typen mit `regasm`, wie im folgenden Beispiel veranschaulicht.  
  
```console  
regasm.exe /tlb:CalcProxy.tlb client.dll  
```  
  
 Die erstellte Assembly sollte dem globalen Assemblycache hinzugefügt werden. Obwohl nicht streng erforderlich, wird hierdurch der Prozess vereinfacht, bei dem die Laufzeit die Assembly lokalisiert. Mit dem folgenden Befehl wird die Assembly dem globalen Assemblycache hinzugefügt.  
  
```console  
gacutil.exe /i client.dll  
```  
  
> [!NOTE]
> Der Dienstmoniker erfordert nur die Typregistrierung und verwendet nicht den Proxy für die Kommunikation mit dem Dienst.  
  
 Die ComCalcClient.vbs-Clientanwendung nutzt die `GetObject`-Funktion, um einen Proxy für den Dienst zu erstellen, wobei die Dienstmonikersyntax für die Festlegung von Adresse, Bindung und Vertrag für den Dienst verwendet wird.  
  
```vbscript
Set typedServiceMoniker = GetObject(  
"service4:address=http://localhost/ServiceModelSamples/service.svc, binding=wsHttpBinding,
contractType={9213C6D2-5A6F-3D26-839B-3BA9B82228D3}")  
```  
  
 Die vom Moniker verwendeten Parameter legen Folgendes fest:  
  
- Die Adresse des Dienstendpunkts.  
  
- Die Bindung, die der Client verwenden sollte, um eine Verbindung mit diesem Endpunkt herzustellen. In diesem Fall wird die vom System definierte wsHttpBinding verwendet. Allerdings können auch benutzerdefinierte Bindungen in den Clientkonfigurationsdateien definiert werden. Für die Verwendung mit dem Windows Script Host wird die benutzerdefinierte Bindung in einer „Cscript.exe.config“-Datei im gleichen Verzeichnis wie „Cscript.exe“ definiert.  
  
- Der Typ des Vertrags, der vom Endpunkt unterstützt wird. Dies ist der Typ, der oben generiert und registriert wurde. Da Visual Basic Skript keine stark typisierte com-Umgebung bereitstellt, muss ein Bezeichner für den Vertrag angegeben werden. Diese GUID ist die `interfaceID` aus "CalcProxy.tlb", die durch COM-Tools wie OLE/COM-Objektkatalog (OleView.exe) eingesehen werden kann. Bei stark typisierten Umgebungen wie Office VBA oder Visual Basic 6,0 können Sie anstelle des Vertrags Parameters einen expliziten Verweis auf die Typbibliothek hinzufügen und dann den Typ des Proxy Objekts deklarieren. Auf diese Weise wird auch während der Clientanwendungsentwicklung IntelliSense-Unterstützung bereitgestellt.  
  
 Durch Erstellung der Proxyinstanz mit dem Dienstmoniker kann die Clientanwendung Methoden auf dem Proxy aufrufen. Dies führt dazu, dass die Dienstmonikerinfrastruktur die entsprechenden Dienstvorgänge aufruft.  
  
```vbscript  
' Call the service operations using the moniker object  
WScript.Echo "Typed service moniker: 100 + 15.99 = " & typedServiceMoniker.Add(100, 15.99)  
```  
  
 Wenn Sie das Beispiel ausführen, werden die Antworten für den Vorgang in einem Windows Script Host-Meldungsfeldfenster angezeigt. Dies veranschaulicht, dass ein com-Client COM-Aufrufe durchführt, die den typisierten Moniker für die Kommunikation mit einem WCF-Dienst Trotz der Verwendung von COM in der Clientanwendung besteht die Kommunikation mit dem Dienst ausschließlich aus Webdienstaufrufen.  
  
## <a name="wsdl-contract"></a>WSDL-Vertrag  

 Um den Moniker mit einem WSDL-Vertrag zu verwenden, ist keine Registrierung der Clientbibliothek erforderlich. Allerdings muss der WSDL-Vertrag für den Dienst über einen Out-of-Band-Mechanismus abgerufen werden, wie beispielsweise die Verwendung eines Browsers für den Zugriff auf den WSDL-Endpunkt des Diensts. Der Moniker kann dann bei Ausführungszeit auf diesen Vertrag zugreifen.  
  
 Die Clientanwendung ComCalcClient.vbs nutzt `FileSystemObject`, um auf die lokal gespeicherte WSDL-Datei zuzugreifen. Anschließend wird mithilfe der `GetObject`-Funktion ein Proxy für den Dienst erstellt.  
  
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
  
 Die vom Moniker verwendeten Parameter legen Folgendes fest:  
  
- Die Adresse des Dienstendpunkts.  
  
- Die Bindung, die der Client verwenden sollte, um eine Verbindung mit diesem Endpunkt herzustellen, und der Namespace, in dem diese Bindung definiert ist. In diesem Fall wird `wsHttpBinding_ICalculator` verwendet.  
  
- Die WSDL, die den Vertrag definiert. In diesem Fall ist dies die Zeichenfolge, die aus der Datei "serviceWsdl.xml" gelesen wurde.  
  
- Der Name und Namespace des Vertrags. Diese Identifikation ist erforderlich, da die WSDL möglicherweise mehr als einen Vertrag enthält.  
  
    > [!NOTE]
    > Standardmäßig generieren WCF-Dienste separate WSDL-Dateien für jeden Namespace, der von verwendet wird. Diese werden mit der Verwendung des WSDL-Importkonstrukts verknüpft. Da der Moniker eine einzige WSDL-Definition erwartet, muss der Dienst entweder einen einzigen Namespace verwenden (wie in diesem Beispiel gezeigt), oder die separaten Dateien müssen manuell zusammengeführt werden.  
  
 Durch Erstellung der Proxyinstanz mit dem Dienstmoniker kann die Clientanwendung Methoden auf dem Proxy aufrufen. Dies führt dazu, dass die Dienstmonikerinfrastruktur die entsprechenden Dienstvorgänge aufruft.  
  
```vbscript  
' Call the service operations using the moniker object  
WScript.Echo "WSDL service moniker: 145 - 76.54 = " & wsdlServiceMoniker.Subtract(145, 76.54)  
```  
  
 Wenn Sie das Beispiel ausführen, werden die Antworten für den Vorgang in einem Windows Script Host-Meldungsfeldfenster angezeigt. Dadurch wird veranschaulicht, wie ein com-Client COM-Aufrufe mithilfe des Monikers mit einem WSDL-Vertrag für die Kommunikation mit einem WCF-Dienst durchführt.  
  
## <a name="metadata-exchange-contract"></a>Metadatenaustausch-Vertrag  

 Um den Moniker mit einem MEX-Vertrag zu verwenden, ist wie bei einem WSDL-Vertrag keine Clientregistrierung erforderlich. Der Vertrag für den Dienst wird bei Ausführungszeit durch die interne Verwendung von Metadatenaustausch abgerufen.  
  
 Die Clientanwendung ComCalcClient.vbs verwendet wieder die `GetObject`-Funktion, um einen Proxy für den Dienst zu erstellen.  
  
```vbscript  
' Create a string for the service moniker specifying the address to retrieve the service metadata from  
mexMonikerString = "service4:mexAddress='http://localhost/servicemodelsamples/service.svc/mex'"  
mexMonikerString = mexMonikerString + ", address='http://localhost/ServiceModelSamples/service.svc'"  
mexMonikerString = mexMonikerString + ", binding=WSHttpBinding_ICalculator, bindingNamespace='http://Microsoft.ServiceModel.Samples'"  
mexMonikerString = mexMonikerString + ", contract=ICalculator, contractNamespace='http://Microsoft.ServiceModel.Samples'"  
  
' Create the service moniker object  
Set mexServiceMoniker = GetObject(mexMonikerString)  
```  
  
 Die vom Moniker verwendeten Parameter legen Folgendes fest:  
  
- Die Adresse des Metadatenaustausch-Endpunkts des Diensts.  
  
- Die Adresse des Dienstendpunkts.  
  
- Die Bindung, die der Client verwenden sollte, um eine Verbindung mit diesem Endpunkt herzustellen, und der Namespace, in dem diese Bindung definiert ist. In diesem Fall wird `wsHttpBinding_ICalculator` verwendet.  
  
- Der Name und Namespace des Vertrags. Diese Identifikation ist erforderlich, da die WSDL möglicherweise mehr als einen Vertrag enthält.  
  
 Durch Erstellung der Proxyinstanz mit dem Dienstmoniker kann die Clientanwendung Methoden auf dem Proxy aufrufen. Dies führt dazu, dass die Dienstmonikerinfrastruktur die entsprechenden Dienstvorgänge aufruft.  
  
```vbscript  
' Call the service operations using the moniker object  
WScript.Echo "MEX service moniker: 9 * 81.25 = " & mexServiceMoniker.Multiply(9, 81.25)  
```  
  
 Wenn Sie das Beispiel ausführen, werden die Antworten für den Vorgang in einem Windows Script Host-Meldungsfeldfenster angezeigt. Dadurch wird veranschaulicht, wie ein com-Client COM-Aufrufe mithilfe des Monikers mit einem MEX-Vertrag für die Kommunikation mit einem WCF-Dienst durchführt.  
  
#### <a name="to-set-up-and-build-the-sample"></a>So richten Sie das Beispiel ein und erstellen es  
  
1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.  
  
2. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.  
  
3. Öffnen Sie in einer Developer-Eingabeaufforderung für Visual Studio den Ordner "\client\bin" unter dem sprachspezifischen Ordner.  
  
    > [!NOTE]
    > Wenn Sie Windows Vista, Windows Server 2008, Windows 7 oder Windows Server 2008 R2 verwenden, stellen Sie sicher, dass Sie die Eingabeaufforderung mit Administratorrechten ausführen.  
  
4. Geben `tlbexp.exe client.dll /out:CalcProxy.tlb` Sie ein, um die dll in eine TLB-Datei zu exportieren. Eventuell wird eine "Typbibliothekexporter-Warnung" ausgegeben. Diese stellt jedoch kein Problem dar, da der generische Typ nicht benötigt wird.  
  
5. Geben `regasm.exe /tlb:CalcProxy.tlb client.dll` Sie ein, um die Typen bei com zu registrieren. Eventuell wird eine "Typbibliothekexporter-Warnung" ausgegeben. Diese stellt jedoch kein Problem dar, da der generische Typ nicht benötigt wird.  
  
6. Geben Sie ein `gacutil.exe /i client.dll` , um die Assembly dem globalen Assemblycache hinzuzufügen.  
  
#### <a name="to-run-the-sample-on-the-same-computer"></a>So führen Sie das Beispiel auf demselben Computer aus  
  
1. Überprüfen Sie, ob Sie über einen Browser auf den Dienst zugreifen können, indem Sie die folgende Adresse eingeben: `http://localhost/servicemodelsamples/service.svc` . Als Antwort sollte eine Bestätigungsseite angezeigt werden.  
  
2. Führen Sie die Datei "ComCalcClient.vbs" aus dem Ordner "\client" unter dem sprachspezifischen Ordner aus. Die Clientaktivität wird in den Meldungsfeldfenstern angezeigt.  
  
3. Wenn der Client und der Dienst nicht kommunizieren können, finden Sie unter [Tipps zur Problembehandlung für WCF-Beispiele](/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))Weitere Informationen.  
  
#### <a name="to-run-the-sample-across-computers"></a>So führen Sie das Beispiel computerübergreifend aus  
  
1. Erstellen Sie auf dem Dienstcomputer ein virtuelles Verzeichnis mit dem Namen ServiceModelSamples. Zum Erstellen des Festplattenverzeichnisses und des virtuellen Verzeichnisses kann das im Beispiel enthaltene Skript Setupvroot.bat verwendet werden.  
  
2. Kopieren Sie die Dienstprogrammdateien aus %SystemDrive%\Inetpub\wwwroot\servicemodelsamples in das virtuelle Verzeichnis ServiceModelSamples auf dem Dienstcomputer. Stellen Sie sicher, dass Sie die Dateien in das Verzeichnis \bin einfügen.  
  
3. Kopieren Sie die Skriptdatei aus dem Ordner \client (unterhalb des sprachspezifischen Ordners) auf den Clientcomputer.  
  
4. Ändern Sie in der Skriptdatei den Adresswert der Endpunktdefinition, sodass dieser mit der neuen Adresse Ihres Diensts übereinstimmt. Ersetzen Sie alle Verweise auf localhost in der Adresse durch einen vollqualifizierten Domänennamen.  
  
5. Kopieren Sie die WSDL-Datei auf den Clientcomputer. Ersetzen Sie in der WSDL-Datei serviceWsdl.xml alle Verweise auf localhost in der Adresse durch einen vollqualifizierten Domänennamen.  
  
6. Kopieren Sie die Bibliothek Client.dll aus dem Ordner \client\bin (unterhalb des sprachspezifischen Ordners) in ein Verzeichnis auf dem Clientcomputer.  
  
7. Navigieren Sie an einer Eingabeaufforderung zu diesem Zielverzeichnis auf dem Clientcomputer. Wenn Sie Windows Vista oder Windows Server 2008 verwenden, stellen Sie sicher, dass Sie die Eingabeaufforderung als Administrator ausführen.  
  
8. Geben `tlbexp.exe client.dll /out:CalcProxy.tlb` Sie ein, um die dll in eine TLB-Datei zu exportieren. Eventuell wird eine "Typbibliothekexporter-Warnung" ausgegeben. Diese stellt jedoch kein Problem dar, da der generische Typ nicht benötigt wird.  
  
9. Geben `regasm.exe /tlb:CalcProxy.tlb client.dll` Sie ein, um die Typen bei com zu registrieren. Stellen Sie sicher, dass der Pfad auf den Ordner festgelegt wurde, der enthält, `regasm.exe` bevor Sie den Befehl ausführen.  
  
10. Geben Sie ein `gacutil.exe /i client.dll` , um die Assembly dem globalen Assemblycache hinzuzufügen. Stellen Sie sicher, dass der Pfad auf den Ordner festgelegt wurde, der enthält, `gacutil.exe` bevor Sie den Befehl ausführen.  
  
11. Testen Sie, ob Sie mit einem Browser vom Clientcomputer auf den Dienst zugreifen können.  
  
12. Starten Sie auf dem Clientcomputer ComCalcClient.vbs.  
  
#### <a name="to-clean-up-after-the-sample"></a>So stellen Sie den Zustand vor Ausführung des Beispiels wieder her  
  
- Entfernen Sie aus Sicherheitsgründen die Definition des virtuellen Verzeichnisses und die in den Setupschritten gewährten Berechtigungen, wenn Sie die Beispiele abgeschlossen haben.
