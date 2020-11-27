---
title: Sitzungen, Instanziierung und Parallelität
description: Erfahren Sie mehr über Sitzungen, Instanziierung und Parallelität, ihre Verwendung und die Interaktionen zwischen Ihnen im wfc.
ms.date: 03/30/2017
ms.assetid: 50797a3b-7678-44ed-8138-49ac1602f35b
ms.openlocfilehash: 7335d1c4d4ddf5247fc42c70cdc5e8ae33be7292
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96254206"
---
# <a name="sessions-instancing-and-concurrency"></a>Sitzungen, Instanziierung und Parallelität

Eine *Sitzung* ist die Korrelation (d. h. die Beziehung) aller zwischen zwei Endpunkten gesendeter Nachrichten. *Instanziierung* bezieht sich auf die Steuerung der Lebensdauer von benutzerdefinierten Dienstobjekten und den zugehörigen <xref:System.ServiceModel.InstanceContext> -Objekten. *Parallelität* bezeichnet die Kontrolle der Anzahl von Threads, die gleichzeitig in einem <xref:System.ServiceModel.InstanceContext> ausgeführt werden.  
  
 In diesem Thema werden diese Einstellungen, ihre Verwendung und die Interaktion zwischen den Einstellungen beschrieben.  
  
## <a name="sessions"></a>Sitzungen  

 Wenn die <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType> -Eigenschaft durch einen Dienstvertrag auf <xref:System.ServiceModel.SessionMode.Required?displayProperty=nameWithType>festgelegt wird, bedeutet dies, dass alle Aufrufe (das heißt der zugrunde liegende Nachrichtenaustausch, durch den die Aufrufe unterstützt werden) Teil derselben Konversation sein müssen. Falls in einem Vertrag angegeben wird, dass Sitzungen zwar erlaubt, aber nicht erforderlich sind, können Clients eine Verbindung herstellen und eine Sitzung aufbauen oder auch nicht. Wird eine Sitzung beendet und eine Nachricht über diesen sitzungsbasierten Kanal gesendet, wird eine Ausnahme ausgelöst.  
  
 WCF-Sitzungen verfügen über die folgenden Hauptfunktionen:  
  
- Sie werden explizit von der aufrufenden Anwendung initiiert und beendet.  
  
- Die während einer Sitzung gesendeten Nachrichten werden in der Reihenfolge verarbeitet, in der sie empfangen wurden.  
  
- Durch Sitzungen wird eine Gruppe von Nachrichten zu einer Konversation zusammengefasst. Diese Korrelation ist jedoch abstrakt. So werden zum Beispiel bei einem sitzungsbasierten Kanal Nachrichten auf Grundlage einer gemeinsamen Netzwerkverbindung zueinander in Beziehung gesetzt, bei einem anderen Kanal geschieht dies wiederum auf Grundlage eines gemeinsamen Tags im Nachrichtentext. Die Funktionen, die von der Sitzung abgeleitet werden können, sind abhängig von der Art der Korrelation.  
  
- Einer WCF-Sitzung ist kein allgemeiner Datenspeicher zugeordnet.  
  
 Wenn Sie mit der <xref:System.Web.SessionState.HttpSessionState?displayProperty=nameWithType> -Klasse in ASP.NET-Anwendungen und der von ihr bereitgestellten Funktionalität vertraut sind, werden Sie möglicherweise die folgenden Unterschiede zwischen dieser Art von Sitzung und WCF-Sitzungen bemerken:  
  
- ASP.NET-Sitzungen werden immer vom Server initiiert.  
  
- ASP.NET-Sitzungen sind implizit Unsortiert.  
  
- ASP.NET-Sitzungen stellen einen allgemeinen Datenspeichermechanismus für Anforderungen bereit.  
  
 Client- und Dienstanwendungen interagieren auf unterschiedliche Weise mit Sitzungen. Clientanwendungen initiieren Sitzungen und empfangen und verarbeiten dann die innerhalb der Sitzung gesendeten Nachrichten. Dienstanwendungen können Sitzungen als Erweiterungspunkt verwenden, um zusätzliches Verhalten hinzuzufügen. Dies geschieht durch direkte Nutzung von <xref:System.ServiceModel.InstanceContext> oder durch Implementierung eines benutzerspezifischen Instanzenkontextanbieters.  
  
## <a name="instancing"></a>Instanziierung  

 Durch das Instanziierungsverhalten (das über die <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A?displayProperty=nameWithType> -Eigenschaft festgelegt wird) lässt sich steuern, wie der <xref:System.ServiceModel.InstanceContext> als Antwort auf eingehende Nachrichten erstellt wird. Standardmäßig ist jeder <xref:System.ServiceModel.InstanceContext> einem benutzerdefinierten Dienstobjekt zugeordnet. Dies bedeutet, dass (im Normalfall) auch die Instanziierung benutzerdefinierter Dienstobjekte über die <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> -Eigenschaft gesteuert wird. Die <xref:System.ServiceModel.InstanceContextMode> -Enumeration definiert die Instanziierungsmodi.  
  
 Es stehen die folgenden Instanziierungsmodi zur Verfügung:  
  
- <xref:System.ServiceModel.InstanceContextMode.PerCall>: Für jede Clientanforderung wird ein neuer <xref:System.ServiceModel.InstanceContext> (und damit auch ein neues Dienstobjekt) erstellt.  
  
- <xref:System.ServiceModel.InstanceContextMode.PerSession>: Für jede neue Clientsitzung wird ein neuer <xref:System.ServiceModel.InstanceContext> (und damit auch ein neues Dienstobjekt) erstellt und für die Lebensdauer dieser Sitzung aufrechterhalten, wofür eine Bindung erforderlich ist, die Sitzungen unterstützt.  
  
- <xref:System.ServiceModel.InstanceContextMode.Single>: Alle Clientanforderungen werden während der Lebensdauer der Anwendung von einem <xref:System.ServiceModel.InstanceContext> (und damit einem Dienstobjekt) verarbeitet.  
  
 Das folgende Codebeispiel zeigt den Standard- <xref:System.ServiceModel.InstanceContextMode> -Wert ( <xref:System.ServiceModel.InstanceContextMode.PerSession> ), der explizit für eine Dienstklasse festgelegt wird.  
  
```csharp  
[ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)]
public class CalculatorService : ICalculatorInstance
{
    ...  
}  
```  
  
 Durch die <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A?displayProperty=nameWithType> -Eigenschaft wird gesteuert, wie oft der <xref:System.ServiceModel.InstanceContext> freigegeben wird. Die <xref:System.ServiceModel.OperationBehaviorAttribute.ReleaseInstanceMode%2A?displayProperty=nameWithType> -Eigenschaft und die <xref:System.ServiceModel.ServiceBehaviorAttribute.ReleaseServiceInstanceOnTransactionComplete%2A?displayProperty=nameWithType> -Eigenschaft bestimmen dagegen, wann das Dienstobjekt freigegeben wird.  
  
### <a name="well-known-singleton-services"></a>Bekannte Singleton-Dienste  

 Gelegentlich ist eine Variante für einzelne Instanzendienstobjekte nützlich: Sie können selbst ein Dienstobjekt und den Diensthost, der dieses Objekt verwendet, erstellen. Hierfür müssen Sie auch die <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A?displayProperty=nameWithType> -Eigenschaft auf <xref:System.ServiceModel.InstanceContextMode.Single> festlegen, damit keine Ausnahme ausgelöst wird, sobald der Diensthost geöffnet wird.  
  
 Verwenden Sie zum Erstellen eines solchen Diensts den <xref:System.ServiceModel.ServiceHost.%23ctor%28System.Object%2CSystem.Uri%5B%5D%29> -Konstruktor. Dieser stellt eine Alternative zur Implementierung eines benutzerdefinierten <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer?displayProperty=nameWithType> dar, wenn Sie eine bestimmte Objektinstanz für einen Singleton-Dienst bereitstellen möchten. Sie können diese Überladung verwenden, wenn der Dienst Implementierungstyp schwer zu erstellen ist (wenn er z. b. keinen Parameter losen öffentlichen Konstruktor implementiert).  
  
 Beachten Sie Folgendes: Wenn ein Objekt für diesen Konstruktor bereitgestellt wird, funktionieren einige Funktionen im Zusammenhang mit dem Windows Communication Foundation-Instanziierungsverhalten (WCF) unterschiedlich. So zeigt zum Beispiel der Aufruf von <xref:System.ServiceModel.InstanceContext.ReleaseServiceInstance%2A?displayProperty=nameWithType> keine Wirkung, wenn eine Singleton-Objektinstanz bereitgestellt wird. Dementsprechend werden auch alle anderen Instanzfreigabemechanismen ignoriert. Der <xref:System.ServiceModel.ServiceHost> verhält sich immer so, als ob die <xref:System.ServiceModel.OperationBehaviorAttribute.ReleaseInstanceMode%2A?displayProperty=nameWithType> -Eigenschaft für alle Vorgänge auf <xref:System.ServiceModel.ReleaseInstanceMode.None?displayProperty=nameWithType> festgelegt ist.  
  
### <a name="sharing-instancecontext-objects"></a>Freigeben von InstanceContext-Objekten  

 Sie können auch steuern, welcher sitzungsbasierte Kanal oder Aufruf dem <xref:System.ServiceModel.InstanceContext> -Objekt zugeordnet wird, indem Sie diese Zuordnung selbst vornehmen.  
  
## <a name="concurrency"></a>Parallelität  

 Bei der Parallelität handelt es sich um die Steuerung der Anzahl von Threads, die gleichzeitig in einem <xref:System.ServiceModel.InstanceContext> aktiv sind. Sie können diese Anzahl über <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A?displayProperty=nameWithType> in Verbindung mit der <xref:System.ServiceModel.ConcurrencyMode> -Enumeration bestimmen.  
  
 Es stehen die folgenden drei Parallelitätsmodi zur Verfügung:  
  
- <xref:System.ServiceModel.ConcurrencyMode.Single>: Jeder Instanzkontext darf höchstens über jeweils einen Thread verfügen, der im Instanzkontext Nachrichten verarbeitet. Falls weitere Threads diesen Instanzkontext verwenden möchten, werden sie so lange blockiert, bis der ursprüngliche Thread den Instanzkontext verlässt.  
  
- <xref:System.ServiceModel.ConcurrencyMode.Multiple>: Jede Dienstinstanz kann über mehrere Threads verfügen, die Nachrichten gleichzeitig verarbeiten. Für diesen Parallelitätsmodus muss die Dienstimplementierung threadsicher sein.  
  
- <xref:System.ServiceModel.ConcurrencyMode.Reentrant>: Jede Dienstinstanz verarbeitet jeweils nur eine Nachricht, akzeptiert jedoch eintrittsinvariante Aufrufe. Der Dienst akzeptiert diese Aufrufe nur, wenn er über ein WCF-Client Objekt aufgerufen wird.  
  
> [!NOTE]
> Das Schreiben von Code, bei dem problemlos mehr als ein Thread verwendet wird, kann sich als sehr schwierig erweisen. Stellen Sie sicher, dass Ihr Dienst ordnungsgemäß mit den Modi <xref:System.ServiceModel.ConcurrencyMode.Multiple> bzw. <xref:System.ServiceModel.ConcurrencyMode.Reentrant> arbeiten kann, bevor Sie diese Werte verwenden. Weitere Informationen finden Sie unter <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A>.  
  
 Die Parallelität steht mit dem Instanziierungsmodus in Beziehung. Bei <xref:System.ServiceModel.InstanceContextMode.PerCall> der Instanziierung ist die Parallelität nicht relevant, da jede Nachricht von einem neuen verarbeitet wird <xref:System.ServiceModel.InstanceContext> und daher nie mehr als ein Thread im aktiv ist <xref:System.ServiceModel.InstanceContext> .  
  
 Das folgende Codebeispiel zeigt, wie die <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> -Eigenschaft auf den Wert <xref:System.ServiceModel.ConcurrencyMode.Multiple>festgelegt wird.  
  
```csharp
[ServiceBehavior(ConcurrencyMode=ConcurrencyMode.Multiple, InstanceContextMode = InstanceContextMode.Single)]
public class CalculatorService : ICalculatorConcurrency
{
    ...  
}  
```  
  
## <a name="sessions-interact-with-instancecontext-settings"></a>Interaktion von Sitzungen und InstanceContext-Einstellungen  

 Sitzungen und der <xref:System.ServiceModel.InstanceContext> interagieren je nach Kombination des Werts der <xref:System.ServiceModel.SessionMode> -Enumeration in einem Vertrag und der <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A?displayProperty=nameWithType> -Eigenschaft der Dienstimplementierung, durch die die Zuordnung zwischen Kanälen und bestimmten Dienstobjekten gesteuert wird.  
  
 Die folgende Tabelle enthält eine Übersicht über die Ergebnisse eines eingehenden Kanals, der Sitzungen je nach Kombination der Werte für die <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType> -Eigenschaft und die <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A?displayProperty=nameWithType> -Eigenschaft eines Diensts unterstützt oder nicht unterstützt.  
  
|InstanceContextMode-Wert|<xref:System.ServiceModel.SessionMode.Required>|<xref:System.ServiceModel.SessionMode.Allowed>|<xref:System.ServiceModel.SessionMode.NotAllowed>|  
|-------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|  
|PerCall|-Verhalten mit Sitzungs basierten Kanälen: eine Sitzung und <xref:System.ServiceModel.InstanceContext> für jeden-Befehl.<br />-Verhalten mit sessionless Channel: Es wird eine Ausnahme ausgelöst.|-Verhalten mit Sitzungs basierten Kanälen: eine Sitzung und <xref:System.ServiceModel.InstanceContext> für jeden-Befehl.<br />-Verhalten mit sessionless Channel: ein <xref:System.ServiceModel.InstanceContext> für jeden-Befehl.|-Verhalten mit Sitzungs basierten Kanälen: Es wird eine Ausnahme ausgelöst.<br />-Verhalten mit sessionless Channel: ein <xref:System.ServiceModel.InstanceContext> für jeden-Befehl.|  
|PerSession|-Verhalten mit Sitzungs basierten Kanälen: eine Sitzung und <xref:System.ServiceModel.InstanceContext> für jeden Kanal.<br />-Verhalten mit sessionless Channel: Es wird eine Ausnahme ausgelöst.|-Verhalten mit Sitzungs basierten Kanälen: eine Sitzung und <xref:System.ServiceModel.InstanceContext> für jeden Kanal.<br />-Verhalten mit sessionless Channel: ein <xref:System.ServiceModel.InstanceContext> für jeden-Befehl.|-Verhalten mit Sitzungs basierten Kanälen: Es wird eine Ausnahme ausgelöst.<br />-Verhalten mit sessionless Channel: ein <xref:System.ServiceModel.InstanceContext> für jeden-Befehl.|  
|Single|-Verhalten mit Sitzungs basierten Kanälen: eine Sitzung und eine <xref:System.ServiceModel.InstanceContext> für alle Aufrufe.<br />-Verhalten mit sessionless Channel: Es wird eine Ausnahme ausgelöst.|-Verhalten mit Sitzungs basierten Kanälen: eine Sitzung und <xref:System.ServiceModel.InstanceContext> für den erstellten oder benutzerdefinierten Singleton.<br />-Verhalten mit sessionless Channel: ein-Objekt <xref:System.ServiceModel.InstanceContext> für den erstellten oder den Benutzer angegebenen Singleton.|-Verhalten mit Sitzungs basierten Kanälen: Es wird eine Ausnahme ausgelöst.<br />-Verhalten mit sessionless Channel: ein <xref:System.ServiceModel.InstanceContext> für jeden erstellten SINGLETON oder für den vom Benutzer angegebenen Singleton.|  
  
## <a name="see-also"></a>Weitere Informationen

- [Verwenden von Sitzungen](../using-sessions.md)
- [Vorgehensweise: Erstellen eines Diensts, der Sitzungen erfordert](how-to-create-a-service-that-requires-sessions.md)
- [Vorgehensweise: Steuern der Dienstinstanzierung](how-to-control-service-instancing.md)
- [Parallelität](../samples/concurrency.md)
- [Instanziierung](../samples/instancing.md)
- [Sitzungskonsistenz](../samples/session.md)
