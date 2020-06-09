---
title: 'Vorgehensweise: Verwenden des Windows Communication Foundation-Dienstmonikers ohne Registrierung'
ms.date: 03/30/2017
helpviewer_keywords:
- COM [WCF], service monikers without registration
ms.assetid: ee3cf5c0-24f0-4ae7-81da-73a60de4a1a8
ms.openlocfilehash: f69314948a0e0a69e49ec148f94572f17d0b8e3c
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595049"
---
# <a name="how-to-use-the-windows-communication-foundation-service-moniker-without-registration"></a>Vorgehensweise: Verwenden des Windows Communication Foundation-Dienstmonikers ohne Registrierung
Zum Herstellen einer Verbindung mit einem Windows Communication Foundation (WCF)-Dienst muss eine WCF-Client Anwendung über die Details der Dienst Adresse, der Bindungs Konfiguration und des Dienstvertrags verfügen.  
  
 Der WCF-Dienstmoniker ruft in der Regel den erforderlichen Vertrag durch vorherige Registrierung der erforderlichen Attributtypen ab, aber es gibt Fälle, in denen dies nicht möglich ist. Anstelle der Registrierung kann der Moniker die Definition des Vertrags in Form eines Web Services Definition Language (WSDL)-Dokuments abrufen. Dies geschieht durch Verwendung des `wsdl`-Parameters, durch Metadatenaustausch oder durch Verwendung des `mexAddress`-Parameters.  
  
 Dadurch wird beispielsweise die Verteilung eines Excel-Arbeitsblatts, in dem einige Zellenwerte anhand von Webdienstinteraktionen berechnet werden, ermöglicht. In diesem Szenario kann die Dienstvertragassembly möglicherweise nicht auf allen Clients registriert werden, von denen das Dokument ggf. geöffnet wird. Der `wsdl`-Parameter oder der `mexAddress`-Parameter aktiviert eine in sich geschlossene Projektmappe.  
  
> [!NOTE]
> Gegenseitige Authentifizierung muss verwendet werden, um Schutz vor Anforderungs- und Antwortmanipulation oder Spoofing zu bieten. Insbesondere benötigen Clients die Gewährleistung, dass es sich beim antwortenden Endpunkt des Metadatenaustauschs um die gewünschte vertrauenswürdige Partei handelt.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird die Verwendung des Dienstmonikers mit einem MEX-Vertrag veranschaulicht. Ein Dienst mit dem folgenden Vertrag wird mit wsHttpBinding verfügbar gemacht.  
  
```csharp
using System.ServiceModel;  
  
// ...
  
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
  
 Um einen WCF-Client für den Remote Dienst zu erstellen, kann die folgende Beispielmonikerzeichenfolge verwendet werden.  
  
```
service4:mexAddress="http://servername/Affiliates/service.svc/mex",  
address="http://servername/Affiliates/service.svc",  
contract=IAffiliate, contractNamespace=http://Microsoft.ServiceModel.Demo,  
binding=WSHttpBinding_IAffiliate, bindingNamespace=http://tempuri.org/  
```  
  
 Während der Ausführung der Clientanwendung führt der Client `WS-MetadataExchange` mit der bereitgestellten `mexAddress` aus. Dabei werden unter Umständen Adresse, Bindung und Vertragsdetails für eine Reihe von Diensten zurückgegeben. Der `address`-Parameter, der `contract`-Parameter, der `contractNamespace`-Parameter, der `binding`-Parameter und der `bindingNamespace`-Parameter werden zum Identifizieren des gewünschten Diensts verwendet. Nachdem diese Parameter abgeglichen wurden, erstellt der Moniker einen WCF-Client mit der entsprechenden Vertrags Definition, und Aufrufe können dann mithilfe des WCF-Clients wie beim typisierten Vertrag durchgeführt werden.  
  
> [!NOTE]
> Ist der Moniker nicht ordnungsgemäß formatiert oder der Dienst nicht verfügbar, wird nach dem `GetObject`-Aufruf ein Syntaxfehler zurückgegeben. Vergewissern Sie sich bei Auftreten dieses Fehlers, dass der verwendete Moniker korrekt und der Dienst verfügbar ist.  
  
## <a name="see-also"></a>Weitere Informationen

- [Vorgehensweise: Registrieren und Konfigurieren eines Dienstmonikers](how-to-register-and-configure-a-service-moniker.md)
