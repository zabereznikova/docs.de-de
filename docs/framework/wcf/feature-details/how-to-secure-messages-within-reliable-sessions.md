---
title: "Vorgehensweise: Sch&#252;tzen von Nachrichten innerhalb einer zuverl&#228;ssigen Sitzung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: aee33e50-936f-4486-9ca8-c1520c19a62d
caps.latest.revision: 8
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 8
---
# Vorgehensweise: Sch&#252;tzen von Nachrichten innerhalb einer zuverl&#228;ssigen Sitzung
Dieses Thema enthält einen Überblick über die Schritte zum Aktivieren der Sicherheit auf Nachrichtenebene für den Nachrichtenaustausch innerhalb einer zuverlässigen Sitzung mithilfe einer der vom System bereitgestellten Bindungen, die eine solche Sitzung zwar unterstützen, standardmäßig aber keine Unterstützung dafür bieten.Eine sichere, zuverlässige Sitzung können Sie entweder verbindlich durch Verwenden von Code oder deklarativ in der Konfigurationsdatei aktivieren.Dieses Verfahren verwendet die Konfigurationsdateien von Client und Dienst, um die sichere, zuverlässige Sitzung zu aktivieren.  
  
 Dieses Verfahren besteht aus den folgenden drei Hauptaufgaben:  
  
1.  Angeben, dass der Client und der Dienst Nachrichten in einer zuverlässigen Sitzung austauschen.  
  
2.  Anfordern der Sicherheit auf Nachrichtenebene innerhalb der zuverlässigen Sitzung.  
  
3.  Angeben des Clientanmeldeinformationstyps, den der Client verwenden muss, um sich selbst beim Server authentifizieren zu können.  
  
 Der wesentliche Punkt der ersten Aufgabe besteht darin, dass das Element zur Endpunktkonfiguration ein `bindingConfiguration`\-Attribut enthält, das auf eine Bindungskonfiguration namens \(in diesem Beispiel\) "MessageSecurity" verweist. Das [\<Bindung\>](../../../../docs/framework/misc/binding.md)`enabled-Konfigurationselement kann dann zum Aktivieren zuverlässiger Sitzungen auf diesen Namen verweisen, indem es das` [reliableSession\-Attribut des](http://msdn.microsoft.com/de-de/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b)`true-Elements auf`  festlegt.Sie können angeben, dass eine Zusicherung der Zustellung in der richtigen Reihenfolge innerhalb einer zuverlässigen Sitzung verfügbar ist, indem Sie das `ordered`\-Attribut auf `true` festlegen.  
  
 Die Quellkopie des Beispiels, auf dem dieses Konfigurationsverfahren basiert, finden Sie unter [Zuverlässige WS\-Sitzung](../../../../docs/framework/wcf/samples/ws-reliable-session.md).  
  
 Die wesentlichen Punkte der zweiten Aufgabe werden erreicht, indem Sie das `mode`\-Attribut des im \<`binding`\>\-Element des Clients und des Diensts enthaltenen \<`security`\>\-Elements auf `Message` festlegen.  
  
 Die wesentlichen Punkte der dritten Aufgabe werden erreicht, indem Sie das `clientCredentialType`\-Attribut des im \<`security`\>\-Element des Clients und des Diensts enthaltenen \<`message`\>\-Elements auf `Certificate` festlegen.  
  
> [!NOTE]
>  Wenn Sie Nachrichtensicherheit zusammen mit zuverlässigen Sitzungen verwenden, und der Client ist nicht authentifiziert, versucht das zuverlässiges Messaging, den Client so lange zu authentifizieren, bis ein Timeout auftritt, statt nach dem ersten Fehlschlag eine Ausnahme auszulösen.  
  
### So konfigurieren Sie den Dienst mit WSHttpBinding zur Verwendung einer zuverlässigen Sitzung  
  
1.  Dieses Verfahren wird unter [Vorgehensweise: Austauschen von Nachrichten innerhalb einer zuverlässigen Sitzung](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md) beschrieben.  
  
### So konfigurieren Sie den Client mit WSHttpBinding zur Verwendung einer zuverlässigen Sitzung  
  
1.  Dieses Verfahren wird unter [Vorgehensweise: Austauschen von Nachrichten innerhalb einer zuverlässigen Sitzung](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-within-a-reliable-session.md) beschrieben.  
  
### So legen Sie den Modus und den ClientCredentialType in der Konfiguration fest  
  
1.  Fügen Sie dem [\<Bindungen\>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)\-Element der Konfigurationsdatei ein entsprechendes Bindungselement hinzu.Im folgenden Beispiel wird ein [\<wsHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)\-Element hinzugefügt.  
  
2.  Fügen Sie ein \<`binding`\>\-Element hinzu, und legen Sie das `name`\-Attribut auf einen geeigneten Wert fest.  
  
3.  Fügen Sie ein `<security>``mode-Element hinzu, und legen Sie das` `Message-Attribut auf`  fest.  
  
     Im folgenden Beispiel wird der Modus auf `Message` festgelegt, und anschließend wird das `clientCredentialType`\-Attribut des \<`message`\>\-Elements auf `Certificate` festgelegt.  
  
    ```  
    <wsHttpBinding>  
    <binding name="MessageSecurity">  
        <security mode="Message" />  
           <message clientCredentialType = " Certificate" />  
        </security>  
    </binding>  
    </wsHttpBinding >  
    ```