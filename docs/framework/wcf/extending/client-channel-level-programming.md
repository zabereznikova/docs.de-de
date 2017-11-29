---
title: Client-Kanalebenenprogrammierung
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 3b787719-4e77-4e77-96a6-5b15a11b995a
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a6ffe482c8d04314b79ee5bb7029d2583c56c363
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="client-channel-level-programming"></a>Client-Kanalebenenprogrammierung
In diesem Thema wird das Schreiben einer [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Clientanwendung ohne Verwenden der <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType>-Klasse und der zugehörigen Objektmodelle beschrieben.  
  
## <a name="sending-messages"></a>Senden von Nachrichten  
 Um für das Senden von Nachrichten und das Empfangen und Verarbeiten von Antworten bereit zu sein, sind die folgenden Schritte erforderlich:  
  
1.  Erstellen Sie eine Bindung.  
  
2.  Erstellen einer Kanalfactory.  
  
3.  Erstellen eines Kanals.  
  
4.  Senden einer Anforderung und Lesen der Antwort.  
  
5.  Schließen Sie alle Kanalobjekte.  
  
#### <a name="creating-a-binding"></a>Erstellen einer Bindung  
 Ähnlich wie beim empfangenden Fall (finden Sie unter [Programmierung auf Kanalebene Service](../../../../docs/framework/wcf/extending/service-channel-level-programming.md)), das Senden von Nachrichten beginnt durch Erstellen einer Bindung. In diesem Beispiel wird eine neue <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType> erstellt und ein <xref:System.ServiceModel.Channels.HttpTransportBindingElement?displayProperty=nameWithType> seiner Elementauflistung hinzugefügt.  
  
#### <a name="building-a-channelfactory"></a>Erstellen einer ChannelFactory  
 Anstatt einen <xref:System.ServiceModel.Channels.IChannelListener?displayProperty=nameWithType> zu erstellen, wird hier eine <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType> erstellt, indem <xref:System.ServiceModel.ChannelFactory.CreateFactory%2A?displayProperty=nameWithType> auf der Bindung aufgerufen wird, bei der der Typparameter <xref:System.ServiceModel.Channels.IRequestChannel?displayProperty=nameWithType> ist. Während die Kanallistener von der Seite verwendet werden, die auf eingehende Nachrichten wartet, werden Kanalfactorys von der Seite verwendet, die die Kommunikation für die Erstellung eines Kanals initiiert. Wie Kanallistener müssen auch Kanalfactorys zuerst geöffnet werden, bevor sie verwendet werden können.  
  
#### <a name="creating-a-channel"></a>Erstellen eines Kanals  
 Wir rufen dann <xref:System.ServiceModel.ChannelFactory%601.CreateChannel%2A?displayProperty=nameWithType> auf, um einen <xref:System.ServiceModel.Channels.IRequestChannel> zu erstellen. Dieser Aufruf nimmt die Adresse des Endpunkts, mit dem wir mithilfe des neu erstellten Kanals kommunizieren möchten. Nachdem wir einen Kanal haben, führen wir einen Öffnen-Vorgang an diesem durch, um ihn in einen Bereitschaftsstatus für die Kommunikation zu versetzen. Abhängig von der Natur des Transports initiiert dieser Aufruf zum Öffnen möglicherweise eine Verbindung mit dem Zielendpunkt, oder es geschieht nichts auf dem Netzwerk.  
  
#### <a name="sending-a-request-and-reading-the-reply"></a>Senden einer Anforderung und Lesen der Antwort  
 Nachdem wir einen offenen Kanal erhalten haben, können wir eine Nachricht erstellen und die Anforderungsmethode des Kanals nutzen, um die Anforderung zu senden und dann auf die Zustellung der Antwort zu warten. Wird diese Methode zurückgegeben, verfügen wir über eine Antwortnachricht, die wir lesen können, um die Antwort des Endpunkts herauszufinden.  
  
#### <a name="closing-objects"></a>Schließen von Objekten  
 Um Ressourcenverluste zu vermeiden, schließen wir in Kommunikationsvorgängen verwendete Objekte, wenn sie nicht mehr benötigt werden.  
  
 Das folgende Codebeispiel zeigt einen grundlegenden Client, der die Kanalfactory zum Senden einer Nachricht und zum Lesen der Antwort verwendet.  
  
 [!code-csharp[ChannelProgrammingBasic#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/channelprogrammingbasic/cs/clientprogram.cs#2)]
 [!code-vb[ChannelProgrammingBasic#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/channelprogrammingbasic/vb/clientprogram.vb#2)]
