---
title: 'Vorgehensweise: Verwenden von „Svcutil.exe“ zum Exportieren von Metadaten aus kompiliertem Dienstcode'
ms.date: 03/30/2017
ms.assetid: 95d0aed3-16a2-4398-89bb-39418eeb7355
ms.openlocfilehash: 9acefdec63a6f518ead6cdbcb19ebc8c75609dd6
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595361"
---
# <a name="how-to-use-svcutilexe-to-export-metadata-from-compiled-service-code"></a><span data-ttu-id="1cb78-102">Vorgehensweise: Verwenden von „Svcutil.exe“ zum Exportieren von Metadaten aus kompiliertem Dienstcode</span><span class="sxs-lookup"><span data-stu-id="1cb78-102">How to: Use Svcutil.exe to Export Metadata from Compiled Service Code</span></span>
<span data-ttu-id="1cb78-103">"Svcutil.exe" kann Metadaten für Dienste, Verträge und Datentypen in kompilierten Assemblys wie folgt exportieren:</span><span class="sxs-lookup"><span data-stu-id="1cb78-103">Svcutil.exe can export metadata for services, contracts, and data types in compiled assemblies, as follows:</span></span>  
  
- <span data-ttu-id="1cb78-104">Zum Exportieren von Metadaten für alle kompilierten Dienstverträge für eine Assemblygruppe mithilfe von "Svcutil.exe" geben Sie die Assemblys als Eingabeparameter an.</span><span class="sxs-lookup"><span data-stu-id="1cb78-104">To export metadata for all compiled service contracts for a set of assemblies using Svcutil.exe, specify the assemblies as input parameters.</span></span> <span data-ttu-id="1cb78-105">Dies ist das Standardverhalten.</span><span class="sxs-lookup"><span data-stu-id="1cb78-105">This is the default behavior.</span></span>  
  
- <span data-ttu-id="1cb78-106">Zum Exportieren von Metadaten für einen kompilierten Dienst mithilfe von "Svcutil.exe" geben Sie die Dienstassembly bzw. -assemblys als Eingabeparameter an.</span><span class="sxs-lookup"><span data-stu-id="1cb78-106">To export metadata for a compiled service using Svcutil.exe, specify the service assembly or assemblies as input parameters.</span></span> <span data-ttu-id="1cb78-107">Sie müssen die `/serviceName`-Option verwenden, um den Konfigurationsnamen des Diensts anzugeben, den Sie exportieren möchten.</span><span class="sxs-lookup"><span data-stu-id="1cb78-107">You must use the `/serviceName` option to indicate the configuration name of the service you want to export.</span></span> <span data-ttu-id="1cb78-108">"Svcutil.exe" lädt die Konfigurationsdatei für die angegebene ausführbare Assembly automatisch.</span><span class="sxs-lookup"><span data-stu-id="1cb78-108">Svcutil.exe automatically loads the configuration file for the specified executable assembly.</span></span>  
  
- <span data-ttu-id="1cb78-109">Um alle Datenvertragstypen innerhalb einer Assemblygruppe zu exportieren, verwenden Sie die `/dataContractOnly`-Option.</span><span class="sxs-lookup"><span data-stu-id="1cb78-109">To export all data contract types within a set of assemblies, use the `/dataContractOnly` option.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1cb78-110">Zum Angeben von Dateipfaden zu abhängigen Assemblys verwenden Sie die `/reference`-Option.</span><span class="sxs-lookup"><span data-stu-id="1cb78-110">Use the `/reference` option to specify the file paths to any dependent assemblies.</span></span>  
  
### <a name="to-export-metadata-for-compiled-service-contracts"></a><span data-ttu-id="1cb78-111">So exportieren Sie Metadaten für kompilierte Dienstverträge</span><span class="sxs-lookup"><span data-stu-id="1cb78-111">To export metadata for compiled service contracts</span></span>  
  
1. <span data-ttu-id="1cb78-112">Kompilieren Sie die Dienstvertragsimplementierungen in eine oder mehrere Klassenbibliotheken.</span><span class="sxs-lookup"><span data-stu-id="1cb78-112">Compile your service contract implementations into one or more class libraries.1</span></span>  
  
2. <span data-ttu-id="1cb78-113">Führen Sie "Svcutil.exe" auf den kompilierten Assemblys aus.</span><span class="sxs-lookup"><span data-stu-id="1cb78-113">Run Svcutil.exe on the compiled assemblies.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="1cb78-114">Zum Angeben des Dateipfads zur abhängigen Assembly müssen Sie möglicherweise den `/reference`-Schalter verwenden.</span><span class="sxs-lookup"><span data-stu-id="1cb78-114">You might need to use the `/reference` switch to specify the file path to any dependent assemblies.</span></span>  
  
    ```console
    svcutil.exe Contracts.dll  
    ```  
  
### <a name="to-export-metadata-for-a-compiled-service"></a><span data-ttu-id="1cb78-115">So exportieren Sie Metadaten füreinen kompilierten Dienst</span><span class="sxs-lookup"><span data-stu-id="1cb78-115">To export metadata for a compiled service</span></span>  
  
1. <span data-ttu-id="1cb78-116">Kompilieren Sie die Dienstimplementierung in eine ausführbare Assembly.</span><span class="sxs-lookup"><span data-stu-id="1cb78-116">Compile your service implementation into an executable assembly.</span></span>  
  
2. <span data-ttu-id="1cb78-117">Erstellen Sie eine Konfigurationsdatei für die ausführbare Dienstdatei, und fügen Sie eine Dienstkonfiguration hinzu.</span><span class="sxs-lookup"><span data-stu-id="1cb78-117">Create a configuration file for your service executable and add a service configuration.</span></span>  
  
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
  
3. <span data-ttu-id="1cb78-118">Zum Angeben des Konfigurationsnamen des Diensts führen Sie "Svcutil.exe" für die kompilierte ausführbare Dienstdatei mithilfe des `/serviceName`-Schalters aus.</span><span class="sxs-lookup"><span data-stu-id="1cb78-118">Run Svcutil.exe on the compiled service executable using the `/serviceName` switch to specify the configuration name of the service.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="1cb78-119">Zum Angeben des Dateipfads zur abhängigen Assembly müssen Sie möglicherweise den `/reference`-Schalter verwenden.</span><span class="sxs-lookup"><span data-stu-id="1cb78-119">You might need to use the `/reference` switch to specify the file path to any dependent assemblies.</span></span>  
  
    ```console  
    svcutil.exe /serviceName:MyService Service.exe /reference:path/Contracts.dll  
    ```  
  
### <a name="to-export-metadata-for-compiled-data-contracts"></a><span data-ttu-id="1cb78-120">So exportieren Sie Metadaten für kompilierte Datenverträge</span><span class="sxs-lookup"><span data-stu-id="1cb78-120">To export metadata for compiled data contracts</span></span>  
  
1. <span data-ttu-id="1cb78-121">Kompilieren Sie die Datenvertragsimplementierungen in eine oder mehrere Klassenbibliotheken.</span><span class="sxs-lookup"><span data-stu-id="1cb78-121">Compile your data contract implementations into one or more class libraries.</span></span>  
  
2. <span data-ttu-id="1cb78-122">Führen Sie "Svcutil.exe" für die kompilierten Assemblys mithilfe des `/dataContract`-Schalters aus, um anzugeben, dass nur Metadaten für Datenverträge generiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="1cb78-122">Run Svcutil.exe on the compiled assemblies using the `/dataContract` switch to specify that only metadata for data contracts should be generated.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="1cb78-123">Zum Angeben des Dateipfads zur abhängigen Assembly müssen Sie möglicherweise den `/reference`-Schalter verwenden.</span><span class="sxs-lookup"><span data-stu-id="1cb78-123">You might need to use the `/reference` switch to specify the file path to any dependent assemblies.</span></span>  
  
    ```console  
    svcutil.exe /dataContractOnly Contracts.dll  
    ```  
  
## <a name="example"></a><span data-ttu-id="1cb78-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1cb78-124">Example</span></span>  
 <span data-ttu-id="1cb78-125">Im folgenden Beispiel wird veranschaulicht, wie Metadaten für eine einfache Dienstimplementierung und -konfiguration generiert werden.</span><span class="sxs-lookup"><span data-stu-id="1cb78-125">The following example demonstrates how to generate metadata for a simple service implementation and configuration.</span></span>  
  
 <span data-ttu-id="1cb78-126">So exportieren Sie Metadaten für den Dienstvertrag</span><span class="sxs-lookup"><span data-stu-id="1cb78-126">To export metadata for the service contract.</span></span>  
  
```console  
svcutil.exe Contracts.dll  
```  
  
 <span data-ttu-id="1cb78-127">So exportieren Sie Metadaten für Datenverträge</span><span class="sxs-lookup"><span data-stu-id="1cb78-127">To export metadata for the data contracts.</span></span>  
  
```console  
svcutil.exe /dataContractOnly Contracts.dll  
```  
  
 <span data-ttu-id="1cb78-128">So exportieren Sie Metadaten für die Dienstimplementierung</span><span class="sxs-lookup"><span data-stu-id="1cb78-128">To export metadata for the service implementation.</span></span>  
  
```console  
svcutil.exe /serviceName:MyService Service.exe /reference:<path>/Contracts.dll  
```  
  
 <span data-ttu-id="1cb78-129">Der `<path>` entspricht dem Pfad zu "Contracts.dll".</span><span class="sxs-lookup"><span data-stu-id="1cb78-129">The `<path>` is the path to Contracts.dll.</span></span>  
  
```csharp
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
```

```csharp
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
```

```xml  
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
  
## <a name="see-also"></a><span data-ttu-id="1cb78-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1cb78-130">See also</span></span>

- [<span data-ttu-id="1cb78-131">ServiceModel Metadata Utility-Tool (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="1cb78-131">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../servicemodel-metadata-utility-tool-svcutil-exe.md)
- [<span data-ttu-id="1cb78-132">Exportieren und Importieren von Metadaten</span><span class="sxs-lookup"><span data-stu-id="1cb78-132">Exporting and Importing Metadata</span></span>](exporting-and-importing-metadata.md)
