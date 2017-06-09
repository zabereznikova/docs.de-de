---
title: "Erweiterte Formatauswahl | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e02d9082-4d55-41d8-9329-98f6d1c77f06
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# Erweiterte Formatauswahl
In diesem Beispiel wird veranschaulicht, wie das [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-REST\-Programmiermodell zur Unterstützung neuer Formate für ausgehende Antworten erweitert wird.  In diesem Beispiel wird zusätzlich eine T4\-Vorlage verwendet, damit die Antwort als XHTML\-Seite zurückgegeben wird. Auf diese Weise wird veranschaulicht, wie ein Programmiermodell zur Ansicht implementiert werden kann.  
  
## Beispieldetails  
 Das Beispiel besteht aus einem einfachen Dienst und Clientcode, mit dem Anforderungen an den Dienst gesendet werden.  Der Dienst unterstützt einen einzelnen \[WebGet\-\]Vorgang mit der folgenden Methodensignatur: `Message EchoListWithGet(string list);`  
  
 Wenn der Client eine Anforderung an den Dienst sendet, stellt er eine durch Trennzeichen getrennte Liste der Elemente aus dem `list`\-Abfragezeichenfolgenparameter bereit. Der Dienst gibt diese gleiche Liste in einem der folgenden Formate XML, JSON, Atom, XHTML oder JPEG zurück.  
  
 Das vom Dienst zurückgegebene Antwortformat wird von einem `format`\-Abfragezeichenfolgenparameter und zusätzlich von einem mit der Anforderung angegebenen HTTP Accept\-Header bestimmt.  Wenn der Wert des `format`\-Abfragezeichenfolgenparameters einem der vorangehenden Formate entspricht, wird die Antwort im entsprechenden Format zurückgegeben.  Wenn die `format`\-Abfragezeichenfolge nicht vorhanden ist, durchläuft der Dienst die Accept\-Headerelemente der Anforderung und gibt das Format des ersten Inhaltstyp zurück, den der Dienst unterstützt.  
  
 Beim Rückgabetyp des Vorgangs ist Folgendes zu beachten.  Das [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-REST\-Programmiermodell unterstützt XML\- und JSON\-Antwortformate systemintern nur dann, wenn ein Vorgang einen anderen Typ als <xref:System.ServiceModel.Channels.Message> zurückgibt.  Wenn als Rückgabetyp jedoch <xref:System.ServiceModel.Channels.Message> verwendet wird, kann der Entwickler vollständig selbst bestimmen, wie der Inhalt der Meldung formatiert werden soll.  
  
 In diesem Beispiel wird die Liste der Zeichenfolgen mithilfe der Methoden <xref:System.ServiceModel.Web.WebOperationContext.CreateXmlResponse%2A>, <xref:System.ServiceModel.Web.WebOperationContext.CreateJsonResponse%2A> und <xref:System.ServiceModel.Web.WebOperationContext.CreateAtom10Response%2A> in entsprechende XML\-, JSON\- und ATOM\-Meldungen serialisiert.  Für das JPEG\-Antwortformat wird die <xref:System.ServiceModel.Web.WebOperationContext.CreateStreamResponse%2A>\-Methode verwendet, und das Bild wird im Stream gespeichert.  Für die XHTML\-Antwort wird die <xref:System.ServiceModel.Web.WebOperationContext.CreateTextResponse%2A> mit einer zuvor verarbeiteten T4\-Vorlage verwendet. Diese besteht aus einer TT\-Datei und einer automatisch generierten CS\-Datei.  Die TT\-Datei ermöglicht es Entwicklern, eine Antwort in ein Vorlagenformular zu schreiben, das Variablen und Steuerelementstrukturen enthält.  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] zu T4 finden Sie unter [Generieren von Artefakten mithilfe von Textvorlagen](http://go.microsoft.com/fwlink/?LinkId=166023).  
  
 Das Beispiel umfasst einen selbst gehosteten Dienst und einen Client, der in einer Konsolenanwendung ausgeführt wird.  Während die Konsolenanwendung ausgeführt wird, sendet der Client Anforderungen an den Dienst und schreibt die in den Antworten enthaltenen wichtigen Informationen in das Konsolenfenster.  
  
#### So führen Sie dieses Beispiel aus  
  
1.  Öffnen Sie die Projektmappe für das Beispiel zur erweiterten Formatauswahl.  Sie müssen [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] als Administrator ausführen, damit das Beispiel erfolgreich ausgeführt werden kann.  Klicken Sie dazu mit der rechten Maustaste auf das [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]\-Symbol, und wählen Sie im Kontextmenü die Option **Als Administrator ausführen** aus.  
  
2.  Drücken Sie STRG\+UMSCHALT\+B, um die Projektmappe zu erstellen, und dann STRG\+F5, um das AdvancedFormatSelection\-Projekt der Konsolenanwendung ohne Debuggen auszuführen.  Im eingeblendeten Konsolenfenster werden der URI des ausgeführten Diensts und der URI der HTML\-Hilfeseite für den ausgeführten Dienst angezeigt.  
  
3.  Während das Beispiel ausgeführt wird, sendet der Client Anforderungen an den Dienst und schreibt die Antworten in das Konsolenfenster.  Beachten Sie die anderen Formate der Antworten: XML, JSON, Atom und XHTML.  
  
4.  Sie werden daraufhin aufgefordert, zu einem URI zu wechseln, in dem Sie die Antwort im JPEG\-Format anfordern können.  Öffnen Sie einen Browser, und wechseln Sie zum angegebenen URI.  
  
5.  Drücken Sie eine beliebige Taste, um das Beispiel zu beenden.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.  Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.  Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples\WCF\Basic\Web\AdvancedFormatSelection`  
  
## Siehe auch