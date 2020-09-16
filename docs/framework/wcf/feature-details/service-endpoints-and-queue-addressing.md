---
title: Dienstendpunkte und Adressieren von Warteschlangen
ms.date: 03/30/2017
ms.assetid: 7d2d59d7-f08b-44ed-bd31-913908b83d97
ms.openlocfilehash: fb74ba52c0f08d9e9976ddc8dd6d59037ec32e4b
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90546288"
---
# <a name="service-endpoints-and-queue-addressing"></a>Dienstendpunkte und Adressieren von Warteschlangen
In diesem Thema wird erläutert, wie Clients Dienste adressieren, die Daten aus Warteschlangen auslesen, und wie Dienstendpunkte Warteschlangen zugeordnet werden. Zur Erinnerung: die folgende Abbildung zeigt die Bereitstellung der Bereitstellung der klassischen Windows Communication Foundation (WCF) in der Warteschlange.  
  
 ![In die Warteschlange gestelltes Anwendungsdiagramm](media/distributed-queue-figure.jpg "Verteilte Warteschlangen (Abbildung)")  
  
 Damit der Client die Nachricht an den Dienst senden kann, richtet der Client die Nachricht an die Zielwarteschlange. Damit der Dienst Nachrichten aus der Warteschlange lesen kann, legt er als Abhöradresse die Zielwarteschlange fest. Die Adressierung in WCF ist Uniform Resource Identifier (URI)-basiert, während Message Queuing (MSMQ)-Warteschlangen Namen nicht URI-basiert sind. Daher ist es erforderlich, dass Sie wissen, wie in MSMQ mithilfe von WCF erstellte Warteschlangen adressiert werden.  
  
## <a name="msmq-addressing"></a>MSMQ-Adressierung  
 MSMQ verwendet Pfade und Formatnamen, um eine Warteschlange zu identifizieren. Pfade geben einen Hostnamen und einen `QueueName` an. Optional kann ein `Private$` zwischen dem Hostnamen und dem `QueueName` vorliegen, um eine private Warteschlange anzugeben, die nicht im Active Directory-Verzeichnisdienst veröffentlicht wird.  
  
 Pfadnamen werden "FormatNames" zugeordnet, um weitere Aspekte der Adresse zu bestimmen, einschließlich Routing und Warteschlangen-Manager-Übertragungsprotokoll. Der Warteschlangen-Manager unterstützt zwei Übertragungsprotokolle: das systemeigene MSMQ-Protokoll und das SOAP Reliable Messaging Protocol (SRMP).  
  
 Weitere Informationen zu MSMQ-Pfad-und-Format Namen finden Sie unter [Informationen zu Message Queuing](/previous-versions/windows/desktop/legacy/ms706032(v=vs.85)).  
  
## <a name="netmsmqbinding-and-service-addressing"></a>NetMsmqBinding und Dienstadressierung  
 Bei der Adressierung einer Nachricht an einen Dienst wird das Schema in dem URI anhand des für die Kommunikation verwendeten Transports ausgewählt. Jeder Transport in WCF verfügt über ein eindeutiges Schema. Das Schema muss die Art des für die Kommunikation verwendeten Transports wiedergeben, z. B. net.tcp, net.pipe, HTTP usw.  
  
 Der MSMQ-Warteschlangen Transport in WCF macht ein net. msmq-Schema verfügbar. Alle Nachrichten, die mithilfe des net.msmq-Schemas adressiert werden, werden mithilfe von `NetMsmqBinding` über den MSMQ-Warteschlangen-Transportkanal gesendet.  
  
 Die Adressierung einer Warteschlange in WCF basiert auf dem folgenden Muster:  
  
 NET. MSMQ:// \<*host-name*> /[privat/] \<*queue-name*>  
  
 Dabei gilt Folgendes:  
  
- \<*host-name*> der Name des Computers, der die Ziel Warteschlange hostet.  
  
- [privat] ist optional. Dies wird verwendet, wenn eine Zielwarteschlange adressiert wird, bei der es sich um eine private Warteschlange handelt. Um eine öffentliche Warteschlange zu adressieren, dürfen Sie nicht "privat" angeben. Beachten Sie, dass im Gegensatz zu MSMQ-Pfaden im WCF-URI-Formular kein "$" vorhanden ist.  
  
- \<*queue-name*> der Name der Warteschlange. Der Warteschlangenname kann auch auf eine Unterwarteschlange verweisen. Daher ist \<*queue-name*>  =  \<*name-of-queue*> [;* unter Warteschlangen Name*].  
  
 Beispiel1: Für die Adressierung einer privaten Warteschlange PurchaseOrders, die auf dem Computer abc atadatum.com gehostet wird, wäre der URI net.msmq://abc.adatum.com/private/PurchaseOrders.  
  
 Beispiel2: Für die Adressierung einer öffentlichen Warteschlange AccountsPayable, die auf dem Computer def atadatum.com gehostet wird, wäre der URI net.msmq://def.adatum.com/AccountsPayable.  
  
 Die Warteschlangenadresse wird vom Listener als Abhör-URI zum Lesen von Nachrichten verwendet. Mit anderen Worten, die Warteschlangenadresse entspricht dem Abhöranschluss des TCP-Sockets.  
  
 Ein Endpunkt, der aus einer Warteschlange liest, muss die Adresse der Warteschlange nach demselben Schema angeben, das zuvor beim Öffnen des ServiceHost angegeben worden war. Beispiele finden Sie unter [net-MSMQ-Bindung](../samples/net-msmq-binding.md).  
  
### <a name="multiple-contracts-in-a-queue"></a>Mehrere Verträge in einer Warteschlange  
 Nachrichten in einer Warteschlange können verschiedene Verträge implementieren. In diesem Fall muss eines der folgenden Szenarien zutreffen, um alle Nachrichten erfolgreich lesen und verarbeiten zu können:  
  
- Geben Sie einen Endpunkt für einen Dienst an, der alle Verträge implementiert. Dies ist die empfohlene Vorgehensweise.  
  
- Geben Sie mehrere Endpunkte mit verschiedenen Verträgen an, stellen Sie jedoch sicher, dass alle Endpunkte das gleiche `NetMsmqBinding`-Objekt verwenden. Die Dispatchlogik in ServiceModel verwendet ein Nachrichtensystem, das Nachrichten aus dem Transportkanal für den Dispatch ausliest, der schließlich für die Nachrichten auf der Grundlage des Vertrags ein De-Multiplexing mit anderen Endpunkten ausführt. Es wird ein Nachrichtensystem für ein Abhör-URI-/Bindungspaar erstellt. Die Warteschlangenadresse wird von dem Warteschlangenlistener als Abhör-URI verwendet. Da alle Endpunkte dasselbe Bindungsobjekt verwenden, wird sichergestellt, dass ein einziges Nachrichtensystem zum Lesen der Nachricht und zum Ausführen von De-Multiplexing für relevante Endpunkte auf der Grundlage des Vertrags verwendet wird.  
  
### <a name="srmp-messaging"></a>SRMP-Messaging  
 Wie zuvor erläutert, können Sie das SRMP-Protokoll für Übertragungen zwischen Warteschlangen einsetzen. Dies wird häufig angewendet, wenn ein HTTP-Transport Nachrichten zwischen der Übertragungswarteschlange und der Zielwarteschlange sendet.  
  
 Um das SRMP-Übertragungsprotokoll zu verwenden, adressieren Sie Nachrichten mithilfe des net.msmq-URI-Schemas, wie zuvor erwähnt, und geben Sie Ihre Wahl zwischen SRMP oder sicherem SRMP in der `QueueTransferProtocol`-Eigenschaft der `NetMsmqBinding` an.  
  
 Das Angeben der `QueueTransferProtocol`-Eigenschaft wirkt sich nur auf das Senden aus. Dadurch gibt der Client an, welche Art von Warteschlangenübertragungsprotokoll verwendet werden soll.  
  
### <a name="using-active-directory"></a>Using Active Directory  
 MSMQ wird mit Unterstützung für Active Directory-Integration geliefert. Wenn MSMQ mit Active Directory-Integration installiert wird, muss der Computer Teil einer Windows-Domäne sein. Active Directory zum Veröffentlichen von Warteschlangen für die Ermittlung verwendet wird. solche Warteschlangen werden als *öffentliche Warteschlangen*bezeichnet. Wenn Sie eine Warteschlange adressieren, kann die Warteschlange mit Active Directory aufgelöst werden. Dies funktioniert auf ähnliche Weise wie bei der Verwendung des DNS-Systems (Domain Name System) für die Auflösung einer IP-Adresse eines Netzwerknamens. Die `UseActiveDirectory`-Eigenschaft in der `NetMsmqBinding` ist ein boolescher Wert, der angibt, ob der in der Warteschlange stehende Kanal Active Directory verwenden muss, um den URI der Warteschlange aufzulösen. Standardwert: `false`. Wenn die `UseActiveDirectory`-Eigenschaft als `true` angegeben wird, verwendet der in der Warteschlange stehende Kanal Active Directory zum Umwandeln des net.msmq://-URI in den Formatnamen.  
  
 Die `UseActiveDirectory`-Eigenschaft hat nur für den Client Bedeutung, der die Nachricht sendet, da sie beim Senden von Nachrichten zur Auflösung der Adresse der Warteschlange verwendet wird.  
  
### <a name="mapping-netmsmq-uri-to-message-queuing-format-names"></a>Zuordnen des net.msmq-URI zu Message Queuing-Formatnamen  
 Der in der Warteschlange stehende Kanal verarbeitet die Zuordnung des net.msmq-URI-Namens, der für den Kanal bereitgestellt wurde, zu MSMQ-Formatnamen. In der folgenden Tabelle werden die Regeln, die für die Zuordnung zwischen den Namen verwendet werden, zusammengefasst.  
  
|WCF URI-basierte Warteschlangenadresse|Verwenden Sie die Active Directory-Eigenschaft|Warteschlangen-Übertragungsprotokoll-Eigenschaft|Resultierende MSMQ-Formatnamen|  
|----------------------------------|-----------------------------------|--------------------------------------|---------------------------------|  
|`Net.msmq://<machine-name>/private/abc`|False (Standardwert)|Systemeigen (Standardwert)|`DIRECT=OS:machine-name\private$\abc`|  
|`Net.msmq://<machine-name>/private/abc`|False|SRMP|`DIRECT=http://machine/msmq/private$/abc`|  
|`Net.msmq://<machine-name>/private/abc`|True|Systemeigenes Format|`PUBLIC=some-guid` (die GUID der Warteschlange)|  
  
### <a name="reading-messages-from-the-dead-letter-queue-or-the-poison-message-queue"></a>Lesen von Nachrichten aus der Warteschlange für unzustellbare Nachrichten oder der Warteschlange für potenziell schädliche Nachrichten  
 Zum Lesen von Nachrichten aus einer Warteschlange für potenziell schädliche Nachrichten, bei der es sich um eine Unterwarteschlange der Zielwarteschlange handelt, öffnen Sie den `ServiceHost` mit der Adresse der Unterwarteschlange.  
  
 Beispiel: Ein Dienst, der aus der Warteschlange für potenziell schädliche Nachrichten der privaten PurchaseOrders-Warteschlange auf dem lokalen Computer liest, würde net.msmq://localhost/private/PurchaseOrders;poison adressieren.  
  
 Zum Lesen von Nachrichten aus einer transaktionalen Systemwarteschlange für unzustellbare Nachrichten muss der URI folgendes Format haben: net.msmq://localhost/system$;DeadXact.  
  
 Zum Lesen von Nachrichten aus einer nicht transaktionalen Systemwarteschlange für unzustellbare Nachrichten muss der URI folgendes Format haben: net.msmq://localhost/system$;DeadLetter.  
  
 Wenn Sie eine benutzerdefinierte Warteschlange für unzustellbare Nachrichten verwenden, beachten Sie, dass sich die Warteschlange für unzustellbare Nachrichten auf dem lokalen Computer befinden muss. Deshalb ist der URI für die Warteschlange für unzustellbare Nachrichten auf das folgende Format beschränkt:  
  
 NET. MSMQ://localhost/[private/]  \<*custom-dead-letter-queue-name*> .  
  
 Ein WCF-Dienst überprüft, ob alle empfangenen Nachrichten an die jeweilige Warteschlange adressiert wurden, die er überwacht. Wenn die Zielwarteschlange der Nachricht nicht mit der Warteschlange übereinstimmt, in der sie gefunden wird, verarbeitet der Dienst die Nachricht nicht. Dies ist ein Problem, das Dienste, die eine Warteschlange für unzustellbare Nachrichten abhören, behandeln müssen, da alle Nachrichten in der Warteschlange für unzustellbare Nachrichten für eine andere Adresse bestimmt waren. Um Nachrichten aus einer Warteschlange für unzustellbare Nachrichten oder einer Warteschlange für potenziell schädliche Nachrichten zu lesen, muss ein `ServiceBehavior` mit dem <xref:System.ServiceModel.AddressFilterMode.Any>-Parameter verwendet werden. Ein Beispiel finden Sie unter [Warteschlangen](../samples/dead-letter-queues.md)für unzustellbare Nachrichten.  
  
## <a name="msmqintegrationbinding-and-service-addressing"></a>NetMsmqBinding und Dienstadressierung  
 Die `MsmqIntegrationBinding` wird für die Kommunikation mit herkömmlichen MSMQ-Anwendungen verwendet. Um die Interoperation mit einer vorhandenen MSMQ-Anwendung zu vereinfachen, unterstützt WCF nur die Format Namen Adressierung. Folglich müssen Nachrichten, die mithilfe dieser Bindung gesendet werden, dem URI-Schema entsprechen:  
  
 MSMQ. Format Name:\<*MSMQ-format-name*>>  
  
 Der MSMQ-Format-Name hat das von MSMQ in [Informationen zu Message Queuing](/previous-versions/windows/desktop/legacy/ms706032(v=vs.85))angegebene Format.  
  
 Beachten Sie, dass Sie nur direkte Formatnamen verwenden können und dass Sie öffentliche und private Formatnamen (dies erfordert die Integration von Active Directory) verwenden können, wenn Nachrichten von einer Warteschlange mithilfe von `MsmqIntegrationBinding` empfangen werden. Es wird jedoch empfohlen, direkte Formatnamen zu verwenden. Beispielsweise verursacht unter Windows Vista die Verwendung eines beliebigen anderen Format namens einen Fehler, da das System versucht, eine unter Warteschlange zu öffnen, die nur mit direkten Format Namen geöffnet werden kann.  
  
 Bei der Adressierung von SRMP mithilfe von `MsmqIntegrationBinding` ist es nicht erforderlich, /msmq/ zu dem direkten Formatnamen hinzuzufügen, um das Senden durch Internetinformationsdienste (Internet Information Services, IIS) zu unterstützen. Beispiel: Wenn Sie eine Warteschlange abc mithilfe des SRMP-Protokolls adressieren, `DIRECT=http://adatum.com/msmq/private$/abc` sollten Sie anstelle von verwenden `DIRECT=http://adatum.com/private$/abc` .  
  
 Beachten Sie, dass Sie net.msmq:// nicht für die Adressierung mit `MsmqIntegrationBinding` verwenden können. Da `MsmqIntegrationBinding` unterstützt die Verwendung von MSMQ-Format Namen (Free-Form), können Sie einen WCF-Dienst verwenden, der diese Bindung verwendet, um Multicast-und Verteilerlisten Features in MSMQ zu verwenden. Eine Ausnahme ist das Angeben von `CustomDeadLetterQueue` bei der Verwendung von `MsmqIntegrationBinding`. Das Format muss net.msmq sein:// sein, ähnlich wie bei der Verwendung von `NetMsmqBinding` festgelegt.  
  
## <a name="see-also"></a>Siehe auch

- [Webhosting einer Anwendung mit Queuing](web-hosting-a-queued-application.md)
