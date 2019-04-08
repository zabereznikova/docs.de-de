---
title: 'Vorgehensweise: Verwenden eines Dienstmonikers mit Metadatenaustausch-Verträgen'
ms.date: 03/30/2017
ms.assetid: c41a07e5-cb9d-45d6-9ea4-34511e227faf
ms.openlocfilehash: e1d6c6516294d7df7f8c89a3aaddcf2ac3ba0e2a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59082697"
---
# <a name="how-to-use-a-service-moniker-with-metadata-exchange-contracts"></a>Vorgehensweise: Verwenden eines Dienstmonikers mit Metadatenaustausch-Verträgen
Nach dem Entwickeln von einigen neuen WCF-Diensten, können Sie entscheiden, dass diese Dienste aus einem Skript oder eine Visual Basic 6.0-Anwendung aufrufen kann verwendet werden soll. Eine Methode wäre, eine WCF-Client-Assembly generieren, die Assembly bei COM registriert werden, die Assembly im GAC zu installieren und dann auf die COM-Typen von Visual Basic-Code verweisen. Wenn Sie die Anwendung verteilen, müssen Sie auch die WCF-Client-Assembly zu verteilen. Der Benutzer muss dann die WCF-Clientassembly bei COM registrieren und im GAC platzieren. WCF-COM-Interop können Sie auf die gleichen Dienstaufrufe ohne Rückgriff auf eine WCF-Clientassembly. Der WCF-Monikers können Sie jeden WCF-Dienst alle COM-kompatiblen Sprache (Visual Basic, VBScript, Visual Basic für Applikationen (VBA) usw.) rufen Sie dazu einen Metadatenaustausch (Mex)-Endpunkt URI, der der Dienstmoniker verwendet, um Typ zu extrahieren Informationen zum Dienst. Dieses Thema beschreibt, wie das erste-Schritte-WCF-Beispiel verwenden einen WCF-Monikers, der angibt, einen Mex-Endpunkt aufgerufen wird.  
  
> [!NOTE]
>  Durch die WCF-Clientassembly definierten Typen werden nie tatsächlich instanziiert. Die Assembly wird nur für Metadaten verwendet.  
  
### <a name="using-the-service-moniker-with-a-mex-address"></a>Verwenden des Dienstmonikers mit einer MEX-Adresse  
  
1.  Die Getting Started-Beispiel zu erstellen und verwenden Sie Internet Explorer, um die URL zu suchen (http://localhost/ServiceModelSamples/Service.svc) um sicherzustellen, dass der Dienst funktioniert.  
  
2.  Erstellen Sie ein Visual Basic-Skript oder eine Visual Basic-Anwendung, die den folgenden Code enthält:  
  
    ```  
    monString = "service:mexaddress=http://localhost/ServiceModelSamples/Service.svc/MEX"  
    monString = monString + ", address=http://localhost/ServiceModelSamples/Service.svc"  
    monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", binding=WSHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
  
    Set calc = GetObject(monString)  
    MsgBox calc.Add(3, 4)  
    ```  
  
3.  Führen Sie die Visual Basic-Anwendung oder das Skript aus.  
  
    > [!NOTE]
    >  Der Dienst, den Sie aufrufen, muss einen MEX-Endpunkt für den Moniker verfügbar machen, damit dieser die Metadaten aus dem Dienst lesen kann. Weitere Informationen finden Sie unter [Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md).  
  
    > [!NOTE]
    >  Ist der Moniker nicht ordnungsgemäß formatiert oder der Dienst nicht verfügbar, wird nach dem `GetObject`-Aufruf ein Syntaxfehler zurückgegeben.  Vergewissern Sie sich bei Auftreten dieses Fehlers, dass der verwendete Moniker korrekt und der Dienst verfügbar ist.  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Verwenden des Windows Communication Foundation-Dienstmonikers ohne Registrierung](../../../../docs/framework/wcf/feature-details/use-the-wcf-service-moniker-without-registration.md)
- [Vorgehensweise: Verwenden eines Dienstmonikers mit WSDL-Verträgen](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-wsdl-contracts.md)
