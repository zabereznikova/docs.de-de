---
title: "Sitzungen, Instanziierung und Parallelit&#228;t | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 50797a3b-7678-44ed-8138-49ac1602f35b
caps.latest.revision: 16
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 16
---
# Sitzungen, Instanziierung und Parallelit&#228;t
Eine *Sitzung* ist die Korrelation \(d.&\#160;h. die Beziehung\) aller zwischen zwei Endpunkten gesendeter Nachrichten.*Instanziierung* bezieht sich auf die Steuerung der Lebensdauer von benutzerdefinierten Dienstobjekten und den zugehörigen <xref:System.ServiceModel.InstanceContext>\-Objekten.*Parallelität* bezeichnet die Kontrolle der Anzahl von Threads, die gleichzeitig in einem <xref:System.ServiceModel.InstanceContext> ausgeführt werden.  
  
 In diesem Thema werden diese Einstellungen, ihre Verwendung und die Interaktion zwischen den Einstellungen beschrieben.  
  
## Sitzungen  
 Wenn die <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=fullName>\-Eigenschaft durch einen Dienstvertrag auf <xref:System.ServiceModel.SessionMode?displayProperty=fullName> festgelegt wird, bedeutet dies, dass alle Aufrufe \(das heißt der zugrunde liegende Nachrichtenaustausch, durch den die Aufrufe unterstützt werden\) Teil derselben Konversation sein müssen. Falls in einem Vertrag angegeben wird, dass Sitzungen zwar erlaubt, aber nicht erforderlich sind, können Clients eine Verbindung herstellen und eine Sitzung aufbauen oder auch nicht. Wird eine Sitzung beendet und eine Nachricht über diesen sitzungsbasierten Kanal gesendet, wird eine Ausnahme ausgelöst.  
  
 Bei [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Sitzungen finden sich die folgenden Hauptkonzepte:  
  
-   Sie werden explizit von der aufrufenden Anwendung initiiert und beendet.  
  
-   Die während einer Sitzung gesendeten Nachrichten werden in der Reihenfolge verarbeitet, in der sie empfangen wurden.  
  
-   Durch Sitzungen wird eine Gruppe von Nachrichten zu einer Konversation zusammengefasst. Diese Korrelation ist jedoch abstrakt. So werden zum Beispiel bei einem sitzungsbasierten Kanal Nachrichten auf Grundlage einer gemeinsamen Netzwerkverbindung zueinander in Beziehung gesetzt, bei einem anderen Kanal geschieht dies wiederum auf Grundlage eines gemeinsamen Tags im Nachrichtentext. Die Funktionen, die von der Sitzung abgeleitet werden können, sind abhängig von der Art der Korrelation.  
  
-   Einer [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Sitzung ist kein allgemeiner Datenspeicher zugeordnet.  
  
 Falls Sie mit der <xref:System.Web.SessionState.HttpSessionState?displayProperty=fullName>\-Klasse und den von ihr bereitgestellten Funktionen in [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]\-Anwendungen vertraut sind, fallen Ihnen möglicherweise die folgenden Unterschiede zwischen dieser Art von Sitzung und einer [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Sitzung auf:  
  
-   [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]\-Sitzungen werden immer vom Server initiiert.  
  
-   [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]\-Sitzungen sind implizit nicht sortiert.  
  
-   [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]\-Sitzungen stellen einen allgemeinen Datenspeicher für Anforderungen bereit.  
  
 Client\- und Dienstanwendungen interagieren auf unterschiedliche Weise mit Sitzungen. Clientanwendungen initiieren Sitzungen und empfangen und verarbeiten dann die innerhalb der Sitzung gesendeten Nachrichten. Dienstanwendungen können Sitzungen als Erweiterungspunkt verwenden, um zusätzliches Verhalten hinzuzufügen. Dies geschieht durch direkte Nutzung von <xref:System.ServiceModel.InstanceContext> oder durch Implementierung eines benutzerspezifischen Instanzenkontextanbieters.  
  
## Instanziierung  
 Durch das Instanziierungsverhalten \(das über die <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A?displayProperty=fullName>\-Eigenschaft festgelegt wird\) lässt sich steuern, wie der <xref:System.ServiceModel.InstanceContext> als Antwort auf eingehende Nachrichten erstellt wird. Standardmäßig ist jeder <xref:System.ServiceModel.InstanceContext> einem benutzerdefinierten Dienstobjekt zugeordnet. Dies bedeutet, dass \(im Normalfall\) auch die Instanziierung benutzerdefinierter Dienstobjekte über die <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>\-Eigenschaft gesteuert wird. Die <xref:System.ServiceModel.InstanceContextMode>\-Enumeration definiert die Instanziierungsmodi.  
  
 Es stehen die folgenden Instanziierungsmodi zur Verfügung:  
  
-   <xref:System.ServiceModel.InstanceContextMode>: Für jede Clientanforderung wird ein neuer <xref:System.ServiceModel.InstanceContext> \(und damit auch ein neues Dienstobjekt\) erstellt.  
  
-   <xref:System.ServiceModel.InstanceContextMode>: Für jede neue Clientsitzung wird ein neuer <xref:System.ServiceModel.InstanceContext> \(und damit auch ein neues Dienstobjekt\) erstellt und für die Lebensdauer dieser Sitzung aufrechterhalten, wofür eine Bindung erforderlich ist, die Sitzungen unterstützt.  
  
-   <xref:System.ServiceModel.InstanceContextMode>: Alle Clientanforderungen werden während der Lebensdauer der Anwendung von einem <xref:System.ServiceModel.InstanceContext> \(und damit einem Dienstobjekt\) verarbeitet.  
  
 Das folgende Codebeispiel zeigt den Standard\-<xref:System.ServiceModel.InstanceContextMode>\-Wert \(<xref:System.ServiceModel.InstanceContextMode>\), der explizit für eine Dienstklasse festgelegt wird.  
  
```  
[ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)]   
public class CalculatorService : ICalculatorInstance   
{   
    ...  
}  
```  
  
 Durch die <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A?displayProperty=fullName>\-Eigenschaft wird gesteuert, wie oft der <xref:System.ServiceModel.InstanceContext> freigegeben wird. Die <xref:System.ServiceModel.OperationBehaviorAttribute.ReleaseInstanceMode%2A?displayProperty=fullName>\-Eigenschaft und die <xref:System.ServiceModel.ServiceBehaviorAttribute.ReleaseServiceInstanceOnTransactionComplete%2A?displayProperty=fullName>\-Eigenschaft bestimmen dagegen, wann das Dienstobjekt freigegeben wird.  
  
### Bekannte Singleton\-Dienste  
 Gelegentlich ist eine Variante für einzelne Instanzendienstobjekte nützlich: Sie können selbst ein Dienstobjekt und den Diensthost, der dieses Objekt verwendet, erstellen. Hierfür müssen Sie auch die <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A?displayProperty=fullName>\-Eigenschaft auf <xref:System.ServiceModel.InstanceContextMode> festlegen, damit keine Ausnahme ausgelöst wird, sobald der Diensthost geöffnet wird.  
  
 Verwenden Sie zum Erstellen eines solchen Diensts den [ServiceHost.ServiceHost\(Object, Uri\<xref:System.ServiceModel.ServiceHost.%23ctor%28System.Object%2CSystem.Uri%5B%5D%29?displayProperty=fullName>\-Konstruktor. Dieser stellt eine Alternative zur Implementierung eines benutzerdefinierten <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer?displayProperty=fullName> dar, wenn Sie eine bestimmte Objektinstanz für einen Singleton\-Dienst bereitstellen möchten. Sie können diese Alternative verwenden, wenn Ihr Dienstimplementierungstyp schwer zu erstellen ist \(wenn er z.&\#160;B. keinen öffentlichen parameterlosen Standardkonstruktor implementiert\).  
  
 Beachten Sie, dass einige Funktionen im Zusammenhang mit dem [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Instanziierungsverhalten anders arbeiten, wenn ein Objekt für diesen Konstruktor bereitgestellt wird. So zeigt zum Beispiel der Aufruf von <xref:System.ServiceModel.InstanceContext.ReleaseServiceInstance%2A?displayProperty=fullName> keine Wirkung, wenn eine Singleton\-Objektinstanz bereitgestellt wird. Dementsprechend werden auch alle anderen Instanzfreigabemechanismen ignoriert. Der <xref:System.ServiceModel.ServiceHost> verhält sich immer so, als ob die <xref:System.ServiceModel.OperationBehaviorAttribute.ReleaseInstanceMode%2A?displayProperty=fullName>\-Eigenschaft für alle Vorgänge auf <xref:System.ServiceModel.ReleaseInstanceMode?displayProperty=fullName> festgelegt ist.  
  
### Freigeben von InstanceContext\-Objekten  
 Sie können auch steuern, welcher sitzungsbasierte Kanal oder Aufruf dem <xref:System.ServiceModel.InstanceContext>\-Objekt zugeordnet wird, indem Sie diese Zuordnung selbst vornehmen.  
  
## Parallelität  
 Bei der Parallelität handelt es sich um die Steuerung der Anzahl von Threads, die gleichzeitig in einem <xref:System.ServiceModel.InstanceContext> aktiv sind. Sie können diese Anzahl über <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A?displayProperty=fullName> in Verbindung mit der <xref:System.ServiceModel.ConcurrencyMode>\-Enumeration bestimmen.  
  
 Es stehen die folgenden drei Parallelitätsmodi zur Verfügung:  
  
-   <xref:System.ServiceModel.ConcurrencyMode>: Jeder Instanzkontext darf höchstens über jeweils einen Thread verfügen, der im Instanzkontext Nachrichten verarbeitet. Falls weitere Threads diesen Instanzkontext verwenden möchten, werden sie so lange blockiert, bis der ursprüngliche Thread den Instanzkontext verlässt.  
  
-   <xref:System.ServiceModel.ConcurrencyMode>: Jede Dienstinstanz kann über mehrere Threads verfügen, die Nachrichten gleichzeitig verarbeiten. Für diesen Parallelitätsmodus muss die Dienstimplementierung threadsicher sein.  
  
-   <xref:System.ServiceModel.ConcurrencyMode>: Jede Dienstinstanz verarbeitet jeweils nur eine Nachricht, akzeptiert jedoch eintrittsinvariante Aufrufe. Der Dienst akzeptiert diese Aufrufe nur dann, wenn der Aufruf über ein [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Clientobjekt erfolgt.  
  
> [!NOTE]
>  Das Schreiben von Code, bei dem problemlos mehr als ein Thread verwendet wird, kann sich als sehr schwierig erweisen. Stellen Sie sicher, dass Ihr Dienst ordnungsgemäß mit den Modi <xref:System.ServiceModel.ConcurrencyMode> bzw. <xref:System.ServiceModel.ConcurrencyMode> arbeiten kann, bevor Sie diese Werte verwenden.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A>.  
  
 Die Parallelität steht mit dem Instanziierungsmodus in Beziehung. Bei der <xref:System.ServiceModel.InstanceContextMode>``\-Instanziierung ist die Parallelität nicht relevant, da jede Nachricht von einem neuen <xref:System.ServiceModel.InstanceContext> verarbeitet wird und daher nie mehr als ein Thread im <xref:System.ServiceModel.InstanceContext> aktiv ist.  
  
 Das folgende Codebeispiel zeigt, wie die <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A>\-Eigenschaft auf den Wert <xref:System.ServiceModel.ConcurrencyMode> festgelegt wird.  
  
```  
[ServiceBehavior(ConcurrencyMode=ConcurrencyMode.Multiple, InstanceContextMode = InstanceContextMode.Single)]   
public class CalculatorService : ICalculatorConcurrency   
{   
    ...  
}  
  
```  
  
## Interaktion von Sitzungen und InstanceContext\-Einstellungen  
 Sitzungen und der <xref:System.ServiceModel.InstanceContext> interagieren je nach Kombination des Werts der <xref:System.ServiceModel.SessionMode>\-Enumeration in einem Vertrag und der <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A?displayProperty=fullName>\-Eigenschaft der Dienstimplementierung, durch die die Zuordnung zwischen Kanälen und bestimmten Dienstobjekten gesteuert wird.  
  
 Die folgende Tabelle enthält eine Übersicht über die Ergebnisse eines eingehenden Kanals, der Sitzungen je nach Kombination der Werte für die <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=fullName>\-Eigenschaft und die <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A?displayProperty=fullName>\-Eigenschaft eines Diensts unterstützt oder nicht unterstützt.  
  
|InstanceContextMode\-Wert|<xref:System.ServiceModel.SessionMode>|<xref:System.ServiceModel.SessionMode>|<xref:System.ServiceModel.SessionMode>|  
|-------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|  
|PerCall|-   Verhalten bei sitzungsbasiertem Kanal: Eine Sitzung und ein <xref:System.ServiceModel.InstanceContext> pro Aufruf.<br />-   Verhalten bei nicht sitzungsbasiertem Kanal: Eine Ausnahme wird ausgelöst.|-   Verhalten bei sitzungsbasiertem Kanal: Eine Sitzung und ein <xref:System.ServiceModel.InstanceContext> pro Aufruf.<br />-   Verhalten bei nicht sitzungsbasiertem Kanal: Ein <xref:System.ServiceModel.InstanceContext> pro Aufruf.|-   Verhalten bei sitzungsbasiertem Kanal: Eine Ausnahme wird ausgelöst.<br />-   Verhalten bei nicht sitzungsbasiertem Kanal: Ein <xref:System.ServiceModel.InstanceContext> pro Aufruf.|  
|PerSession|-   Verhalten bei sitzungsbasiertem Kanal: Eine Sitzung und ein <xref:System.ServiceModel.InstanceContext> pro Kanal.<br />-   Verhalten bei nicht sitzungsbasiertem Kanal: Eine Ausnahme wird ausgelöst.|-   Verhalten bei sitzungsbasiertem Kanal: Eine Sitzung und ein <xref:System.ServiceModel.InstanceContext> pro Kanal.<br />-   Verhalten bei nicht sitzungsbasiertem Kanal: Ein <xref:System.ServiceModel.InstanceContext> pro Aufruf.|-   Verhalten bei sitzungsbasiertem Kanal: Eine Ausnahme wird ausgelöst.<br />-   Verhalten bei nicht sitzungsbasiertem Kanal: Ein <xref:System.ServiceModel.InstanceContext> pro Aufruf.|  
|Single|-   Verhalten bei sitzungsbasiertem Kanal: Eine Sitzung und ein <xref:System.ServiceModel.InstanceContext> für alle Aufrufe.<br />-   Verhalten bei nicht sitzungsbasiertem Kanal: Eine Ausnahme wird ausgelöst.|-   Verhalten bei sitzungsbasiertem Kanal: Eine Sitzung und ein <xref:System.ServiceModel.InstanceContext> für den erstellten bzw. den vom Benutzer angegebenen Singleton.<br />-   Verhalten bei nicht sitzungsbasiertem Kanal: Ein <xref:System.ServiceModel.InstanceContext> für den erstellten bzw. den vom Benutzer angegebenen Singleton.|-   Verhalten bei sitzungsbasiertem Kanal: Eine Ausnahme wird ausgelöst.<br />-   Verhalten bei nicht sitzungsbasiertem Kanal: Ein <xref:System.ServiceModel.InstanceContext> für jeden erstellten Singleton oder für den vom Benutzer angegebenen Singleton.|  
  
## Siehe auch  
 [Verwenden von Sitzungen](../../../../docs/framework/wcf/using-sessions.md)   
 [Vorgehensweise: Erstellen eines Diensts, der Sitzungen erfordert](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-that-requires-sessions.md)   
 [Gewusst wie: Steuern der Dienstinstanzierung](../../../../docs/framework/wcf/feature-details/how-to-control-service-instancing.md)   
 [Parallelität](../../../../docs/framework/wcf/samples/concurrency.md)   
 [Instanziierung](../../../../docs/framework/wcf/samples/instancing.md)   
 [Sitzung](../../../../docs/framework/wcf/samples/session.md)