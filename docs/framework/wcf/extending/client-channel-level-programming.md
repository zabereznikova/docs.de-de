---
title: Client-Kanalebenenprogrammierung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3b787719-4e77-4e77-96a6-5b15a11b995a
ms.openlocfilehash: 4f24c558b1d5303b2417416beb14555539f498ea
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70797270"
---
# <a name="client-channel-level-programming"></a>Client-Kanalebenenprogrammierung
In diesem Thema wird beschrieben, wie Sie eine Windows Communication Foundation (WCF)-Client Anwendung <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType> schreiben, ohne die-Klasse und das zugehörige-Objektmodell zu verwenden.  
  
## <a name="sending-messages"></a>Senden von Nachrichten  
 Um für das Senden von Nachrichten und das Empfangen und Verarbeiten von Antworten bereit zu sein, sind die folgenden Schritte erforderlich:  
  
1. Erstellen Sie eine Bindung.  
  
2. Erstellen einer Kanalfactory.  
  
3. Erstellen eines Kanals.  
  
4. Senden einer Anforderung und Lesen der Antwort.  
  
5. Schließen Sie alle Kanalobjekte.  
  
#### <a name="creating-a-binding"></a>Erstellen einer Bindung  
 Vergleichbar mit dem empfangenden Fall (siehe [Programmieren auf Dienst Kanal Ebene](service-channel-level-programming.md)), wird das Senden von Nachrichten gestartet, indem eine Bindung erstellt wird. In diesem Beispiel wird eine neue <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType> erstellt und ein <xref:System.ServiceModel.Channels.HttpTransportBindingElement?displayProperty=nameWithType> seiner Elementauflistung hinzugefügt.  
  
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
