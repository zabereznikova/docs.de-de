---
title: "Vorgehensweise: Verwenden eines Dienstmonikers mit Metadatenaustausch-Verträgen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c41a07e5-cb9d-45d6-9ea4-34511e227faf
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7d2b5b6d4a671a3eb281f49dd60fd3c00ee76f8a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-a-service-moniker-with-metadata-exchange-contracts"></a>Vorgehensweise: Verwenden eines Dienstmonikers mit Metadatenaustausch-Verträgen
Nach dem Entwickeln neuer [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienste können Sie entscheiden, ob das Aufrufen dieser Dienste aus einem Skript oder einer Visual Basic 6.0-Anwendung möglich sein soll. Eine mögliche Methode ist das Generieren einer [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Clientassembly, das Registrieren der Assembly bei COM, das Installieren der Assembly im GAC und anschließend das Verweisen der COM-Typen aus dem Visual Basic-Code. Wenn Sie die Anwendung verteilen, müssen Sie auch die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Clientassembly verteilen. Der Benutzer muss dann die WCF-Clientassembly bei COM registrieren und im GAC platzieren. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-COM-Interop ermöglicht Ihnen die gleichen Dienstaufrufe ohne eine [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Clientassembly. Mithilfe des [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Monikers können Sie einen beliebigen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst aus jeder COM-kompatiblen Sprache (Visual Basic, VBScript, Visual Basic for Applications (VBA) usw.) aufrufen, indem Sie einen Metadatenaustausch (MEX)-Endpunkt-URI angeben, den der Dienstmoniker zum Extrahieren von Typinformationen über den Dienst verwendet. In diesem Thema wird beschrieben, wie das Beispiel für Erste Schritte mit [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] unter Verwendung eines [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Monikers aufgerufen wird, der einen MEX-Endpunkt angibt.  
  
> [!NOTE]
>  Die von der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Clientassembly definierten Typen werden nie tatsächlich instanziiert. Die Assembly wird nur für Metadaten verwendet.  
  
### <a name="using-the-service-moniker-with-a-mex-address"></a>Verwenden des Dienstmonikers mit einer MEX-Adresse  
  
1.  Erstellen Sie das Beispiel für Erste Schritte, und wechseln Sie in Internet Explorer zu seiner URL (http://localhost/ServiceModelSamples/Service.svc), um sicherzustellen, dass der Dienst funktioniert.  
  
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
