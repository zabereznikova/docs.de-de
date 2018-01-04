---
title: 'Gewusst wie: Verwenden des Windows Communication Foundation-Dienstmonikers ohne Registrierung'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: COM [WCF], service monikers without registration
ms.assetid: ee3cf5c0-24f0-4ae7-81da-73a60de4a1a8
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 18f575e9bae37b66526d7b61a641374266ba627b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-the-windows-communication-foundation-service-moniker-without-registration"></a>Gewusst wie: Verwenden des Windows Communication Foundation-Dienstmonikers ohne Registrierung
Soll eine Verbindung mit einem [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Dienst hergestellt und mit diesem kommuniziert werden, benötigt eine [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Clientanwendung die genauen Daten der Dienstadresse, der Bindungskonfiguration und des Dienstvertrags.  
  
 Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienstmoniker ruft in der Regel den erforderlichen Vertrag über vorherige Registrierung der erforderlichen Attributtypen ab, doch in manchen Fällen ist dies nicht möglich. Anstelle der Registrierung kann der Moniker die Definition des Vertrags in Form eines Web Services Definition Language (WSDL)-Dokuments abrufen. Dies geschieht durch Verwendung des `wsdl`-Parameters, durch Metadatenaustausch oder durch Verwendung des `mexAddress`-Parameters.  
  
 Dadurch wird beispielsweise die Verteilung eines Excel-Arbeitsblatts, in dem einige Zellenwerte anhand von Webdienstinteraktionen berechnet werden, ermöglicht. In diesem Szenario kann die Dienstvertragassembly möglicherweise nicht auf allen Clients registriert werden, von denen das Dokument ggf. geöffnet wird. Der `wsdl`-Parameter oder der `mexAddress`-Parameter aktiviert eine in sich geschlossene Projektmappe.  
  
> [!NOTE]
>  Gegenseitige Authentifizierung muss verwendet werden, um Schutz vor Anforderungs- und Antwortmanipulation oder Spoofing zu bieten. Insbesondere benötigen Clients die Gewährleistung, dass es sich beim antwortenden Endpunkt des Metadatenaustauschs um die gewünschte vertrauenswürdige Partei handelt.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird die Verwendung des Dienstmonikers mit einem MEX-Vertrag veranschaulicht. Ein Dienst mit dem folgenden Vertrag wird mit wsHttpBinding verfügbar gemacht.  
  
```  
using System.ServiceModel;  
  
...  
  
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Demo")]  
public interface IAffiliate  
{  
    [OperationContract]  
    bool NewAffiliate(string ID, string company, string fullname, string accountsCode);  
    [OperationContract]  
    bool RemoveAffiliate(string ID);  
    [OperationContract]  
    double RevenueCheckMonthly(ref string ID);  
    [OperationContract]  
    double RevenueCheckTotal(ref string ID);  
}  
```  
  
 Um einen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Client für den Remotedienst zu erstellen, kann die folgende Beispielmonikerzeichenfolge verwendet werden.  
  
```  
service4:mexAddress="http://servername/Affiliates/service.svc/mex",  
address="http://servername/Affiliates/service.svc",  
contract=IAffiliate, contractNamespace=http://Microsoft.ServiceModel.Demo,  
binding=WSHttpBinding_IAffiliate, bindingNamespace=http://tempuri.org/  
```  
  
 Während der Ausführung der Clientanwendung führt der Client `WS-MetadataExchange` mit der bereitgestellten `mexAddress` aus. Dabei werden unter Umständen Adresse, Bindung und Vertragsdetails für eine Reihe von Diensten zurückgegeben. Der `address`-Parameter, der `contract`-Parameter, der `contractNamespace`-Parameter, der `binding`-Parameter und der `bindingNamespace`-Parameter werden zum Identifizieren des gewünschten Diensts verwendet. Nach dem Abgleich dieser Parameter erstellt der Moniker einen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Client mit der erforderlichen Vertragsdefinition. Anschließend können Aufrufe mithilfe des [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Clients wie beim typisierten Vertrag ausgelöst werden.  
  
> [!NOTE]
>  Ist der Moniker nicht ordnungsgemäß formatiert oder der Dienst nicht verfügbar, wird nach dem `GetObject`-Aufruf ein Syntaxfehler zurückgegeben. Vergewissern Sie sich bei Auftreten dieses Fehlers, dass der verwendete Moniker korrekt und der Dienst verfügbar ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Registrieren und Konfigurieren eines Dienstmonikers](../../../../docs/framework/wcf/feature-details/how-to-register-and-configure-a-service-moniker.md)
