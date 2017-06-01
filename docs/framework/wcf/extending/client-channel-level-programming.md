---
title: "Client-Kanalebenenprogrammierung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3b787719-4e77-4e77-96a6-5b15a11b995a
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Client-Kanalebenenprogrammierung
In diesem Thema wird das Schreiben einer [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Clientanwendung ohne Verwenden der <xref:System.ServiceModel.ClientBase%601?displayProperty=fullName>\-Klasse und der zugehörigen Objektmodelle beschrieben.  
  
## Senden von Nachrichten  
 Um für das Senden von Nachrichten und das Empfangen und Verarbeiten von Antworten bereit zu sein, sind die folgenden Schritte erforderlich:  
  
1.  Erstellen einer Bindung.  
  
2.  Erstellen einer Kanalfactory.  
  
3.  Erstellen eines Kanals.  
  
4.  Senden einer Anforderung und Lesen der Antwort.  
  
5.  Schließen Sie alle Kanalobjekte.  
  
#### Erstellen einer Bindung  
 Ähnlich wie beim Empfang \(siehe [Dienst\-Kanalebenenprogrammierung](../../../../docs/framework/wcf/extending/service-channel-level-programming.md)\) beginnt das Senden von Nachrichten mit der Erstellung einer Bindung.In diesem Beispiel wird eine neue <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=fullName> erstellt und ein <xref:System.ServiceModel.Channels.HttpTransportBindingElement?displayProperty=fullName> seiner Elementauflistung hinzugefügt.  
  
#### Erstellen einer ChannelFactory  
 Anstatt einen <xref:System.ServiceModel.Channels.IChannelListener?displayProperty=fullName> zu erstellen, wird hier eine <xref:System.ServiceModel.ChannelFactory%601?displayProperty=fullName> erstellt, indem <xref:System.ServiceModel.ChannelFactory.CreateFactory%2A?displayProperty=fullName> auf der Bindung aufgerufen wird, bei der der Typparameter <xref:System.ServiceModel.Channels.IRequestChannel?displayProperty=fullName> ist.Während die Kanallistener von der Seite verwendet werden, die auf eingehende Nachrichten wartet, werden Kanalfactorys von der Seite verwendet, die die Kommunikation für die Erstellung eines Kanals initiiert.Wie Kanallistener müssen auch Kanalfactorys zuerst geöffnet werden, bevor sie verwendet werden können.  
  
#### Erstellen eines Kanals  
 Wir rufen dann <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A?displayProperty=fullName> auf, um einen <xref:System.ServiceModel.Channels.IRequestChannel> zu erstellen.Dieser Aufruf nimmt die Adresse des Endpunkts, mit dem wir mithilfe des neu erstellten Kanals kommunizieren möchten.Nachdem wir einen Kanal haben, führen wir einen Öffnen\-Vorgang an diesem durch, um ihn in einen Bereitschaftsstatus für die Kommunikation zu versetzen.Abhängig von der Natur des Transports initiiert dieser Aufruf zum Öffnen möglicherweise eine Verbindung mit dem Zielendpunkt, oder es geschieht nichts auf dem Netzwerk.  
  
#### Senden einer Anforderung und Lesen der Antwort  
 Nachdem wir einen offenen Kanal erhalten haben, können wir eine Nachricht erstellen und die Anforderungsmethode des Kanals nutzen, um die Anforderung zu senden und dann auf die Zustellung der Antwort zu warten.Wird diese Methode zurückgegeben, verfügen wir über eine Antwortnachricht, die wir lesen können, um die Antwort des Endpunkts herauszufinden.  
  
#### Schließen von Objekten  
 Um Ressourcenverluste zu vermeiden, schließen wir in Kommunikationsvorgängen verwendete Objekte, wenn sie nicht mehr benötigt werden.  
  
 Das folgende Codebeispiel zeigt einen grundlegenden Client, der die Kanalfactory zum Senden einer Nachricht und zum Lesen der Antwort verwendet.  
  
 [!code-csharp[ChannelProgrammingBasic#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/channelprogrammingbasic/cs/clientprogram.cs#2)]
 [!code-vb[ChannelProgrammingBasic#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/channelprogrammingbasic/vb/clientprogram.vb#2)]