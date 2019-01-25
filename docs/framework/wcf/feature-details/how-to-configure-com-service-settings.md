---
title: 'Vorgehensweise: Konfigurieren von COM+-Diensteinstellungen'
ms.date: 03/30/2017
helpviewer_keywords:
- COM+ [WCF], configuring service settings
ms.assetid: f42a55a8-3af8-4394-9fdd-bf12a93780eb
ms.openlocfilehash: 8deb7be51cdf3273a57d6777b103123636a2d2f8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54637397"
---
# <a name="how-to-configure-com-service-settings"></a>Vorgehensweise: Konfigurieren von COM+-Diensteinstellungen
Wird eine Anwendungsschnittstelle durch Verwendung des COM+-Dienskonfigurationstools hinzugefügt oder entfernt, wird die Webdienstkonfiguration innerhalb der Konfigurationsdatei der Anwendung aktualisiert. Im COM+-gehosteten Modus befindet sich die Datei Application.config im Stammverzeichnis Anwendung (%PROGRAMFILES%\ComPlus Anwendungen\\{Appid} ist die Standardeinstellung). In beiden im Internet gehosteten Modi wird die Datei Web.config im angegebenen vroot-Verzeichnis abgelegt.  
  
> [!NOTE]
>  Nachrichtensignaturen sollten zum Schutz vor Manipulation von Nachrichten zwischen einem Client und einem Server verwendet werden. Außerdem sollte Verschlüsselung auf Nachrichten- oder Transportebene verwendet werden, um Schutz vor der Offenlegung von Informationen in Nachrichten zu bieten, die zwischen einem Client und einem Server übertragen werden. Wie bei Windows Communication Foundation (WCF)-Diensten, sollten Sie die Drosselung verwenden, um die Anzahl der gleichzeitigen Anrufe, Verbindungen, Instanzen und ausstehenden Vorgänge zu beschränken. Dies trägt zur Vermeidung einer übermäßigen Ressourcenbeanspruchung bei. Das Drosselungsverhalten wird durch Dienstkonfigurations-Dateieinstellungen angegeben.  
  
## <a name="example"></a>Beispiel  
 Beispiel: Eine Komponente, mit der die folgende Schnittstelle implementiert wird:  
  
```  
[Guid("C551FBA9-E3AA-4272-8C2A-84BD8D290AC7")]  
public interface IFinances  
{  
    string Debit(string accountNo, double amount);  
    string Credit(string accountNo, double amount);  
}  
```  
  
 Wird die Komponente als Webdienst verfügbar gemacht, sieht der entsprechende verfügbare Dienstvertrag, dessen Vorgaben die Clients entsprechen müssen, folgendermaßen aus:  
  
```  
[ServiceContract(Session = true,  
Namespace = "http://tempuri.org/C551FBA9-E3AA-4272-8C2A-84BD8D290AC7",  
Name = "IFinances")]  
public interface IFinancesContract : IDisposable  
{  
    [OperationContract]  
    string Debit(string accountNo, double amount);  
    [OperationContract]  
    string Credit(string accountNo, double amount);  
}  
```  
  
> [!NOTE]
>  IID bildet einen Teil des ursprünglichen Namespaces für den Vertrag.  
  
 Clientanwendungen, die diesen Dienst verwenden, müssen den Vorgaben dieses Vertrags entsprechen und eine Bindung verwenden, die mit der in der Anwendungskonfiguration angegebenen Bindung kompatibel ist.  
  
 Das folgende Codebeispiel zeigt eine standardmäßige Konfigurationsdatei. Einen Windows Communication Foundation (WCF)-Webdienst, dies entspricht dem standard-Service Model Configuration Schema und kann bearbeitet werden, auf die gleiche Weise wie andere WCF-Services-Konfigurationsdateien.  
  
 Folgende Änderungen sind üblich:  
  
- Das Ändern der Endpunktadresse vom standardmäßigen Format Anwendungsname/Komponentenname/Schnittstellenname in eine benutzerfreundlichere Form.  
  
- Ändern den Namespace des Diensts von der Standardeinstellung `http://tempuri.org/InterfaceID` Formular aus, um eine aussagekräftigere Form.  
  
- Das Ändern des Endpunkts, um eine andere Transportbindung zu verwenden.  
  
     Bei einem Hosting durch COM+ wird standardmäßig der Transport mittels benannter Pipes verwendet, doch es kann auch ein Datentransportprotokoll wie TCP verwendet werden.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
    <system.serviceModel>  
        <bindings>  
            <netNamedPipeBinding>  
                <binding name="comNonTransactionalBinding" />  
                <binding name="comTransactionalBinding" transactionFlow="true" />  
            </netNamedPipeBinding>  
        </bindings>  
        <comContracts>  
            <comContract contract="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}"  
                name="IFinances" namespace="http://tempuri.org/C551FBA9-E3AA-4272-8C2A-84BD8D290AC7"  
                requiresSession="true">  
                <exposedMethods>  
                    <add exposedMethod="Debit" />  
                    <add exposedMethod="Credit" />  
                </exposedMethods>  
            </comContract>  
        </comContracts>  
        <services>  
            <service name="{DCDB24CC-0B19-4534-95CD-FBBFF4D67DD9},{C942B840-AD54-4A44-B5F7-928130980AB9}">  
                <endpoint address="IFinances" binding="netNamedPipeBinding" bindingConfiguration="comNonTransactionalBinding"  
                    contract="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}" />  
                <host>  
                    <baseAddresses>  
                        <add baseAddress="net.pipe://localhost/ServiceModelDocSampleApp/ServiceModelDocSample.esFinance" />  
                    </baseAddresses>  
                </host>  
            </service>  
        </services>  
    </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch
- [Integrieren von COM+-Anwendungen](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
