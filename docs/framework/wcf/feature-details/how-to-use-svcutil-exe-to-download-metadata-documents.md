---
title: 'Vorgehensweise: Verwenden von „Svcutil.exe“ zum Herunterladen von Metadatendokumenten'
description: Erfahren Sie, wie Sie mit Svcutil.exe Metadaten aus laufenden Diensten herunterladen und die Metadaten in lokalen Dateien speichern.
ms.date: 03/30/2017
ms.assetid: 15524274-3167-4627-b722-d6cedb9fa8c6
ms.openlocfilehash: 42df55fe7bbae6d8c977263e05053d8a8fa87aff
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246765"
---
# <a name="how-to-use-svcutilexe-to-download-metadata-documents"></a>Vorgehensweise: Verwenden von „Svcutil.exe“ zum Herunterladen von Metadatendokumenten
Svcutil.exe kann verwendet werden, um Metadaten aus ausgeführten Diensten herunterzuladen und die Metadaten in lokalen Dateien zu speichern. Bei http-und HTTPS-URL-Schemas versucht Svcutil.exe, Metadaten mithilfe von WS-MetadataExchange und der [XML-Webdienst](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/fxx6cfx2(v=vs.100))Ermittlung abzurufen. Bei allen anderen URL-Schemas verwendet Svcutil.exe nur WS-MetadataExchange.  
  
 Standardmäßig verwendet Svcutil.exe die in der <xref:System.ServiceModel.Description.MetadataExchangeBindings>-Klasse definierten Bindungen. Wenn Sie die für WS-MetadataExchange verwendete Bindung konfigurieren möchten, müssen Sie einen Clientendpunkt in der Konfigurationsdatei für „Svcutil.exe“ (svcutil.exe.config) definieren, der den `IMetadataExchange`-Vertrag verwendet und über dasselbe URI-Schema der Metadaten-Endpunktadresse verfügt.  
  
> [!CAUTION]
> Beim Ausführen Svcutil.exe zum Abrufen von Metadaten für einen Dienst, der zwei verschiedene Dienstverträge verfügbar macht, die jeweils einen gleichnamigen Vorgang enthalten, zeigt Svcutil.exe einen Fehler an, der besagt, dass keine Metadaten von... abgerufen werden können. Wenn Sie z. b. über einen Dienst verfügen, der einen Dienstvertrag mit dem Namen verfügbar macht `ICarService` , der über einen-Vorgang verfügt `Get(Car c)` und der gleiche Dienst einen Dienstvertrag namens mit einem-Vorgang bereitstellt `IBookService` `Get(Book b)` . Führen Sie einen der folgenden Schritte aus, um dieses Problem zu umgehen:
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
  
3. Das <`url`>-Argument gibt die URL zu einem Dienst Endpunkt an, der Metadaten bereitstellt, oder ein Metadatendokument, das online gehostet wird. Das <`epr`>-Argument gibt den Pfad zu einer XML-Datei an, die eine WS-Adressierung `EndpointAddress` für einen Dienst Endpunkt enthält, der WS-MetadataExchange unterstützt.  
  
 Weitere Optionen zur Verwendung dieses Tools für das Herunterladen von Metadaten finden Sie unter [Service Model Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md).  
  
## <a name="example"></a>Beispiel  
 Der folgende Befehl lädt Metadatendokumente aus einem ausführenden Dienst herunter.  
  
```console
svcutil /t:metadata http://service/metadataEndpoint  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [ServiceModel Metadata Utility-Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md)
