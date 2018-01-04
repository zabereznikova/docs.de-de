---
title: 'Vorgehensweise: Verwenden von "Svcutil.exe" zum Exportieren von Metadaten aus kompiliertem Dienstcode'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 95d0aed3-16a2-4398-89bb-39418eeb7355
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6e50ddaa5a9fe5038ef167c4a53f9600eda0f027
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-svcutilexe-to-export-metadata-from-compiled-service-code"></a>Vorgehensweise: Verwenden von "Svcutil.exe" zum Exportieren von Metadaten aus kompiliertem Dienstcode
"Svcutil.exe" kann Metadaten für Dienste, Verträge und Datentypen in kompilierten Assemblys wie folgt exportieren:  
  
-   Zum Exportieren von Metadaten für alle kompilierten Dienstverträge für eine Assemblygruppe mithilfe von "Svcutil.exe" geben Sie die Assemblys als Eingabeparameter an. Dies ist das Standardverhalten.  
  
-   Zum Exportieren von Metadaten für einen kompilierten Dienst mithilfe von "Svcutil.exe" geben Sie die Dienstassembly bzw. -assemblys als Eingabeparameter an. Sie müssen die `/serviceName`-Option verwenden, um den Konfigurationsnamen des Diensts anzugeben, den Sie exportieren möchten. "Svcutil.exe" lädt die Konfigurationsdatei für die angegebene ausführbare Assembly automatisch.  
  
-   Um alle Datenvertragstypen innerhalb einer Assemblygruppe zu exportieren, verwenden Sie die `/dataContractOnly`-Option.  
  
> [!NOTE]
>  Zum Angeben von Dateipfaden zu abhängigen Assemblys verwenden Sie die `/reference`-Option.  
  
### <a name="to-export-metadata-for-compiled-service-contracts"></a>So exportieren Sie Metadaten für kompilierte Dienstverträge  
  
1.  Kompilieren Sie die Dienstvertragsimplementierungen in eine oder mehrere Klassenbibliotheken.  
  
2.  Führen Sie "Svcutil.exe" auf den kompilierten Assemblys aus.  
  
    > [!NOTE]
    >  Zum Angeben des Dateipfads zur abhängigen Assembly müssen Sie möglicherweise den `/reference`-Schalter verwenden.  
  
    ```  
    svcutil.exe Contracts.dll  
    ```  
  
### <a name="to-export-metadata-for-a-compiled-service"></a>So exportieren Sie Metadaten füreinen kompilierten Dienst  
  
1.  Kompilieren Sie die Dienstimplementierung in eine ausführbare Assembly.  
  
2.  Erstellen Sie eine Konfigurationsdatei für die ausführbare Dienstdatei, und fügen Sie eine Dienstkonfiguration hinzu.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <system.serviceModel>  
        <services>  
          <service name="MyService" >  
            <endpoint address="finder" contract="IPeopleFinder" binding="wsHttpBinding" />  
          </service>  
        </services>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
3.  Zum Angeben des Konfigurationsnamen des Diensts führen Sie "Svcutil.exe" für die kompilierte ausführbare Dienstdatei mithilfe des `/serviceName`-Schalters aus.  
  
    > [!NOTE]
    >  Zum Angeben des Dateipfads zur abhängigen Assembly müssen Sie möglicherweise den `/reference`-Schalter verwenden.  
  
    ```  
    svcutil.exe /serviceName:MyService Service.exe /reference:path/Contracts.dll  
    ```  
  
### <a name="to-export-metadata-for-compiled-data-contracts"></a>So exportieren Sie Metadaten für kompilierte Datenverträge  
  
1.  Kompilieren Sie die Datenvertragsimplementierungen in eine oder mehrere Klassenbibliotheken.  
  
2.  Führen Sie "Svcutil.exe" für die kompilierten Assemblys mithilfe des `/dataContract`-Schalters aus, um anzugeben, dass nur Metadaten für Datenverträge generiert werden sollen.  
  
    > [!NOTE]
    >  Zum Angeben des Dateipfads zur abhängigen Assembly müssen Sie möglicherweise den `/reference`-Schalter verwenden.  
  
    ```  
    svcutil.exe /dataContractOnly Contracts.dll  
    ```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie Metadaten für eine einfache Dienstimplementierung und -konfiguration generiert werden.  
  
 So exportieren Sie Metadaten für den Dienstvertrag  
  
```  
svcutil.exe Contracts.dll  
```  
  
 So exportieren Sie Metadaten für Datenverträge  
  
```  
svcutil.exe /dataContractOnly Contracts.dll  
```  
  
 So exportieren Sie Metadaten für die Dienstimplementierung  
  
```  
svcutil.exe /serviceName:MyService Service.exe /reference:<path>/Contracts.dll  
```  
  
 Der `<path>` entspricht dem Pfad zu "Contracts.dll".  
  
```  
// The following service contract and data contracts are compiled into   
// Contracts.dll.  
[ServiceContract(ConfigurationName="IPeopleFinder")]  
public interface IPersonFinder  
{  
    [OperationContract]  
    Address GetAddress(Person s);  
}  
  
[DataContract]  
public class Person  
{  
    [DataMember]  
    public string firstName;  
    [DataMember]  
    public string lastName;  
    [DataMember]  
    public int age;  
}  
  
[DataContract]  
public class Address  
{  
    [DataMember]  
    public string city;  
    [DataMember]  
    public string state;  
    [DataMember]  
    public string street;  
    [DataMember]  
    public int zipCode;  
    [DataMember]  
    public Person person;  
}  
  
// The following service implementation is compiled into Service.exe.     
// This service uses the contracts specified in Contracts.dll.  
[ServiceBehavior(ConfigurationName = "MyService")]  
public class MyService : IPersonFinder  
{  
    public Address GetAddress(Person person)  
    {  
        Address address = new Address();  
        address.person = person;  
        return address;  
    }  
}  
  
<!-- The following is the configuration file for Service.exe. -->  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service name="MyService">  
         <endpoint  address="finder"  
                    binding="basicHttpBinding"  
                    contract="IPeopleFinder"/>  
      </service>  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [ServiceModel Metadata Utility-Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)  
 [Exportieren und Importieren von Metadaten](../../../../docs/framework/wcf/feature-details/exporting-and-importing-metadata.md)
