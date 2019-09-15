---
title: 'Vorgehensweise: Verwenden eines Dienstmonikers mit Metadatenaustausch-Verträgen'
ms.date: 03/30/2017
ms.assetid: c41a07e5-cb9d-45d6-9ea4-34511e227faf
ms.openlocfilehash: e114bc2c046ba7145a91121ce23c82912680a048
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2019
ms.locfileid: "70968963"
---
# <a name="how-to-use-a-service-moniker-with-metadata-exchange-contracts"></a>Vorgehensweise: Verwenden eines Dienstmonikers mit Metadatenaustausch-Verträgen
Nachdem Sie einige neue WCF-Dienste entwickelt haben, können Sie entscheiden, ob Sie in der Lage sein möchten, diese Dienste aus einem Skript oder einer Visual Basic 6,0-Anwendung aufzurufen. Eine Methode wäre das Generieren einer WCF-Clientassembly, das Registrieren der Assembly bei com, das Installieren der Assembly im GAC und das anschließende verweisen auf die COM-Typen aus dem Visual Basic-Code. Wenn Sie die Anwendung verteilen, müssen Sie die WCF-Clientassembly ebenfalls verteilen. Der Benutzer muss dann die WCF-Clientassembly bei COM registrieren und im GAC platzieren. Mit WCF COM Interop können Sie auch dieselben Dienst Aufrufe ausführen, ohne sich auf eine WCF-Clientassembly verlassen zu müssen. Der WCF-Moniker ermöglicht das Aufrufen eines beliebigen WCF-Dienstanbieter von jeder com-kompatiblen Sprache (Visual Basic, VBScript, Visual Basic for Applications (VBA) usw.) durch Angabe eines MEX-Endpunkt-URIs (Metadata Exchange), den der Dienstmoniker zum Extrahieren des Typs verwendet. Informationen zum Dienst. In diesem Thema wird beschrieben, wie das Beispiel für die ersten Schritte mit einem WCF-Moniker aufgerufen wird, der einen MEX-Endpunkt angibt.  
  
> [!NOTE]
> Die von der WCF-Clientassembly definierten Typen werden nie tatsächlich instanziiert. Die Assembly wird nur für Metadaten verwendet.  
  
### <a name="using-the-service-moniker-with-a-mex-address"></a>Verwenden des Dienstmonikers mit einer MEX-Adresse  
  
1. Erstellen Sie das Beispiel "Getting Started", und verwenden Sie Internet Explorer, http://localhost/ServiceModelSamples/Service.svc) um die URL zu suchen (um sicherzustellen, dass der Dienst funktioniert.  
  
2. Erstellen Sie ein Visual Basic-Skript oder eine Visual Basic-Anwendung, die den folgenden Code enthält:  
  
    ```vb
    monString = "service:mexaddress=http://localhost/ServiceModelSamples/Service.svc/MEX"  
    monString = monString + ", address=http://localhost/ServiceModelSamples/Service.svc"  
    monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", binding=WSHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
  
    Set calc = GetObject(monString)  
    MsgBox calc.Add(3, 4)  
    ```  
  
3. Führen Sie die Visual Basic-Anwendung oder das Skript aus.  
  
    > [!NOTE]
    > Der Dienst, den Sie aufrufen, muss einen MEX-Endpunkt für den Moniker verfügbar machen, damit dieser die Metadaten aus dem Dienst lesen kann. Weitere Informationen finden Sie unter [Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurations](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)Datei.  
  
    > [!NOTE]
    > Ist der Moniker nicht ordnungsgemäß formatiert oder der Dienst nicht verfügbar, wird nach dem `GetObject`-Aufruf ein Syntaxfehler zurückgegeben.  Vergewissern Sie sich bei Auftreten dieses Fehlers, dass der verwendete Moniker korrekt und der Dienst verfügbar ist.  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Verwenden des Windows Communication Foundation-Dienstmonikers ohne Registrierung](../../../../docs/framework/wcf/feature-details/use-the-wcf-service-moniker-without-registration.md)
- [Vorgehensweise: Verwenden eines Dienstmonikers mit WSDL-Verträgen](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-wsdl-contracts.md)
