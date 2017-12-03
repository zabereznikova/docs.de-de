---
title: Dienstendpunkte und Adressieren von Warteschlangen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7d2d59d7-f08b-44ed-bd31-913908b83d97
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b2c8b85c2920133e21e7659ca0c27e28ab4a8eae
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="service-endpoints-and-queue-addressing"></a>Dienstendpunkte und Adressieren von Warteschlangen
In diesem Thema wird erläutert, wie Clients Dienste adressieren, die Daten aus Warteschlangen auslesen, und wie Dienstendpunkte Warteschlangen zugeordnet werden. Zur Erinnerung stellt die folgende Abbildung die klassische Bereitstellung von Anwendungen in der Warteschlange von [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] dar.  
  
 ![In der Warteschlange Anwendungsdiagramm](../../../../docs/framework/wcf/feature-details/media/distributed-queue-figure.jpg "Distributed-Warteschlange-Abbildung")  
  
 Damit der Client die Nachricht an den Dienst senden kann, richtet der Client die Nachricht an die Zielwarteschlange. Damit der Dienst Nachrichten aus der Warteschlange lesen kann, legt er als Abhöradresse die Zielwarteschlange fest. Die Adressierung in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] erfolgt Uniform Resource Identifier- (URI-)basiert, während die Warteschlangennamen für Message Queuing (MSMQ) nicht URI-basiert sind. Sie müssen sich deshalb damit vertraut machen, wie Warteschlangen adressiert werden, die in MSMQ mithilfe von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] erstellt worden sind.  
  
## <a name="msmq-addressing"></a>MSMQ-Adressierung  
 MSMQ verwendet Pfade und Formatnamen, um eine Warteschlange zu identifizieren. Pfade geben einen Hostnamen und einen `QueueName` an. Optional kann ein `Private$` zwischen dem Hostnamen und dem `QueueName` vorliegen, um eine private Warteschlange anzugeben, die nicht im Active Directory-Verzeichnisdienst veröffentlicht wird.  
  
 Pfadnamen werden "Formatnames zugeordnet des", um zusätzliche Aspekte der Adresse, einschließlich routing und Warteschlangen-Manager-Übertragungsprotokoll zu bestimmen, zugeordnet. Der Warteschlangen-Manager unterstützt zwei Übertragungsprotokolle: das systemeigene MSMQ-Protokoll und das SOAP Reliable Messaging Protocol (SRMP).  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]MSMQ-Pfad und den Format-Namen, finden Sie unter [zu Message Queuing](http://go.microsoft.com/fwlink/?LinkId=94837).  
  
## <a name="netmsmqbinding-and-service-addressing"></a>NetMsmqBinding und Dienstadressierung  
 Bei der Adressierung einer Nachricht an einen Dienst wird das Schema in dem URI anhand des für die Kommunikation verwendeten Transports ausgewählt. Jeder Transport in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verfügt über ein eindeutiges Schema. Das Schema muss die Art des für die Kommunikation verwendeten Transports wiedergeben, z. B. net.tcp, net.pipe, HTTP usw.  
  
 Der MSMQ-Warteschlangentransport in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] macht ein net.msmq-Schema verfügbar. Alle Nachrichten, die mithilfe des net.msmq-Schemas adressiert werden, werden mithilfe von `NetMsmqBinding` über den MSMQ-Warteschlangen-Transportkanal gesendet.  
  
 Die Adressierung einer Warteschlange in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] basiert auf dem folgenden Muster:  
  
 NET.MSMQ: / / \< *Hostname*> / [private /] \< *Queue-Name*>  
  
 Dabei gilt:  
  
-   \<*Hostname*> ist der Name des Computers, der die Zielwarteschlange hostet.  
  
-   [privat] ist optional. Dies wird verwendet, wenn eine Zielwarteschlange adressiert wird, bei der es sich um eine private Warteschlange handelt. Um eine öffentliche Warteschlange zu adressieren, dürfen Sie nicht "privat" angeben. Beachten Sie, dass es, anders als bei MSMQ-Pfaden, im [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-URI-Formular kein "$" gibt.  
  
-   \<*Warteschlangenname*> ist der Name der Warteschlange. Der Warteschlangenname kann auch auf eine Unterwarteschlange verweisen. Folglich \< *Warteschlangenname*> = \< *Name-of-Queue*> [; *Sub-queue-Name*].  
  
 Beispiel1: Für die Adressierung einer privaten Warteschlange PurchaseOrders, die auf dem Computer abc atadatum.com gehostet wird, wäre der URI net.msmq://abc.adatum.com/private/PurchaseOrders.  
  
 Beispiel2: Für die Adressierung einer öffentlichen Warteschlange AccountsPayable, die auf dem Computer def atadatum.com gehostet wird, wäre der URI net.msmq://def.adatum.com/AccountsPayable.  
  
 Die Warteschlangenadresse wird vom Listener als Abhör-URI zum Lesen von Nachrichten verwendet. Mit anderen Worten, die Warteschlangenadresse entspricht dem Abhöranschluss des TCP-Sockets.  
  
 Ein Endpunkt, der aus einer Warteschlange liest, muss die Adresse der Warteschlange nach demselben Schema angeben, das zuvor beim Öffnen des ServiceHost angegeben worden war. Beispiele finden Sie unter [Net MSMQ-Bindung](../../../../docs/framework/wcf/samples/net-msmq-binding.md) und [Message Queuing-Integration binden Samples](http://msdn.microsoft.com/en-us/997d11cb-f2c5-4ba0-9209-92843d4d0e1a).  
  
### <a name="multiple-contracts-in-a-queue"></a>Mehrere Verträge in einer Warteschlange  
 Nachrichten in einer Warteschlange können verschiedene Verträge implementieren. In diesem Fall muss eines der folgenden Szenarien zutreffen, um alle Nachrichten erfolgreich lesen und verarbeiten zu können:  
  
-   Geben Sie einen Endpunkt für einen Dienst an, der alle Verträge implementiert. Dies ist die empfohlene Vorgehensweise.  
  
-   Geben Sie mehrere Endpunkte mit verschiedenen Verträgen an, stellen Sie jedoch sicher, dass alle Endpunkte das gleiche `NetMsmqBinding`-Objekt verwenden. Die Dispatchlogik in ServiceModel verwendet ein Nachrichtensystem, das Nachrichten aus dem Transportkanal für den Dispatch ausliest, der schließlich für die Nachrichten auf der Grundlage des Vertrags ein De-Multiplexing mit anderen Endpunkten ausführt. Es wird ein Nachrichtensystem für ein Abhör-URI-/Bindungspaar erstellt. Die Warteschlangenadresse wird von dem Warteschlangenlistener als Abhör-URI verwendet. Da alle Endpunkte dasselbe Bindungsobjekt verwenden, wird sichergestellt, dass ein einziges Nachrichtensystem zum Lesen der Nachricht und zum Ausführen von De-Multiplexing für relevante Endpunkte auf der Grundlage des Vertrags verwendet wird.  
  
### <a name="srmp-messaging"></a>SRMP-Messaging  
 Wie zuvor erläutert, können Sie das SRMP-Protokoll für Übertragungen zwischen Warteschlangen einsetzen. Dies wird häufig angewendet, wenn ein HTTP-Transport Nachrichten zwischen der Übertragungswarteschlange und der Zielwarteschlange sendet.  
  
 Um das SRMP-Übertragungsprotokoll zu verwenden, adressieren Sie Nachrichten mithilfe des net.msmq-URI-Schemas, wie zuvor erwähnt, und geben Sie Ihre Wahl zwischen SRMP oder sicherem SRMP in der `QueueTransferProtocol`-Eigenschaft der `NetMsmqBinding` an.  
  
 Das Angeben der `QueueTransferProtocol`-Eigenschaft wirkt sich nur auf das Senden aus. Dadurch gibt der Client an, welche Art von Warteschlangenübertragungsprotokoll verwendet werden soll.  
  
### <a name="using-active-directory"></a>Using Active Directory  
 MSMQ wird mit Unterstützung für Active Directory-Integration geliefert. Wenn MSMQ mit Active Directory-Integration installiert wird, muss der Computer Teil einer Windows-Domäne sein. Active Directory verwendet wird, um Warteschlangen für die Erkennung zu veröffentlichen. Diese Warteschlangen heißen *öffentliche Warteschlangen*. Wenn Sie eine Warteschlange adressieren, kann die Warteschlange mit Active Directory aufgelöst werden. Dies funktioniert auf ähnliche Weise wie bei der Verwendung des DNS-Systems (Domain Name System) für die Auflösung einer IP-Adresse eines Netzwerknamens. Die `UseActiveDirectory`-Eigenschaft in der `NetMsmqBinding` ist ein boolescher Wert, der angibt, ob der in der Warteschlange stehende Kanal Active Directory verwenden muss, um den URI der Warteschlange aufzulösen. In der Standardeinstellung ist die Eigenschaft auf `false` festgelegt. Wenn die `UseActiveDirectory`-Eigenschaft als `true` angegeben wird, verwendet der in der Warteschlange stehende Kanal Active Directory zum Umwandeln des net.msmq://-URI in den Formatnamen.  
  
 Die `UseActiveDirectory`-Eigenschaft hat nur für den Client Bedeutung, der die Nachricht sendet, da sie beim Senden von Nachrichten zur Auflösung der Adresse der Warteschlange verwendet wird.  
  
### <a name="mapping-netmsmq-uri-to-message-queuing-format-names"></a>Zuordnen des net.msmq-URI zu Message Queuing-Formatnamen  
 Der in der Warteschlange stehende Kanal verarbeitet die Zuordnung des net.msmq-URI-Namens, der für den Kanal bereitgestellt wurde, zu MSMQ-Formatnamen. In der folgenden Tabelle werden die Regeln, die für die Zuordnung zwischen den Namen verwendet werden, zusammengefasst.  
  
|WCF URI-basierte Warteschlangenadresse|Verwenden Sie die Active Directory-Eigenschaft|Warteschlangen-Übertragungsprotokoll-Eigenschaft|Resultierende MSMQ-Formatnamen|  
|----------------------------------|-----------------------------------|--------------------------------------|---------------------------------|  
|NET.MSMQ://\<Machine-Name >/Private/Abc|False (Standardwert)|Systemeigen (Standardwert)|DIRECT=OS:Computername\privat$\abc|  
|NET.MSMQ://\<Machine-Name >/Private/Abc|False|SRMP|DIRECT=http://Computer/msmq/privat$/abc|  
|NET.MSMQ://\<Machine-Name >/Private/Abc|True|Systemeigen|PUBLIC=some-guid (die GUID der Warteschlange)|  
  
### <a name="reading-messages-from-the-dead-letter-queue-or-the-poison-message-queue"></a>Lesen von Nachrichten aus der Warteschlange für unzustellbare Nachrichten oder der Warteschlange für potenziell schädliche Nachrichten  
 Zum Lesen von Nachrichten aus einer Warteschlange für potenziell schädliche Nachrichten, bei der es sich um eine Unterwarteschlange der Zielwarteschlange handelt, öffnen Sie den `ServiceHost` mit der Adresse der Unterwarteschlange.  
  
 Beispiel: Ein Dienst, der aus der Warteschlange für potenziell schädliche Nachrichten der privaten PurchaseOrders-Warteschlange auf dem lokalen Computer liest, würde net.msmq://localhost/private/PurchaseOrders;poison adressieren.  
  
 Zum Lesen von Nachrichten aus einer transaktionalen Systemwarteschlange für unzustellbare Nachrichten muss der URI folgendes Format haben: net.msmq://localhost/system$;DeadXact.  
  
 Zum Lesen von Nachrichten aus einer nicht transaktionalen Systemwarteschlange für unzustellbare Nachrichten muss der URI folgendes Format haben: net.msmq://localhost/system$;DeadLetter.  
  
 Wenn Sie eine benutzerdefinierte Warteschlange für unzustellbare Nachrichten verwenden, beachten Sie, dass sich die Warteschlange für unzustellbare Nachrichten auf dem lokalen Computer befinden muss. Deshalb ist der URI für die Warteschlange für unzustellbare Nachrichten auf das folgende Format beschränkt:  
  
 NET.MSMQ: //localhost/ [private /] \< *Custom-Dead-Letter-Queue-Name*>.  
  
 Ein [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst überprüft, ob alle eingehenden Nachrichten an die überwachte Warteschlange adressiert waren. Wenn die Zielwarteschlange der Nachricht nicht mit der Warteschlange übereinstimmt, in der sie gefunden wird, verarbeitet der Dienst die Nachricht nicht. Dies ist ein Problem, das Dienste, die eine Warteschlange für unzustellbare Nachrichten abhören, behandeln müssen, da alle Nachrichten in der Warteschlange für unzustellbare Nachrichten für eine andere Adresse bestimmt waren. Um Nachrichten aus einer Warteschlange für unzustellbare Nachrichten oder einer Warteschlange für potenziell schädliche Nachrichten zu lesen, muss ein `ServiceBehavior` mit dem <xref:System.ServiceModel.AddressFilterMode.Any>-Parameter verwendet werden. Ein Beispiel finden Sie unter [Warteschlangen für unzustellbare](../../../../docs/framework/wcf/samples/dead-letter-queues.md).  
  
## <a name="msmqintegrationbinding-and-service-addressing"></a>NetMsmqBinding und Dienstadressierung  
 Die `MsmqIntegrationBinding` wird für die Kommunikation mit herkömmlichen MSMQ-Anwendungen verwendet. Um die Zusammenarbeit mit einer vorhandenen MSMQ-Anwendung zu vereinfachen, unterstützt [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] nur die Formatnamenadressierung. Folglich müssen Nachrichten, die mithilfe dieser Bindung gesendet werden, dem URI-Schema entsprechen:  
  
 MSMQ.FormatName:\<*MSMQ-Formatnamen*>>  
  
 Der MSMQ-Formatnamen wird der angegebenen von MSMQ in Form [zu Message Queuing](http://go.microsoft.com/fwlink/?LinkId=94837).  
  
 Beachten Sie, dass Sie nur direkte Formatnamen verwenden können und dass Sie öffentliche und private Formatnamen (dies erfordert die Integration von Active Directory) verwenden können, wenn Nachrichten von einer Warteschlange mithilfe von `MsmqIntegrationBinding` empfangen werden. Es wird jedoch empfohlen, direkte Formatnamen zu verwenden. Bei [!INCLUDE[wv](../../../../includes/wv-md.md)] kann die Verwendung eines anderen Formatnamens z. B. einen Fehler verursachen, da das System versucht, eine Unterwarteschlange zu öffnen, die nur bei Verwendung von direkten Formatnamen geöffnet werden kann.  
  
 Bei der Adressierung von SRMP mithilfe von `MsmqIntegrationBinding` ist es nicht erforderlich, /msmq/ zu dem direkten Formatnamen hinzuzufügen, um das Senden durch Internetinformationsdienste (Internet Information Services, IIS) zu unterstützen. Beispiel: Bei der Adressierung einer Warteschlange abc mithilfe des SRMP-Protokolls sollten Sie DIRECT=http://adatum.com/privat$/abc statt DIRECT=http://adatum.com/msmq/privat$/abc verwenden.  
  
 Beachten Sie, dass Sie net.msmq:// nicht für die Adressierung mit `MsmqIntegrationBinding` verwenden können. Da `MsmqIntegrationBinding` die formlose MSMQ-Formatnamenadressierung unterstützt, können Sie einen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst verwenden, der diese Bindung verwendet, um Multicast- und Verteilerlistenfunktionen in MSMQ zu verwenden. Eine Ausnahme ist das Angeben von `CustomDeadLetterQueue` bei der Verwendung von `MsmqIntegrationBinding`. Das Format muss net.msmq sein:// sein, ähnlich wie bei der Verwendung von `NetMsmqBinding` festgelegt.  
  
## <a name="see-also"></a>Siehe auch  
 [Webhosting einer Anwendung mit Queuing](../../../../docs/framework/wcf/feature-details/web-hosting-a-queued-application.md)
