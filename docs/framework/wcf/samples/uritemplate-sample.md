---
title: "UriTemplate-Beispiel | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0aaf91d0-ce18-468d-8006-bc9bc2e48231
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# UriTemplate-Beispiel
Die <xref:System.UriTemplate>\-Klasse stellt Methoden zum Arbeiten mit Sätzen von URIs bereit, die eine gemeinsame Struktur verwenden.In diesem Beispiel werden die folgenden Schlüsselkonzepte für die `UriTemplate`\-Klasse veranschaulicht:  
  
-   Syntax zum Erstellen von Vorlagen.  
  
-   Instanziieren von URIs aus einer `UriTemplate` mit <xref:System.UriTemplate.BindByName%2A> und <xref:System.UriTemplate.BindByPosition%2A>.  
  
-   <xref:System.UriTemplateTable.Match%2A>. Dies ist die Umkehroperation zu `BindByName` und `BindByPosition`.  
  
### So richten Sie das Beispiel ein, erstellen es und führen es aus  
  
1.  Zum Erstellen der C\#\- oder Visual Basic .NET\-Edition der Projektmappe befolgen Sie die unter [Erstellen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md) aufgeführten Anweisungen.  
  
2.  Um das Beispiel in einer Konfiguration mit einem Computer oder computerübergreifend auszuführen, befolgen Sie die Anweisungen unter [Durchführen der Windows Communication Foundation\-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\UriTemplate`  
  
## Siehe auch  
 [UriTemplate\-Tabelle](../../../../docs/framework/wcf/samples/uritemplate-table-sample.md)   
 [UriTemplate\-Tabellenverteiler](../../../../docs/framework/wcf/samples/uritemplate-table-dispatcher-sample.md)