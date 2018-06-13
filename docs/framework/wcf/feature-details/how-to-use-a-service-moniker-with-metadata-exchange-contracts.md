---
title: 'Vorgehensweise: Verwenden eines Dienstmonikers mit Metadatenaustausch-Verträgen'
ms.date: 03/30/2017
ms.assetid: c41a07e5-cb9d-45d6-9ea4-34511e227faf
ms.openlocfilehash: 6265860c2e1efb2f74a0243157a223a33889629a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33491249"
---
# <a name="how-to-use-a-service-moniker-with-metadata-exchange-contracts"></a>Vorgehensweise: Verwenden eines Dienstmonikers mit Metadatenaustausch-Verträgen
Nach dem Entwickeln einige neue WCF-Dienste, können Sie entscheiden, dass diese Dienste aus einem Skript oder einer Visual Basic 6.0-Anwendung aufrufen soll. Eine Methode wäre, generieren eine WCF-Clientassembly, die Assembly bei COM registriert, die Assembly im GAC installieren, und verweisen dann die COM-Typen aus dem Visual Basic-Code. Wenn Sie die Anwendung verteilen, müssen Sie auch die WCF-Client-Assembly zu verteilen. Der Benutzer muss dann die WCF-Clientassembly bei COM registrieren und im GAC platzieren. WCF-COM-Interop ermöglicht Ihnen die gleichen Dienstaufrufe ohne Rückgriff auf einen WCF-Clientassembly. Der WCF-Monikers können Sie WCF-Dienst aus einer beliebigen COM-kompatiblen Sprache (Visual Basic, VBScript, Visual Basic for Applications (VBA) usw.) aufrufen, durch Angabe von einem Metadatenaustausch (Mex)-Endpunkt URI, der der Dienstmoniker zum Extrahieren von Typ verwendet Informationen zum Dienst. Dieses Thema beschreibt, wie das erste Schritte mit WCF-Beispiel, das mit einem WCF-Moniker, der einen Mex-Endpunkt angibt.  
  
> [!NOTE]
>  Durch die WCF-Clientassembly definierten Typen werden nie tatsächlich instanziiert. Die Assembly wird nur für Metadaten verwendet.  
  
### <a name="using-the-service-moniker-with-a-mex-address"></a>Verwenden des Dienstmonikers mit einer MEX-Adresse  
  
1.  Erstellen Sie das Beispiel Einstieg und Verwenden von Internet Explorer, um die URL zu suchen (http://localhost/ServiceModelSamples/Service.svc) um sicherzustellen, dass der Dienst funktioniert.  
  
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
 [Vorgehensweise: Verwenden des Windows Communication Foundation-Dienstmonikers ohne Registrierung](../../../../docs/framework/wcf/feature-details/use-the-wcf-service-moniker-without-registration.md)  
 [Vorgehensweise: Verwenden eines Dienstmonikers mit WSDL-Verträgen](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-wsdl-contracts.md)
