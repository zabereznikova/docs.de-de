---
title: 'Vorgehensweise: Konfigurieren von COM+-Diensteinstellungen'
ms.date: 03/30/2017
helpviewer_keywords:
- COM+ [WCF], configuring service settings
ms.assetid: f42a55a8-3af8-4394-9fdd-bf12a93780eb
ms.openlocfilehash: b75f5c2a64b7184959e929439893b33193aa7bae
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96257469"
---
# <a name="how-to-configure-com-service-settings"></a>Vorgehensweise: Konfigurieren von COM+-Diensteinstellungen

Wird eine Anwendungsschnittstelle durch Verwendung des COM+-Dienskonfigurationstools hinzugefügt oder entfernt, wird die Webdienstkonfiguration innerhalb der Konfigurationsdatei der Anwendung aktualisiert. Im gehosteten com+-Modus wird die Application.config-Datei im Stammverzeichnis der Anwendung abgelegt (%ProgramFiles%\ComPlus Applications \\ {AppID} ist die Standardeinstellung). In beiden im Internet gehosteten Modi wird die Datei Web.config im angegebenen vroot-Verzeichnis abgelegt.  
  
> [!NOTE]
> Nachrichtensignaturen sollten zum Schutz vor Manipulation von Nachrichten zwischen einem Client und einem Server verwendet werden. Außerdem sollte Verschlüsselung auf Nachrichten- oder Transportebene verwendet werden, um Schutz vor der Offenlegung von Informationen in Nachrichten zu bieten, die zwischen einem Client und einem Server übertragen werden. Wie bei den Windows Communication Foundation (WCF)-Diensten sollten Sie die Drosselung verwenden, um die Anzahl gleichzeitiger Aufrufe, Verbindungen, Instanzen und ausstehende Vorgänge einzuschränken. Dies trägt zur Vermeidung einer übermäßigen Ressourcenbeanspruchung bei. Das Drosselungsverhalten wird durch Dienstkonfigurations-Dateieinstellungen angegeben.  
  
## <a name="example"></a>Beispiel  

 Beispiel: Eine Komponente, mit der die folgende Schnittstelle implementiert wird:  
  
```csharp
[Guid("C551FBA9-E3AA-4272-8C2A-84BD8D290AC7")]  
public interface IFinances  
{  
    string Debit(string accountNo, double amount);  
    string Credit(string accountNo, double amount);  
}  
```  
  
 Wird die Komponente als Webdienst verfügbar gemacht, sieht der entsprechende verfügbare Dienstvertrag, dessen Vorgaben die Clients entsprechen müssen, folgendermaßen aus:  
  
```csharp
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
> IID bildet einen Teil des ursprünglichen Namespaces für den Vertrag.  
  
 Clientanwendungen, die diesen Dienst verwenden, müssen den Vorgaben dieses Vertrags entsprechen und eine Bindung verwenden, die mit der in der Anwendungskonfiguration angegebenen Bindung kompatibel ist.  
  
 Das folgende Codebeispiel zeigt eine standardmäßige Konfigurationsdatei. Da es sich um einen Windows Communication Foundation (WCF)-Webdienst handelt, entspricht dieser dem Standard Konfigurations Schema des Dienst Modells und kann auf die gleiche Weise wie andere Konfigurationsdateien für WCF-Dienste bearbeitet werden.  
  
 Folgende Änderungen sind üblich:  
  
- Das Ändern der Endpunktadresse vom standardmäßigen Format Anwendungsname/Komponentenname/Schnittstellenname in eine benutzerfreundlichere Form.  
  
- Ändern des Namespaces des Dienstanbieter von der Standard `http://tempuri.org/InterfaceID` Form in eine relevantere Form.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- [Integration in com+-Anwendungen](integrating-with-com-plus-applications.md)
