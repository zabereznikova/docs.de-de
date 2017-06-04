---
title: "Zugreifen auf den Dienst in einem Webbrowser (WCF Data Services-Schnellstart) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5a6fa180-3094-4e6e-ba2b-8c80975d18d1
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# Zugreifen auf den Dienst in einem Webbrowser (WCF Data Services-Schnellstart)
In dieser Aufgabe starten Sie [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] aus [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] und deaktivieren optional das Lesen von Feeds im Webbrowser.  Sie rufen dann das Dienstdefinitionsdokument ab und greifen auf Datendienstressourcen zu, indem Sie HTTP GET\-Anforderungen über einen Webbrowser an die verfügbar gemachten Ressourcen senden.  
  
> [!NOTE]
>  Standardmäßig weist [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] dem `localhost`\-URI auf dem Computer automatisch eine Portnummer zu.  Für diese Aufgabe wird in den URI\-Beispielen die Portnummer `12345` verwendet.  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] zum Festlegen einer bestimmten Portnummer im [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]\-Projekt finden Sie unter [Erstellen des Datendiensts](../../../../docs/framework/data/wcf/creating-the-data-service.md).  
  
### So fordern Sie das Standarddienstdokument mithilfe von Internet Explorer an  
  
1.  Wählen Sie in Internet Explorer im Menü **Extras** die Option **Internetoptionen** aus, klicken Sie auf die Registerkarte **Inhalt**, klicken Sie auf **Einstellungen**, und deaktivieren Sie **Feedleseanzeige einschalten**.  
  
     Dadurch wird sichergestellt, dass das Lesen von Feeds deaktiviert ist.  Wenn Sie diese Funktionalität nicht deaktivieren, behandelt der Webbrowser das zurückgegebene AtomPub\-codierte Dokument als XML\-Feed, statt die unformatierten XML\-Daten anzuzeigen.  
  
    > [!NOTE]
    >  Wenn der Browser den Feed nicht als unformatierte XML\-Daten anzeigen kann, sollten es dennoch möglich sein, den Feed als Quellcode der Seite anzuzeigen.  
  
2.  Drücken Sie in [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] die F5\-TASTE, um die Anwendung zu debuggen.  
  
3.  Öffnen Sie auf dem lokalen Computer einen Webbrowser.  Geben Sie in der Adressleiste den folgenden URI ein:  
  
    ```  
    http://localhost:12345/northwind.svc  
    ```  
  
     Dadurch wird das Standarddienstdokument zurückgegeben, das eine Liste von Entitätenmengen enthält, die von diesem Datendienst verfügbar gemacht werden.  
  
### So greifen Sie auf Entitätenmengenressourcen in einem Webbrowser zu  
  
1.  Geben Sie in der Adressleiste des Webbrowsers den folgenden URI ein:  
  
    ```  
    http://localhost:12345/northwind.svc/Customers  
    ```  
  
     Dadurch wird ein Satz aller Kunden in der Northwind\-Beispieldatenbank zurückgegeben.  
  
2.  Geben Sie in der Adressleiste des Webbrowsers den folgenden URI ein:  
  
    ```  
    http://localhost:12345/northwind.svc/Customers('ALFKI')  
    ```  
  
     Dadurch wird eine Entitätsinstanz für einen bestimmten Kunden, `ALFKI`, zurückgegeben.  
  
3.  Geben Sie in der Adressleiste des Webbrowsers den folgenden URI ein:  
  
    ```  
    http://localhost:12345/northwind.svc/Customers('ALFKI')/Orders  
    ```  
  
     Dadurch wird die Beziehung zwischen Kunden und Bestellungen durchlaufen, um einen Satz aller Bestellungen für den Kunden `ALFKI` zurückzugeben.  
  
4.  Geben Sie in der Adressleiste des Webbrowsers den folgenden URI ein:  
  
    ```  
    http://localhost:12345/northwind.svc/Customers('ALFKI')/Orders?$filter=OrderID eq 10643  
    ```  
  
     Dadurch werden Bestellungen gefiltert, die zum Kunden `ALFKI` gehören, sodass auf der Grundlage des angegebenen `OrderID`\-Werts nur eine bestimmte Bestellung zurückgegeben wird.  
  
## Nächste Schritte  
 Sie haben erfolgreich in einem Webbrowser auf [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] zugegriffen, wobei der Browser HTTP GET\-Anforderungen an angegebene Ressourcen ausgegeben hat.  Mithilfe eines Webbrowsers können Sie leicht mit der Adressierungssyntax von Anforderungen experimentieren und die Ergebnisse anzeigen.  Auf einen Produktionsdatendienst wird jedoch im Allgemeinen nicht mit dieser Methode zugegriffen.  In der Regel interagieren Anwendungen über Anwendungscode oder Skriptsprachen mit dem Datendienst. Als Nächstes erstellen Sie eine Clientanwendung, die Clientbibliotheken verwendet, um auf Datendienstressourcen wie auf CLR \(Common Language Runtime\)\-Objekte zuzugreifen:  
  
 [Erstellen der .NET Framework\-Clientanwendung](../../../../docs/framework/data/wcf/creating-the-dotnet-client-application-wcf-data-services-quickstart.md)  
  
## Siehe auch  
 [Zugreifen auf Datendienstressourcen](../../../../docs/framework/data/wcf/accessing-data-service-resources-wcf-data-services.md)