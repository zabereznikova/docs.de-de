---
title: 'Gewusst wie: Verwenden von Svcutil.exe zum Herunterladen von Metadatendokumenten'
ms.date: 03/30/2017
ms.assetid: 15524274-3167-4627-b722-d6cedb9fa8c6
ms.openlocfilehash: 359cdb58ef65c9fb69c0ecfc759f70164a369cce
ms.sourcegitcommit: 09b4090b78f52fd09b0e430cd4b26576f1fdf96e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2020
ms.locfileid: "76212106"
---
# <a name="how-to-use-svcutilexe-to-download-metadata-documents"></a>Gewusst wie: Verwenden von Svcutil.exe zum Herunterladen von Metadatendokumenten
Svcutil.exe kann verwendet werden, um Metadaten aus ausgeführten Diensten herunterzuladen und die Metadaten in lokalen Dateien zu speichern. Für http-und HTTPS-URL-Schemas versucht Svcutil. exe, Metadaten mithilfe von WS-MetadataExchange und der [XML-Webdienst](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/fxx6cfx2(v=vs.100))Ermittlung abzurufen. Bei allen anderen URL-Schemas verwendet Svcutil.exe nur WS-MetadataExchange.  
  
 Standardmäßig verwendet Svcutil.exe die in der <xref:System.ServiceModel.Description.MetadataExchangeBindings>-Klasse definierten Bindungen. Wenn Sie die für WS-MetadataExchange verwendete Bindung konfigurieren möchten, müssen Sie einen Clientendpunkt in der Konfigurationsdatei für „Svcutil.exe“ (svcutil.exe.config) definieren, der den `IMetadataExchange`-Vertrag verwendet und über dasselbe URI-Schema der Metadaten-Endpunktadresse verfügt.  
  
> [!CAUTION]
> Beim Ausführen von "Svcutil. exe" zum Abrufen von Metadaten für einen Dienst, der zwei verschiedene Dienstverträge verfügbar macht, die jeweils einen gleichnamigen Vorgang enthalten, zeigt Svcutil. exe einen Fehler an, der besagt, dass keine Metadaten von... abgerufen werden können. Wenn Sie z. b. über einen Dienst verfügen, der einen Dienstvertrag mit dem Namen `ICarService` verfügbar macht, der über einen Vorgang verfügt `Get(Car c)` und derselbe Dienst einen Dienstvertrag mit dem Namen `IBookService` verfügbar macht, der einen Vorgang `Get(Book b)`hat. Verwenden Sie eine der folgenden Vorgehensweisen, um dieses Problem zu umgehen:
>
> - Benennen Sie eine der Operationen um.
> - Legen Sie die <xref:System.ServiceModel.OperationContractAttribute.Name%2A>-Eigenschaft auf einen anderen Namen fest.
> - Legen Sie einen der Namespaces der Operation mit der <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A>-Eigenschaft auf einen anderen Namespace fest.
  
## <a name="to-download-metadata-using-svcutilexe"></a>So laden Sie Metadaten mit Svcutil.exe herunter  
  
1. Suchen Sie das Tool Svcutil.exe am folgenden Speicherort:  
  
     C:\Programme\Microsoft SDKs\Windows\v1.0.\bin  
  
2. Starten Sie das Tool an der Eingabeaufforderung mit dem folgenden Format.  
  
    ```console
    svcutil.exe /t:metadata  <url>* | <epr>  
    ```  
  
     Um Metadaten herunterzuladen, müssen Sie die `/t:metadata`-Option angeben. Andernfalls werden Clientcode und -konfiguration generiert.  
  
3. Das <`url`>-Argument gibt die URL zu einem Dienst Endpunkt an, der Metadaten bereitstellt, oder zu einem Metadatendokument, das online gehostet wird. Das <`epr`>-Argument gibt den Pfad zu einer XML-Datei an, die eine WS-Adressierungs `EndpointAddress` für einen Dienst Endpunkt enthält, der WS-MetadataExchange unterstützt.  
  
 Weitere Optionen zur Verwendung dieses Tools für das Herunterladen von Metadaten finden Sie unter [Service Model Metadata Utility-Tool (Svcutil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).  
  
## <a name="example"></a>Beispiel  
 Der folgende Befehl lädt Metadatendokumente aus einem ausführenden Dienst herunter.  
  
```console
svcutil /t:metadata http://service/metadataEndpoint  
```  
  
## <a name="see-also"></a>Siehe auch

- [ServiceModel Metadata Utility-Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
