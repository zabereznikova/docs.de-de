---
title: 'Gewusst wie: Verwenden von Svcutil.exe zum Herunterladen von Metadatendokumenten'
ms.date: 03/30/2017
ms.assetid: 15524274-3167-4627-b722-d6cedb9fa8c6
ms.openlocfilehash: 6643f0a5dba98afcef38870cf24d91e7d69a1440
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/26/2018
ms.locfileid: "47195419"
---
# <a name="how-to-use-svcutilexe-to-download-metadata-documents"></a>Gewusst wie: Verwenden von Svcutil.exe zum Herunterladen von Metadatendokumenten
Svcutil.exe kann verwendet werden, um Metadaten aus ausgeführten Diensten herunterzuladen und die Metadaten in lokalen Dateien zu speichern. Bei HTTP und HTTPS-URL-Schemas versucht Svcutil.exe zum Abrufen von Metadaten mit WS-MetadataExchange und [XML-Webdienstsuche](https://go.microsoft.com/fwlink/?LinkId=94950). Bei allen anderen URL-Schemas verwendet Svcutil.exe nur WS-MetadataExchange.  
  
 Standardmäßig verwendet Svcutil.exe die in der <xref:System.ServiceModel.Description.MetadataExchangeBindings>-Klasse definierten Bindungen. Wenn Sie die für WS-MetadataExchange verwendete Bindung konfigurieren möchten, müssen Sie einen Clientendpunkt in der Konfigurationsdatei für "Svcutil.exe" (svcutil.exe.config) definieren, der den `IMetadataExchange`-Vertrag verwendet und über dasselbe URI-Schema der Metadaten-Endpunktadresse verfügt.  
  
> [!CAUTION]
> Beim Ausführen von Svcutil.exe zum Abrufen von Metadaten für einen Dienst, der zwei anderen Dienst verfügbar macht, Verträge, die jeweils einen Vorgang mit dem gleichen Namen enthalten, werden Svcutil.exe eine Fehlermeldung, "Können keine Metadaten von abgerufen..." angezeigt. Wenn Sie einen Dienst haben, die einen Dienstvertrag namens verfügbar macht z. B. `ICarService` , bei dem einen Vorgang `Get(Car c)` und der gleiche Dienst verfügbar macht, einen Dienstvertrag namens `IBookService` , bei dem einen Vorgang `Get(Book b)`. Verwenden Sie eine der folgenden Vorgehensweisen, um dieses Problem zu umgehen:
>
> - Benennen Sie eine der Operationen um.
> - Legen Sie die <xref:System.ServiceModel.OperationContractAttribute.Name%2A>-Eigenschaft auf einen anderen Namen fest.
> - Legen Sie einen der Namespaces der Operation mit der <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A>-Eigenschaft auf einen anderen Namespace fest.
  
## <a name="to-download-metadata-using-svcutilexe"></a>So laden Sie Metadaten mit Svcutil.exe herunter  
  
1.  Suchen Sie das Tool Svcutil.exe am folgenden Speicherort:  
  
     C:\Programme\Microsoft SDKs\Windows\v1.0.\bin  
  
2.  Starten Sie das Tool an der Eingabeaufforderung mit dem folgenden Format.  
  
    ```  
    svcutil.exe /t:metadata  <url>* | <epr>  
    ```  
  
     Um Metadaten herunterzuladen, müssen Sie die `/t:metadata`-Option angeben. Andernfalls werden Clientcode und -konfiguration generiert.  
  
3.  Die <`url`>-Argument gibt die URL zu einem Dienstendpunkt, der Metadaten bereitstellt, oder zu einem online gehosteten Metadatendokument. Die <`epr`>-Argument gibt den Pfad einer XML-Datei, die eine WS-Adressierung enthält `EndpointAddress` für einen Dienstendpunkt, der WS-MetadataExchange unterstützt.  
  
 Weitere Optionen zur Verwendung dieses Tools zum Herunterladen von Metadaten finden Sie unter [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).  
  
## <a name="example"></a>Beispiel  
 Der folgende Befehl lädt Metadatendokumente aus einem ausführenden Dienst herunter.  
  
```  
svcutil /t:metadata http://service/metadataEndpoint  
```  
  
## <a name="see-also"></a>Siehe auch  
 [ServiceModel Metadata Utility-Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
