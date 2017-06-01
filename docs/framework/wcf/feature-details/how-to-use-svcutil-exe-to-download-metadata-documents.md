---
title: "Gewusst wie: Verwenden von Svcutil.exe zum Herunterladen von Metadatendokumenten | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 15524274-3167-4627-b722-d6cedb9fa8c6
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# Gewusst wie: Verwenden von Svcutil.exe zum Herunterladen von Metadatendokumenten
Svcutil.exe kann verwendet werden, um Metadaten aus ausgeführten Diensten herunterzuladen und die Metadaten in lokalen Dateien zu speichern.Bei HTTP\- und HTTPS\-URL\-Schemas versucht Svcutil.exe, Metadaten mit WS\-MetadataExchange und [XML Web Service Discovery](http://go.microsoft.com/fwlink/?LinkId=94950) abzurufen.Bei allen anderen URL\-Schemas verwendet Svcutil.exe nur WS\-MetadataExchange.  
  
 Standardmäßig verwendet Svcutil.exe die in der <xref:System.ServiceModel.Description.MetadataExchangeBindings>\-Klasse definierten Bindungen.Wenn Sie die für WS\-MetadataExchange verwendete Bindung konfigurieren möchten, müssen Sie einen Clientendpunkt in der Konfigurationsdatei für "Svcutil.exe" \(svcutil.exe.config\) definieren, der den `IMetadataExchange`\-Vertrag verwendet und über dasselbe URI\-Schema der Metadaten\-Endpunktadresse verfügt.  
  
> [!CAUTION]
>  Wenn "Svcutil.exe" zum Abrufen von Metadaten für einen Dienst ausgeführt wird, der zwei unterschiedliche Dienstverträge verfügbar macht, die jeweils eine Operation mit dem gleichen Namen enthalten, wird von "Svcutil.exe" eine Fehlermeldung darüber ausgegeben, dass keine Metadaten abgerufen werden können. Dies ist der Fall, wenn beispielsweise ein Dienst einen Dienstvertrag namens "ICarService" mit einer Get\(Car c\)\-Operation verfügbar macht und der gleiche Dienst einen Dienstvertrag namens "IBookService" mit einer Get\(Book b\)\-Operation verfügbar macht.Verwenden Sie eine der folgenden Vorgehensweisen, um dieses Problem zu umgehen:  
>   
>  -   Benennen Sie eine der Operationen um.  
> -   Legen Sie die <xref:System.ServiceModel.OperationContractAttribute.Name%2A>\-Eigenschaft auf einen anderen Namen fest.  
> -   Legen Sie einen der Namespaces der Operation mit der <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A>\-Eigenschaft auf einen anderen Namespace fest.  
  
### So laden Sie Metadaten mit "Svcutil.exe" herunter  
  
1.  Suchen Sie das Tool "Svcutil.exe" am folgenden Speicherort:  
  
     C:\\Programme\\Microsoft SDKs\\Windows\\v1.0.\\bin  
  
2.  Starten Sie das Tool an der Eingabeaufforderung mit dem folgenden Format.  
  
    ```  
    svcutil.exe /t:metadata  <url>* | <epr>  
    ```  
  
     Um Metadaten herunterzuladen, müssen Sie die `/t:metadata`\-Option angeben.Andernfalls werden Clientcode und \-konfiguration generiert.  
  
3.  Das \<`url`\>\-Argument gibt die URL zu einem Dienstendpunkt an, der Metadaten bereitstellt, oder zu einem Metadatendokument, das online gehostet wird.Das \<`epr`\>\-Argument gibt den Pfad zu einer XML\-Datei an, die eine WS\-Adressierung\-`EndpointAddress` für einen Dienstendpunkt enthält, der WS\-MetadataExchange unterstützt.  
  
 Weitere Möglichkeiten zur Verwendung dieses Tools zum Herunterladen von Metadaten finden Sie unter [ServiceModel Metadata Utility\-Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).  
  
## Beispiel  
 Der folgende Befehl lädt Metadatendokumente aus einem ausführenden Dienst herunter.  
  
```  
svcutil /t:metadata http://service/metadataEndpoint  
```  
  
## Siehe auch  
 [ServiceModel Metadata Utility\-Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)