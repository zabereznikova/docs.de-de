---
title: ServiceModel-Transaktionsattribute
ms.date: 03/30/2017
helpviewer_keywords:
- transactions [WCF], ServiceModel attributes
ms.assetid: 1e0d2436-6ae5-439b-9765-a448d6f60000
ms.openlocfilehash: 79d97eee328d816281348b5b15cf779e1ee65893
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="servicemodel-transaction-attributes"></a>ServiceModel-Transaktionsattribute
Windows Communication Foundation (WCF) bietet Eigenschaften für drei Standard- <xref:System.ServiceModel> Attribute, die Ihnen ermöglichen, die das Verhalten von Transaktionen für einen WCF-Dienst zu konfigurieren:  
  
-   <xref:System.ServiceModel.TransactionFlowAttribute>  
  
-   <xref:System.ServiceModel.ServiceBehaviorAttribute>  
  
-   <xref:System.ServiceModel.OperationBehaviorAttribute>  
  
## <a name="transactionflowattribute"></a>TransactionFlowAttribute  
 Das <xref:System.ServiceModel.TransactionFlowAttribute>-Attribut legt die Bereitschaft eines Vorgangs in einem Dienstvertrag fest, die vom Client eingehenden Transaktionen anzunehmen. Das Attribut bietet diese Kontrolle über das folgende Attribut: Transaktionen verwenden die <xref:System.ServiceModel.TransactionFlowOption>-Enumeration, um festzulegen, ob eine eingehende Transaktion <xref:System.ServiceModel.TransactionFlowOption.Mandatory>, <xref:System.ServiceModel.TransactionFlowOption.Allowed> oder <xref:System.ServiceModel.TransactionFlowOption.NotAllowed>ist.  
  
 Dies ist das einzige Attribut, das Dienstvorgänge zu externen Interaktionen mit einem Client verknüpft. Die in den folgenden Abschnitten beschriebenen Attribute beziehen sich auf die Verwendung von Transaktionen innerhalb der Ausführung des Vorgangs.  
  
## <a name="servicebehaviorattribute"></a>ServiceBehaviorAttribute  
 Das <xref:System.ServiceModel.ServiceBehaviorAttribute>-Attribut legt das interne Ausführungsverhalten einer Dienstvertragimplementierung fest. Zu den transaktionsspezifischen Eigenschaften dieses Attributs gehören:  
  
-   <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionAutoCompleteOnSessionClose%2A> gibt an, ob eine nicht abgeschlossene Transaktion beim Schließen der Sitzung abgeschlossen wird. Der Standardwert für diese Eigenschaft ist `false`. Ist diese Eigenschaft `true` und wurde die eingehende Sitzung ordnungsgemäß beendet, anstatt aufgrund eines Netzwerk- oder Clientfehlers geschlossen zu werden, werden alle nicht abgeschlossenen Transaktionen erfolgreich abgeschlossen. Ist diese Eigenschaft `false` oder wurde die Sitzung nicht ordnungsgemäß beendet, wird für alle nicht abgeschlossenen Transaktionen beim Schließen der Sitzung ein Rollback ausgeführt. Wenn diese Eigenschaft `true` ist, muss der eingehende Kanal sitzungsbasiert sein.  
  
-   <xref:System.ServiceModel.ServiceBehaviorAttribute.ReleaseServiceInstanceOnTransactionComplete%2A> legt fest, ob die zugrunde liegende Dienstinstanz beim Abschluss einer Transaktion freigegeben wird. Der Standardwert für diese Eigenschaft ist `true`. Die nächste eingehende Nachricht verursacht die Erstellung einer neuen zugrunde liegenden Instanz, wobei der Pro-Transaktionsstatus, über den die vorherige Instanz möglicherweise verfügte, verworfen wird. Die Freigabe einer Dienstinstanz ist eine interne Aktion, die der Dienst durchführt, und hat keinen Einfluss auf bestehende Verbindungen oder Sitzungen, die von Clients möglicherweise aufgebaut wurden. Diese Funktionalität entspricht der JIT-Aktivierungsfunktion (Just-in-Time), die COM+ bereitstellt. Wenn die Eigenschaft `true` ist, muss <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> gleich <xref:System.ServiceModel.ConcurrencyMode.Single> sein. Andernfalls löst der Dienst während des Starts eine ungültige Konfigurationsvalidierungsausnahme aus.  
  
-   <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionIsolationLevel%2A> legt die Isolationsebene fest, die für Transaktionen innerhalb eines Diensts verwendet wird. Diese Eigenschaft nimmt einen der <xref:System.Transactions.IsolationLevel>-Werte an. Ist die Isolationsebeneneigenschaft etwas anderes als <xref:System.Transactions.IsolationLevel.Unspecified>, muss die Isolationsebene einer eingehenden Transaktion der Einstellung dieser lokalen Eigenschaft entsprechen. Andernfalls wird die eingehende Transaktion abgelehnt, und ein Fehler wird an den Client zurückgesendet. Wenn <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A>`true` ist und keine Transaktion übergeben wird, bestimmt diese Eigenschaft den für die lokal erstellte Transaktion zu verwendenden <xref:System.Transactions.IsolationLevel>-Wert. Wenn <xref:System.Transactions.IsolationLevel> festgelegt ist, um <xref:System.Transactions.IsolationLevel.Unspecified>, <xref:System.Transactions.IsolationLevel> <xref:System.Transactions.IsolationLevel.Serializable> verwendet wird.  
  
-   <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionTimeout%2A> legt den Zeitraum fest, innerhalb dessen eine neue, am Dienst erstellte Transaktion abgeschlossen sein muss. Ist dieser Zeitpunkt erreicht und wurde die Transaktion nicht abgeschlossen, wird sie abgebrochen. Die <xref:System.TimeSpan> wird als <xref:System.Transactions.TransactionScope>-Timeout für alle Vorgänge verwendet, bei denen <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> auf `true` gesetzt ist und für die eine neue Transaktion erstellt worden war. Der Timeout ist die maximal zulässige Dauer von der Erstellung einer Transaktion bis zum Abschluss der Phase 1 im Zweiphasen-Commitprotokoll. Der verwendete Timeout ist immer der niedrigere Wert der <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionTimeout%2A>-Eigenschaft und der `transactionTimeout`-Konfigurationseinstellung.  
  
## <a name="operationbehaviorattribute"></a>OperationBehaviorAttribute  
 Das <xref:System.ServiceModel.OperationBehaviorAttribute>-Attribut legt die Verhaltensweisen der Methoden in der Dienstimplementierung fest. Sie können es verwenden, um das spezifische Ausführungsverhalten des Vorgangs anzugeben. Eigenschaften dieses Attributs wirken sich nicht auf die Web Service Description Language (WSDL) Beschreibung des Dienstvertrags und sind lediglich um Elemente des WCF-Programmiermodells, die allgemeine Funktionen zu ermöglichen, dass die Entwickler andernfalls selbst implementieren müssen.  
  
 Dieses Attribut verfügt über die folgenden transaktionsspezifischen Eigenschaften:  
  
-   <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> gibt an, ob eine Methode innerhalb eines aktiven Transaktionsbereichs ausgeführt werden muss. Die Standardeinstellung ist `false`. Ist das <xref:System.ServiceModel.OperationBehaviorAttribute>-Attribut für eine Methode nicht eingerichtet, wird darüber hinaus angegeben, dass die Methode in einer Transaktion nicht ausgeführt wird. Wird für einen Vorgang kein Transaktionsumfang benötigt, sind alle im Nachrichtenheader vorhandenen Transaktionen nicht aktiviert und bleiben ein Element der <xref:System.ServiceModel.OperationContext.IncomingMessageProperties%2A> des <xref:System.ServiceModel.OperationContext>. Ist für einen Vorgang ein Transaktionsumfang erforderlich, leitet sich die Quelle für die Transaktion folgendermaßen ab:  
  
    -   Wenn eine Transaktion von einem Client übergeben wird, wird die Methode unter einem Transaktionsumfang ausgeführt, der mithilfe der verteilten Transaktion erstellt wurde.  
  
    -   Bei einer in der Warteschlange befindlichen Transaktion wird die Transaktion verwendet, die zum Entfernen der Nachricht aus der Warteschlange zum Einsatz kommt. Beachten Sie, dass es sich bei der verwendeten Transaktion nicht um eine übertragene Transaktion handelt, da diese nicht vom Originalabsender der Nachricht bereitgestellt wurde.  
  
    -   Ein benutzerdefinierter Transport kann durch die Verwendung der `TransportTransactionProperty` eine Transaktion bereitstellen.  
  
    -   Wenn keiner der oben aufgeführten Posten eine externe Quelle für eine Transaktion bereitstellt, wird eine neue <xref:System.Transactions.Transaction>-Instanz direkt vor dem Aufruf der Methode erstellt.  
  
-   <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> legt fest, ob die Transaktion, in der die Methode ausgeführt wird, automatisch abgeschlossen wird, wenn keine Ausnahmefehler ausgelöst werden. Ist diese Eigenschaft `true`, kennzeichnet die aufrufende Infrastruktur die Transaktion automatisch als "abgeschlossen", wenn die Benutzermethode zurückgegeben wird, ohne dass eine Ausnahme ausgelöst wird. Ist diese Eigenschaft `false`, wird die Transaktion an die Instanz angehängt und nur als "abgeschlossen" gekennzeichnet, wenn der Client eine nachfolgende Methode aufruft, die mit dieser Eigenschaft auf `true` gekennzeichnet ist, oder wenn eine nachfolgende Methode explizit <xref:System.ServiceModel.OperationContext.SetTransactionComplete%2A> aufruft. Wird keiner der genannten Posten durchgeführt, wird die Transaktion nie abgeschlossen und die darin befindliche Arbeit wird nicht ausgeführt, es sei denn die <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionAutoCompleteOnSessionClose%2A>-Eigenschaft ist auf `true` gesetzt. Ist diese Eigenschaft auf `true` gesetzt, müssen Sie einen Kanal mit einer Sitzung verwenden und der <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> muss auf <xref:System.ServiceModel.InstanceContextMode.PerSession> gesetzt sein.
