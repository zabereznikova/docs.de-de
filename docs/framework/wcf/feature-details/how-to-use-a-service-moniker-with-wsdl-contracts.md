---
title: 'Vorgehensweise: Verwenden eines Dienstmonikers mit WSDL-Verträgen'
ms.date: 03/30/2017
ms.assetid: a88d9650-bb50-4f48-8c85-12f5ce98a83a
ms.openlocfilehash: 70d7e9ff45616f832597ebc48db00198967935c6
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601139"
---
# <a name="how-to-use-a-service-moniker-with-wsdl-contracts"></a>Vorgehensweise: Verwenden eines Dienstmonikers mit WSDL-Verträgen
Es gibt Situationen, in denen Sie sich möglicherweise einen vollständig unabhängigen COM Interop-Client wünschen. Der Dienst, den Sie aufrufen möchten, stellt vielleicht keinen MEX-Endpunkt bereit, oder die WCF-Client-DLL ist nicht für COM-Interop registriert. In diesen Fällen können Sie eine WSDL-Datei erstellen, die den Dienst beschreibt, und die Datei an den WCF-Dienstmoniker übergeben. In diesem Thema wird beschrieben, wie das Beispiel für Erste Schritte mit WCF zur Verwendung eines WSDL-Monikers in WCF aufgerufen wird.  
  
### <a name="using-the-wsdl-service-moniker"></a>Verwenden des WSDL-Dienstmonikers  
  
1. Öffnen und erstellen Sie die GettingStarted-Beispiellösung.  
  
2. Öffnen Sie Internet Explorer, und navigieren Sie zu, `http://localhost/ServiceModelSamples/Service.svc` um sicherzustellen, dass der Dienst funktioniert.  
  
3. Fügen Sie in der Datei Service.cs der CalculatorService-Klasse das folgende Attribut hinzu:  
  
     [!code-csharp[S_WSDL_Client#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wsdl_client/cs/service.cs#0)]  
  
4. Fügen Sie dem Dienst App.config einen Bindungsnamespace hinzu:  

5. Erstellen Sie eine WSDL-Datei, die von der Anwendung gelesen wird. Da die-Namespaces in den Schritten 3 und 4 hinzugefügt wurden, können Sie Internet Explorer verwenden, um die gesamte WSDL-Beschreibung des Dienstanbieter abzufragen, indem Sie zu navigieren `http://localhost/ServiceModelSamples/Service.svc?wsdl` . Sie können die Datei dann in Internet Explorer als serviceWSDL.xml speichern. Wenn Sie die Namespaces nicht in den Schritten 3 und 4 angeben, ist das von der Abfrage der obigen URL zurückgegebene WSDL-Dokument nicht vollständig. Das zurückgegebene WSDL-Dokument enthält verschiedene Importanweisungen, die andere WSDL-Dokumente importieren. Sie müssen dann die einzelnen Importanweisungen durchgehen und das vollständige WSDL-Dokument erstellen, wobei Sie das vom Dienst zurückgegebene WSDL mit dem importierten WSDL kombinieren.  
  
6. Öffnen Sie Visual Basic 6.0, und erstellen Sie eine neue Standard-EXE-Datei. Fügen Sie dem Formular eine Schaltfläche hinzu, und doppelklicken Sie darauf, um dem Click-Handler den folgenden Code hinzuzufügen.  
  
    ```vb
    ' Open the WSDL contract file and read it all into the wsdlContract string.  
    Const ForReading = 1  
    Set objFSO = CreateObject("Scripting.FileSystemObject")  
    Set objFile = objFSO.OpenTextFile("c:\serviceWsdl.xml", ForReading)  
    wsdlContract = objFile.ReadAll  
    objFile.Close  
  
    ' Create a string for the service moniker including the content of the WSDL contract file.  
    wsdlMonikerString = "service4:address='http://localhost/ServiceModelSamples/service.svc'"  
    wsdlMonikerString = wsdlMonikerString + ", wsdl='" & wsdlContract & "'"  
    wsdlMonikerString = wsdlMonikerString + ", binding=WSHttpBinding_ICalculator, bindingNamespace='http://Microsoft.ServiceModel.Samples'"  
    wsdlMonikerString = wsdlMonikerString + ", contract=ICalculator, contractNamespace='http://Microsoft.ServiceModel.Samples'"  
  
    ' Create the service moniker object.  
    Set wsdlServiceMoniker = GetObject(wsdlMonikerString)  
  
    ' Call the service operations using the moniker object.  
    MsgBox "WSDL service moniker: 145 - 76.54 = " & wsdlServiceMoniker.Subtract(145, 76.54)  
    ```  
  
    > [!NOTE]
    > Ist der Moniker nicht ordnungsgemäß formatiert oder der Dienst nicht verfügbar, wird nach dem `GetObject`-Aufruf ein Syntaxfehler zurückgegeben.  Vergewissern Sie sich bei Auftreten dieses Fehlers, dass der verwendete Moniker korrekt und der Dienst verfügbar ist.  
  
7. Führen Sie die Visual Basic-Anwendung aus. Ein Meldungsfeld wird mit den Ergebnissen des Aufrufs Subtract(145, 76.54) angezeigt.  
  
## <a name="see-also"></a>Weitere Informationen

- [Erste Schritte](../samples/getting-started-sample.md)
- [Übersicht über die Integration von COM-Anwendungen](integrating-with-com-applications-overview.md)
