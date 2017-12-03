---
title: "Gewusst wie: Verwenden eines Dienstmonikers mit WSDL-Verträgen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a88d9650-bb50-4f48-8c85-12f5ce98a83a
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c44b09f512a7625360ca5036316d03a4602c5186
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-use-a-service-moniker-with-wsdl-contracts"></a>Gewusst wie: Verwenden eines Dienstmonikers mit WSDL-Verträgen
Es gibt Situationen, in denen Sie sich möglicherweise einen vollständig unabhängigen COM Interop-Client wünschen. Der Dienst, den Sie aufrufen möchten, stellt vielleicht keinen MEX-Endpunkt bereit, oder die WCF-Client-DLL ist nicht für COM-Interop registriert. In diesen Fällen können Sie eine WSDL-Datei erstellen, die den Dienst beschreibt, und die Datei an den WCF-Dienstmoniker übergeben. In diesem Thema wird beschrieben, wie das Beispiel für Erste Schritte mit WCF zur Verwendung eines WSDL-Monikers in WCF aufgerufen wird.  
  
### <a name="using-the-wsdl-service-moniker"></a>Verwenden des WSDL-Dienstmonikers  
  
1.  Öffnen und erstellen Sie die GettingStarted-Beispiellösung.  
  
2.  Öffnen Sie Internet Explorer, wechseln Sie zu http://localhost/ServiceModelSamples/Service.svc, und stellen Sie sicher, dass der Dienst funktioniert.  
  
3.  Fügen Sie in der Datei Service.cs der CalculatorService-Klasse das folgende Attribut hinzu:  
  
     [!code-csharp[S_WSDL_Client#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wsdl_client/cs/service.cs#0)]  
  
4.  Fügen Sie der Datei „App.config“ des Diensts einen Bindungsnamespace hinzu:  
  
  
  
5.  Erstellen Sie eine WSDL-Datei, die von der Anwendung gelesen wird. Da die Namespaces in den Schritten 3 und 4 hinzugefügt werden, können Sie die gesamte WSDL-Beschreibung des Dienstes in Internet Explorer abfragen, indem Sie zu http://localhost/ServiceModelSamples/Service.svc?wsdl wechseln. Sie können die Datei dann in Internet Explorer als serviceWSDL.xml speichern. Wenn Sie die Namespaces nicht in den Schritten 3 und 4 angeben, ist das von der Abfrage der obigen URL zurückgegebene WSDL-Dokument nicht vollständig. Das zurückgegebene WSDL-Dokument enthält verschiedene Importanweisungen, die andere WSDL-Dokumente importieren. Sie müssen dann die einzelnen Importanweisungen durchgehen und das vollständige WSDL-Dokument erstellen, wobei Sie das vom Dienst zurückgegebene WSDL mit dem importierten WSDL kombinieren.  
  
6.  Öffnen Sie Visual Basic 6.0, und erstellen Sie eine neue Standard-EXE-Datei. Fügen Sie dem Formular eine Schaltfläche hinzu, und doppelklicken Sie darauf, um dem Click-Handler den folgenden Code hinzuzufügen.  
  
    ```  
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
    >  Ist der Moniker nicht ordnungsgemäß formatiert oder der Dienst nicht verfügbar, wird nach dem `GetObject`-Aufruf ein Syntaxfehler zurückgegeben.  Vergewissern Sie sich bei Auftreten dieses Fehlers, dass der verwendete Moniker korrekt und der Dienst verfügbar ist.  
  
7.  Führen Sie die Visual Basic-Anwendung aus. Ein Meldungsfeld wird mit den Ergebnissen des Aufrufs Subtract(145, 76.54) angezeigt.  
  
## <a name="see-also"></a>Siehe auch  
 [Erste Schritte](../../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [Integrieren von COM-Anwendungen (Übersicht)](../../../../docs/framework/wcf/feature-details/integrating-with-com-applications-overview.md)
