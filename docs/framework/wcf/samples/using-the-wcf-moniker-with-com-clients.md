---
title: Verwenden des WCF-Monikers mit COM-Clients
ms.date: 03/30/2017
ms.assetid: e2799bfe-88bd-49d7-9d6d-ac16a9b16b04
ms.openlocfilehash: 79040cd267d354d32b3e957dc70fcc65b09b0fc8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="using-the-wcf-moniker-with-com-clients"></a>Verwenden des WCF-Monikers mit COM-Clients
Dieses Beispiel veranschaulicht, wie mithilfe den Windows Communication Foundation (WCF)-Dienstmoniker Webdienste in COM-basierten entwicklungsumgebungen wie Microsoft Office Visual Basic for Applications (Office VBA) oder Visual Basic 6.0 integriert werden. Das Beispiel umfasst einen Windows Script Host-Client (.vbs), eine unterstützende Clientbibliothek (.dll) und eine Dienstbibliothek (.dll), die von Internetinformationsdienste (IIS) gehostet werden. Der Dienst ist ein Rechnerdienst und der COM-Client ruft mathematische Operationen (Addieren, Subtrahieren, Multiplizieren und Dividieren) auf dem Dienst auf. Die Clientaktivität ist in den Meldungsfeldfenstern sichtbar.  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Interop\COM`  
  
 Der Dienst implementiert einen `ICalculator`-Vertrag, dessen Definition im folgenden Codebeispiel veranschaulicht wird.  
  
```  
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
  
-   Typisierter Vertrag: Der Vertrag wird auf dem Clientcomputer als für COM sichtbarer Typ registriert.  
  
-   WSDL-Vertrag: Der Vertrag wird in Form eines WSDL-Dokuments angegeben.  
  
-   Metadatenaustausch-Vertrag: Der Vertrag wird zur Laufzeit von einem MEX-Endpunkt (Metadata Exchange) abgerufen.  
  
## <a name="typed-contract"></a>Typisierter Vertrag  
 Um den Moniker mit einem typisierten Vertrag zu verwenden, müssen auf geeignete Weise attributierte Typen für den Dienstvertrag mit COM registriert werden. Zunächst muss ein Client generiert werden, mithilfe der [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). Führen Sie den folgenden Befehl an einer Eingabeaufforderung im Clientverzeichnis aus, um den typisierten Proxy zu generieren.  
  
```  
svcutil.exe /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples http://localhost/servicemodelsamples/service.svc /out:generatedClient.cs  
```  
  
 Diese Klasse muss in ein Projekt eingebunden werden, und das Projekt sollte so konfiguriert werden, dass es bei der Kompilierung eine für COM sichtbare, signierte Assembly generiert. Das folgende Attribut muss in der Datei AssemblyInfo.cs enthalten sein.  
  
```  
[assembly: ComVisible(true)]  
```  
  
 Registrieren Sie nach dem Erstellen des Projekts die für COM sichtbaren Typen mit `regasm`, wie im folgenden Beispiel veranschaulicht.  
  
```  
regasm.exe /tlb:CalcProxy.tlb client.dll  
```  
  
 Die erstellte Assembly sollte dem globalen Assemblycache hinzugefügt werden. Obwohl nicht streng erforderlich, wird hierdurch der Prozess vereinfacht, bei dem die Laufzeit die Assembly lokalisiert. Mit dem folgenden Befehl wird die Assembly dem globalen Assemblycache hinzugefügt.  
  
```  
gacutil.exe /i client.dll  
```  
  
> [!NOTE]
>  Der Dienstmoniker erfordert nur die Typregistrierung und verwendet nicht den Proxy für die Kommunikation mit dem Dienst.  
  
 Die ComCalcClient.vbs-Clientanwendung nutzt die `GetObject`-Funktion, um einen Proxy für den Dienst zu erstellen, wobei die Dienstmonikersyntax für die Festlegung von Adresse, Bindung und Vertrag für den Dienst verwendet wird.  
  
```  
Set typedServiceMoniker = GetObject(  
"service4:address=http://localhost/ServiceModelSamples/service.svc, binding=wsHttpBinding,   
contractType={9213C6D2-5A6F-3D26-839B-3BA9B82228D3}")  
```  
  
 Die vom Moniker verwendeten Parameter legen Folgendes fest:  
  
-   Die Adresse des Dienstendpunkts.  
  
-   Die Bindung, die der Client verwenden sollte, um eine Verbindung mit diesem Endpunkt herzustellen. In diesem Fall wird die vom System definierte wsHttpBinding verwendet. Allerdings können auch benutzerdefinierte Bindungen in den Clientkonfigurationsdateien definiert werden. Für die Verwendung mit dem Windows Script Host wird die benutzerdefinierte Bindung in einer Cscript.exe.config-Datei im gleichen Verzeichnis wie "Cscript.exe" definiert.  
  
-   Der Typ des Vertrags, der vom Endpunkt unterstützt wird. Dies ist der Typ, der oben generiert und registriert wurde. Da ein Visual Basic-Skript keine stark typisierte COM-Umgebung bereitstellt, muss eine ID für den Vertrag festgelegt werden. Diese GUID ist die `interfaceID` aus "CalcProxy.tlb", die durch COM-Tools wie OLE/COM-Objektkatalog (OleView.exe) eingesehen werden kann. Für stark typisierte Umgebungen wie Office VBA oder Visual Basic 6.0 kann anstelle des Vertragsparameters ein expliziter Verweis auf die Typbibliothek hinzugefügt werden und daraufhin eine Deklaration des Typs des Proxyobjekts erfolgen. Auf diese Weise wird auch während der Clientanwendungsentwicklung IntelliSense-Unterstützung bereitgestellt.  
  
 Durch Erstellung der Proxyinstanz mit dem Dienstmoniker kann die Clientanwendung Methoden auf dem Proxy aufrufen. Dies führt dazu, dass die Dienstmonikerinfrastruktur die entsprechenden Dienstvorgänge aufruft.  
  
```  
' Call the service operations using the moniker object  
WScript.Echo "Typed service moniker: 100 + 15.99 = " & typedServiceMoniker.Add(100, 15.99)  
```  
  
 Wenn Sie das Beispiel ausführen, werden die Antworten für den Vorgang in einem Windows Script Host-Meldungsfeldfenster angezeigt. Auf diese Weise wird gezeigt, wie ein COM-Client COM-Aufrufe mithilfe des typisierten Monikers vornimmt, um mit einem [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst zu kommunizieren. Trotz der Verwendung von COM in der Clientanwendung besteht die Kommunikation mit dem Dienst ausschließlich aus Webdienstaufrufen.  
  
## <a name="wsdl-contract"></a>WSDL-Vertrag  
 Um den Moniker mit einem WSDL-Vertrag zu verwenden, ist keine Registrierung der Clientbibliothek erforderlich. Allerdings muss der WSDL-Vertrag für den Dienst über einen Out-of-Band-Mechanismus abgerufen werden, wie beispielsweise die Verwendung eines Browsers für den Zugriff auf den WSDL-Endpunkt des Diensts. Der Moniker kann dann bei Ausführungszeit auf diesen Vertrag zugreifen.  
  
 Die Clientanwendung ComCalcClient.vbs nutzt `FileSystemObject`, um auf die lokal gespeicherte WSDL-Datei zuzugreifen. Anschließend wird mithilfe der `GetObject`-Funktion ein Proxy für den Dienst erstellt.  
  
```  
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
  
-   Die Adresse des Dienstendpunkts.  
  
-   Die Bindung, die der Client verwenden sollte, um eine Verbindung mit diesem Endpunkt herzustellen, und der Namespace, in dem diese Bindung definiert ist. In diesem Fall wird `wsHttpBinding_ICalculator` verwendet.  
  
-   Die WSDL, die den Vertrag definiert. In diesem Fall ist dies die Zeichenfolge, die aus der Datei "serviceWsdl.xml" gelesen wurde.  
  
-   Der Name und Namespace des Vertrags. Diese Identifikation ist erforderlich, da die WSDL möglicherweise mehr als einen Vertrag enthält.  
  
    > [!NOTE]
    >  Standardmäßig generieren [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienste separate WSDL-Dateien für jeden verwendeten Namespace. Diese werden mit der Verwendung des WSDL-Importkonstrukts verknüpft. Da der Moniker eine einzige WSDL-Definition erwartet, muss der Dienst entweder einen einzigen Namespace verwenden (wie in diesem Beispiel gezeigt) oder die separaten Dateien müssen manuell zusammengeführt werden.  
  
 Durch Erstellung der Proxyinstanz mit dem Dienstmoniker kann die Clientanwendung Methoden auf dem Proxy aufrufen. Dies führt dazu, dass die Dienstmonikerinfrastruktur die entsprechenden Dienstvorgänge aufruft.  
  
```  
' Call the service operations using the moniker object  
WScript.Echo "WSDL service moniker: 145 - 76.54 = " & wsdlServiceMoniker.Subtract(145, 76.54)  
```  
  
 Wenn Sie das Beispiel ausführen, werden die Antworten für den Vorgang in einem Windows Script Host-Meldungsfeldfenster angezeigt. Auf diese Weise wird gezeigt, wie ein COM-Client COM-Aufrufe mithilfe des Monikers mit einem WSDL-Vertrag vornimmt, um mit einem [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst zu kommunizieren.  
  
## <a name="metadata-exchange-contract"></a>Metadatenaustausch-Vertrag  
 Um den Moniker mit einem MEX-Vertrag zu verwenden, ist wie bei einem WSDL-Vertrag keine Clientregistrierung erforderlich. Der Vertrag für den Dienst wird bei Ausführungszeit durch die interne Verwendung von Metadatenaustausch abgerufen.  
  
 Die Clientanwendung ComCalcClient.vbs verwendet wieder die `GetObject`-Funktion, um einen Proxy für den Dienst zu erstellen.  
  
```  
' Create a string for the service moniker specifying the address to retrieve the service metadata from  
mexMonikerString = "service4:mexAddress='http://localhost/servicemodelsamples/service.svc/mex'"  
mexMonikerString = mexMonikerString + ", address='http://localhost/ServiceModelSamples/service.svc'"  
mexMonikerString = mexMonikerString + ", binding=WSHttpBinding_ICalculator, bindingNamespace='http://Microsoft.ServiceModel.Samples'"  
mexMonikerString = mexMonikerString + ", contract=ICalculator, contractNamespace='http://Microsoft.ServiceModel.Samples'"  
  
' Create the service moniker object  
Set mexServiceMoniker = GetObject(mexMonikerString)  
```  
  
 Die vom Moniker verwendeten Parameter legen Folgendes fest:  
  
-   Die Adresse des Metadatenaustausch-Endpunkts des Diensts.  
  
-   Die Adresse des Dienstendpunkts.  
  
-   Die Bindung, die der Client verwenden sollte, um eine Verbindung mit diesem Endpunkt herzustellen, und der Namespace, in dem diese Bindung definiert ist. In diesem Fall wird `wsHttpBinding_ICalculator` verwendet.  
  
-   Der Name und Namespace des Vertrags. Diese Identifikation ist erforderlich, da die WSDL möglicherweise mehr als einen Vertrag enthält.  
  
 Durch Erstellung der Proxyinstanz mit dem Dienstmoniker kann die Clientanwendung Methoden auf dem Proxy aufrufen. Dies führt dazu, dass die Dienstmonikerinfrastruktur die entsprechenden Dienstvorgänge aufruft.  
  
```  
' Call the service operations using the moniker object  
WScript.Echo "MEX service moniker: 9 * 81.25 = " & mexServiceMoniker.Multiply(9, 81.25)  
```  
  
 Wenn Sie das Beispiel ausführen, werden die Antworten für den Vorgang in einem Windows Script Host-Meldungsfeldfenster angezeigt. Das Beispiel veranschaulicht, wie ein COM-Client unter Verwendung des Monikers mit einem MEX-Vertrag COM-Aufrufe vornimmt, um mit einem [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst zu kommunizieren.  
  
#### <a name="to-set-up-and-build-the-sample"></a>So richten Sie das Beispiel ein und erstellen es  
  
1.  Stellen Sie sicher, dass Sie ausgeführt haben die [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
3.  Öffnen Sie den Ordner \client\bin unter dem sprachspezifischen Ordner aus einer Visual Studio-Eingabeaufforderung.  
  
    > [!NOTE]
    >  Wenn Sie [!INCLUDE[wv](../../../../includes/wv-md.md)], [!INCLUDE[lserver](../../../../includes/lserver-md.md)], Windows 7 oder Windows Server 2008 R2 verwenden, müssen Sie den Befehl mit Administratorberechtigungen ausführen.  
  
4.  Geben Sie im `tlbexp.exe client.dll /out:CalcProxy.tlb` auf die Dll in eine Tlb-Datei exportieren. Eventuell wird eine "Typbibliothekexporter-Warnung" ausgegeben. Diese stellt jedoch kein Problem dar, da der generische Typ nicht benötigt wird.  
  
5.  Geben Sie im `regasm.exe /tlb:CalcProxy.tlb client.dll` auf die Typen bei COM zu registrieren. Eventuell wird eine "Typbibliothekexporter-Warnung" ausgegeben. Diese stellt jedoch kein Problem dar, da der generische Typ nicht benötigt wird.  
  
6.  Geben Sie in `gacutil.exe /i client.dll` um die Assembly im globalen Assemblycache hinzuzufügen.  
  
#### <a name="to-run-the-sample-on-the-same-computer"></a>So führen Sie das Beispiel auf demselben Computer aus  
  
1.  Test, den Sie den Dienst mithilfe eines Browsers durch Eingabe in der folgenden Adresse zugreifen können: `http://localhost/servicemodelsamples/service.svc`. Als Antwort sollte eine Bestätigungsseite angezeigt werden.  
  
2.  Führen Sie die Datei "ComCalcClient.vbs" aus dem Ordner "\client" unter dem sprachspezifischen Ordner aus. Die Clientaktivität wird in den Meldungsfeldfenstern angezeigt.  
  
3.  Wenn Client und Dienst nicht miteinander kommunizieren können, finden Sie unter [Tipps zur Problembehandlung](http://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b).  
  
#### <a name="to-run-the-sample-across-computers"></a>So führen Sie das Beispiel computerübergreifend aus  
  
1.  Erstellen Sie auf dem Dienstcomputer ein virtuelles Verzeichnis mit dem Namen ServiceModelSamples. Zum Erstellen des Festplattenverzeichnisses und des virtuellen Verzeichnisses kann das im Beispiel enthaltene Skript Setupvroot.bat verwendet werden.  
  
2.  Kopieren Sie die Dienstprogrammdateien aus %SystemDrive%\Inetpub\wwwroot\servicemodelsamples in das virtuelle Verzeichnis ServiceModelSamples auf dem Dienstcomputer. Stellen Sie sicher, dass Sie die Dateien in das Verzeichnis \bin einfügen.  
  
3.  Kopieren Sie die Skriptdatei aus dem Ordner \client (unterhalb des sprachspezifischen Ordners) auf den Clientcomputer.  
  
4.  Ändern Sie in der Skriptdatei den Adresswert der Endpunktdefinition, sodass dieser mit der neuen Adresse Ihres Diensts übereinstimmt. Ersetzen Sie alle Verweise auf localhost in der Adresse durch einen vollqualifizierten Domänennamen.  
  
5.  Kopieren Sie die WSDL-Datei auf den Clientcomputer. Ersetzen Sie in der WSDL-Datei serviceWsdl.xml alle Verweise auf localhost in der Adresse durch einen vollqualifizierten Domänennamen.  
  
6.  Kopieren Sie die Bibliothek Client.dll aus dem Ordner \client\bin (unterhalb des sprachspezifischen Ordners) in ein Verzeichnis auf dem Clientcomputer.  
  
7.  Navigieren Sie an einer Eingabeaufforderung zu diesem Zielverzeichnis auf dem Clientcomputer. Wenn Sie [!INCLUDE[wv](../../../../includes/wv-md.md)] oder [!INCLUDE[lserver](../../../../includes/lserver-md.md)] verwenden, stellen Sie sicher, dass Sie die Eingabeaufforderung als Administrator ausführen.  
  
8.  Geben Sie im `tlbexp.exe client.dll /out:CalcProxy.tlb` auf die Dll in eine Tlb-Datei exportieren. Eventuell wird eine "Typbibliothekexporter-Warnung" ausgegeben. Diese stellt jedoch kein Problem dar, da der generische Typ nicht benötigt wird.  
  
9. Geben Sie im `regasm.exe /tlb:CalcProxy.tlb client.dll` auf die Typen bei COM zu registrieren. Stellen Sie sicher, dass der Pfad zu dem Ordner mit vorsieht `regasm.exe` vor dem Ausführen des Befehls.  
  
10. Geben Sie in `gacutil.exe /i client.dll` um die Assembly im globalen Assemblycache hinzuzufügen. Stellen Sie sicher, dass der Pfad zu dem Ordner mit vorsieht `gacutil.exe` vor dem Ausführen des Befehls.  
  
11. Testen Sie, ob Sie mit einem Browser vom Clientcomputer auf den Dienst zugreifen können.  
  
12. Starten Sie auf dem Clientcomputer ComCalcClient.vbs.  
  
#### <a name="to-clean-up-after-the-sample"></a>So stellen Sie den Zustand vor Ausführung des Beispiels wieder her  
  
-   Entfernen Sie aus Sicherheitsgründen die Definition des virtuellen Verzeichnisses und die in den Setupschritten gewährten Berechtigungen, wenn Sie die Beispiele abgeschlossen haben.  
  
## <a name="see-also"></a>Siehe auch
