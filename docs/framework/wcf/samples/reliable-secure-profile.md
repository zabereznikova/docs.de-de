---
title: "Reliable Secure Profile | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 921edc41-e91b-40f9-bde9-b6148b633e61
caps.latest.revision: 8
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 8
---
# Reliable Secure Profile
In diesem Beispiel wird veranschaulicht, wie [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] und [Reliable Secure Profile](http://go.microsoft.com/fwlink/?LinkId=178140) \(RSP\) verfasst wird.In diesem Beispiel wird die Implementierung eines [Make Connection](http://go.microsoft.com/fwlink/?LinkId=178141)\-Kanals veranschaulicht, der zusammen mit zuverlässigem Messaging und optional einem sicheren Kanal verfasst werden kann, um eine zuverlässige sichere Bindung auf Grundlage der RSP\-Spezifikation zu erstellen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\ReliableSecureProfile`  
  
## Diskussion  
 In diesem Beispiel wird ein zuverlässiges asynchrones, bidirektionales Nachrichtenaustauschszenario veranschaulicht.Der Dienst verfügt über einen Duplexvertrag, und der Client implementiert den Duplexrückrufvertrag.Der Client initiiert eine Anforderung an einen Dienst, für den eine Antwort für eine separate Verbindung erwartet wird.Die Anforderungsmeldung wird zuverlässig gesendet.Der Client möchte selbst keinen überwachenden Endpunkt öffnen.Deshalb sendet er eine Abfrage an den Dienst mit 'Make Connection'\-Anforderungen, damit die Antwort auf dem Rückkanal dieser 'Make Connection'\-Anforderung zurückgesendet werden soll.In diesem Beispiel wird veranschaulicht die sichere zuverlässige Duplexkommunikation über HTTP, ohne dass der Client einen überwachenden Endpunkt verfügbar machen muss oder eine Firewallausnahme erstellt werden soll.  
  
## So richten Sie das Beispiel ein, erstellen es und führen es aus  
  
1.  Öffnen Sie die Projektmappe **ReliableSecureProfile**.  
  
2.  Klicken Sie mit der rechten Maustaste unter **Projektmappen\-Explorer** auf das Projekt **Dienst**, und wählen Sie aus dem Kontextmenü **Debuggen**, **Neue Instanz starten** aus.Daraufhin wird der Diensthost gestartet.  
  
3.  Klicken Sie mit der rechten Maustaste unter **Projektmappen\-Explorer** auf das Projekt **Client**, und wählen Sie aus dem Kontextmenü **Debuggen**, **Neue Instanz starten** aus.Daraufhin wird der Client gestartet.  
  
4.  Geben Sie eine beliebige Zeichenfolge in die Eingabeaufforderung im Clientkonsolenfenster ein, und drücken Sie die EINGABETASTE. Daraufhin wird die Eingabezeichenfolge an den Dienst gesendet, und dieser berechnet einen Hash der Zeichenfolge.  
  
5.  Zeigen Sie das Ergebnis in den Clientfenstern an, wenn der Vorgang mit dem Duplexrückrufvertrag vom Dienst zurückgerufen wird, um das Ergebnis im Clientkonsolenfenster anzuzeigen.Es gibt eine absichtliche Verzögerung im Dienst, um einen lange andauernden Ausführungsvorgang zur Datenverarbeitung zu simulieren.  
  
6.  Die Überwachung des HTTP\-Datenverkehrs \(durch ein Online\-Netzwerküberwachungstool wie Network Monitor, Fiddler usw.\) zeigt an, dass eine Sequenz für die Kommunikation zwischen dem Client und dem Dienst gemäß dem Vorbild des Reliable Secure Profile erstellt wird, und demonstriert, wie der Client 'Make Connection'\-Anforderungen als Abfragen an den Dienst sendet.Wenn der Dienst sich darauf vorbereitet, die die verarbeitete Antwort zurückzusenden, sendet es die Ergebnisse über den Rückkanal der letzten 'Make Connection'\-Anforderung zurück.  
  
7.  Drücken Sie im Dienstkonsolenfenster die EINGABETASTE, um den Dienst zu schließen.Drücken Sie im Clientkonsolenfenster die EINGABETASTE, um den Client zu schließen.