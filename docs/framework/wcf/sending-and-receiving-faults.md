---
title: "Senden und Empfangen von Fehlern | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Behandeln von Fehlern [WCF], Senden"
ms.assetid: 7be6fb96-ce2a-450b-aebe-f932c6a4bc5d
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# Senden und Empfangen von Fehlern
SOAP\-Fehler vermitteln Informationen über Fehlerbedingungen von einem Dienst an einen Client und bei Duplexkommunikation von einem Client an einen Dienst in einem interoperablen Verfahren.In der Regel definiert ein Dienst benutzerdefinierten Fehlerinhalt und legt fest, welche Vorgänge ihn zurückgeben können.\(Weitere Informationen finden Sie unter [Definieren und Angeben von Fehlern](../../../docs/framework/wcf/defining-and-specifying-faults.md).\) In diesem Thema wird erläutert, wie ein Dienst oder ein Duplexclient diese Fehler senden kann, wenn der entsprechende Fehlerzustand aufgetreten ist, und wie eine Client\- oder Dienstanwendung diese Fehler verarbeitet.Eine Übersicht über die Fehlerbehandlung bei [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]\-Anwendungen finden Sie unter [Angeben und Behandeln von Fehlern in Verträgen und Diensten](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md).  
  
## Senden von SOAP\-Fehlern  
 Bei deklarierten SOAP\-Fehlern verfügt ein Vorgang über ein <xref:System.ServiceModel.FaultContractAttribute?displayProperty=fullName>, das einen benutzerdefinierten SOAP\-Fehlertyp angibt.Nicht deklarierte SOAP\-Fehler sind jene, die nicht im Vertrag für eine Operation festgelegt werden.  
  
### Senden von deklarierten Fehlern  
 Um einen deklarierten SOAP\-Fehler zu senden, erkennen Sie die Fehlerbedingung, zu der der SOAP\-Fehler passt, und lösen Sie eine neue <xref:System.ServiceModel.FaultException%601?displayProperty=fullName> aus, bei der der Typparameter ein neues Objekt des Typs ist, der im <xref:System.ServiceModel.FaultContractAttribute> für diesen Vorgang angegeben ist.Im folgenden Codebeispiel wird veranschaulicht, wie mit dem <xref:System.ServiceModel.FaultContractAttribute> angegeben werden kann, dass der `SampleMethod`\-Vorgang einen SOAP\-Fehler mit dem Detailtyp `GreetingFault` zurückgeben kann.  
  
 [!code-csharp[FaultContractAttribute#4](../../../samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#4)]
 [!code-vb[FaultContractAttribute#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#4)]  
  
 Um die `GreetingFault`\-Fehlerinformation an den Client zu übermitteln, fangen Sie die entsprechende Fehlerbedingung ab, und lösen Sie eine <xref:System.ServiceModel.FaultException%601?displayProperty=fullName> vom Typ `GreetingFault` mit einem neuen `GreetingFault`\-Objekt als Argument aus, wie im folgenden Codebeispiel dargestellt.Wenn es sich bei dem Client um eine [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Clientanwendung handelt, erfährt er dies als verwaltete Ausnahme, wobei der Typ eine <xref:System.ServiceModel.FaultException%601?displayProperty=fullName> vom Typ `GreetingFault` ist.  
  
 [!code-csharp[FaultContractAttribute#5](../../../samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#5)]
 [!code-vb[FaultContractAttribute#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#5)]  
  
### Senden von undeklarierten Fehlern  
 Das Senden von undeklarierten Fehlern kann sehr nützlich sein, um Probleme in [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Anwendungen schnell zu diagnostizieren und zu debuggen, aber sein Nutzen als Debugtool ist begrenzt.Allgemeiner gesagt, ist es empfehlenswert, beim Debuggen die <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=fullName>\-Eigenschaft zu verwenden.Wenn Sie diesen Wert auf true festlegen, erfahren Clients solche Fehler als <xref:System.ServiceModel.FaultException%601>\-Ausnahmen des Typs <xref:System.ServiceModel.ExceptionDetail>.  
  
> [!IMPORTANT]
>  Da mit verwalteten Ausnahmen interne Anwendungsinformationen verfügbar gemacht werden können, kann mit der Festlegung von `true` für <xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A?displayProperty=fullName> oder <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=fullName>[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Clients gestattet werden, Informationen über interne Dienstvorgangsausnahmen, einschließlich persönlich identifizierbarer oder anderer vertraulicher Informationen, zu erhalten.  
>   
>  Daher wird die Festlegung von `true` für <xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A?displayProperty=fullName> oder <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=fullName> nur für das vorübergehende Debuggen einer Dienstanwendung empfohlen.Außerdem beinhaltet die WSDL für eine Methode, die nicht behandelte verwaltete Ausnahmen auf diese Weise zurückgibt, keinen Vertrag für die <xref:System.ServiceModel.FaultException%601> vom Typ <xref:System.ServiceModel.ExceptionDetail>.Clients müssen die Wahrscheinlichkeit eines unbekannten SOAP\-Fehlers erwarten \(an [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Clients als <xref:System.ServiceModel.FaultException?displayProperty=fullName>\-Objekte zurückgegeben\), um die Debuginformationen richtig zu erhalten.  
  
 Um einen undeklarierten SOAP\-Fehler zu senden, lösen Sie ein <xref:System.ServiceModel.FaultException?displayProperty=fullName>\-Objekt aus \(d. h. nicht den generischen Typ <xref:System.ServiceModel.FaultException%601>\), und übergeben Sie die Zeichenfolge dem Konstruktor.Dies wird für die [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Clientanwendungen als eine ausgelöste <xref:System.ServiceModel.FaultException?displayProperty=fullName>\-Ausnahme verfügbar gemacht, wobei die Zeichenfolge durch Aufrufen der <xref:System.ServiceModel.FaultException%601.ToString%2A?displayProperty=fullName>\-Methode verfügbar ist.  
  
> [!NOTE]
>  Wenn Sie einen SOAP\-Fehler vom Typ Zeichenfolge deklarieren und dies dann in Ihrem Service als <xref:System.ServiceModel.FaultException%601> auslösen, wobei der Typparameter eine <xref:System.String?displayProperty=fullName> ist, wird der Zeichenfolgenwert der <xref:System.ServiceModel.FaultException%601.Detail%2A?displayProperty=fullName>\-Eigenschaft zugewiesen und ist nicht über <xref:System.ServiceModel.FaultException%601.ToString%2A?displayProperty=fullName> verfügbar.  
  
## Behandeln von Fehlern  
 Bei [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Clients werden während einer Kommunikation auftretende SOAP\-Fehler, die für Clientanwendungen relevant sind, als verwaltete Ausnahmen ausgelöst.Während es viele Ausnahmen gibt, die während der Ausführung eines Programms auftreten können, können Anwendungen, die das Programmiermodell des [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Clients verwenden, Ausnahmen der beiden folgenden Typen als Kommunikationsergebnis behandeln.  
  
-   <xref:System.TimeoutException>  
  
-   <xref:System.ServiceModel.CommunicationException>  
  
 <xref:System.TimeoutException>\-Objekte werden ausgelöst, wenn ein Vorgang das angegebene Zeitlimit überschreitet.  
  
 <xref:System.ServiceModel.CommunicationException>\-Objekte werden ausgelöst, wenn entweder beim Dienst oder beim Client eine behebbare Kommunikationsfehlerbedingung besteht.  
  
 Die <xref:System.ServiceModel.CommunicationException>\-Klasse verfügt über zwei wichtige abgeleitete Typen: <xref:System.ServiceModel.FaultException> und den generischen <xref:System.ServiceModel.FaultException%601>\-Typ.  
  
 <xref:System.ServiceModel.FaultException>\-Ausnahmen werden ausgelöst, wenn ein Listener einen Fehler empfängt, der in dem Vorgangsvertrag nicht erwartet oder festgelegt ist; dies geschieht normalerweise, wenn die Anwendung gedebuggt wird und die <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=fullName>\-Eigenschaft des Diensts auf `true` festgelegt ist.  
  
 Am Client werden <xref:System.ServiceModel.FaultException%601>\-Ausnahmen ausgelöst, wenn ein im Vorgangsvertrag angegebener Fehler als Antwort auf einen bidirektionalen Vorgang empfangen wird \(d. h. eine Methode mit einem <xref:System.ServiceModel.OperationContractAttribute>\-Attribut, bei dem <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> auf `false` festgelegt ist\).  
  
> [!NOTE]
>  Wenn für einen [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Dienst die <xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A?displayProperty=fullName>\- oder die <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=fullName>\-Eigenschaft auf `true` festgelegt ist, erfährt der Client dies als eine undeklarierte <xref:System.ServiceModel.FaultException%601> vom Typ <xref:System.ServiceModel.ExceptionDetail>.Clients können diesen bestimmten Fehler entweder abfangen oder den Fehler in einem Catch\-Block für <xref:System.ServiceModel.FaultException> behandeln.  
  
 In der Regel sind nur <xref:System.ServiceModel.FaultException%601>\-, <xref:System.TimeoutException>\- und <xref:System.ServiceModel.CommunicationException>\-Ausnahmen für Clients und Dienste relevant.  
  
> [!NOTE]
>  Es treten natürlich andere Ausnahmen auf.Unerwartete Ausnahmen schließen schwerwiegende Fehler wie <xref:System.OutOfMemoryException?displayProperty=fullName> ein; in der Regel sollten Anwendungen solche Methoden nicht abfangen.  
  
### Abfangen von Fehlerausnahmen in der richtigen Reihenfolge  
 Da <xref:System.ServiceModel.FaultException%601> von <xref:System.ServiceModel.FaultException> abgeleitet wird und <xref:System.ServiceModel.FaultException> von <xref:System.ServiceModel.CommunicationException> abgeleitet wird, müssen diese Ausnahmen in der richtigen Reihenfolge abgefangen werden.Bei einem try\/catch\-Block, bei dem zuerst <xref:System.ServiceModel.CommunicationException> abgefangen wird, werden z. B. alle angegebenen und nicht angegebenen SOAP\-Fehler dort behandelt; nachfolgende catch\-Blöcke zum Behandeln einer benutzerdefinierten <xref:System.ServiceModel.FaultException%601>\-Ausnahme werden niemals aufgerufen.  
  
 Vergessen Sie nicht, dass ein Vorgang eine beliebige Anzahl angegebener Fehler zurückgeben kann.Jeder Fehler ist ein eindeutiger Typ und muss getrennt behandelt werden.  
  
### Behandeln von Ausnahmen beim Schließen des Kanals  
 Der größte Teil der vorangehenden Erläuterung behandelt Fehler, die während der Verarbeitung von Anwendungsnachrichten gesendet werden, d. h. Nachrichten, die explizit vom Client gesendet werden, wenn die Clientanwendung Vorgänge für das [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Clientobjekt aufruft.  
  
 Sogar lokale Objekte, die das Objekt verwerfen, können Ausnahmen, die während des Wiederverwendungsprozesses auftreten, entweder auslösen oder maskieren.Etwas Ähnliches kann auftreten, wenn Sie [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Clientobjekte verwenden.Wenn Sie Vorgänge aufrufen, senden Sie Nachrichten über eine hergestellte Verbindung.Das Schließen des Kanals kann Ausnahmen auslösen, wenn die Verbindung nicht ordnungsgemäß getrennt wird oder bereits getrennt ist, selbst wenn alle Vorgänge ordnungsgemäß zurückgegeben werden.  
  
 In der Regel werden Clientobjektkanäle auf eine der folgenden Möglichkeiten geschlossen:  
  
-   Wenn das [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Clientobjekt wiederverwendet wird.  
  
-   Wenn die Clientanwendung <xref:System.ServiceModel.ClientBase%601.Close%2A?displayProperty=fullName> aufruft.  
  
-   Wenn die Clientanwendung <xref:System.ServiceModel.ICommunicationObject.Close%2A?displayProperty=fullName> aufruft.  
  
-   Wenn die Clientanwendung einen Vorgang aufruft, bei dem es sich um einen Vorgang handelt, der eine Sitzung beendet.  
  
 In jedem Fall weist das Schließen des Kanals den Kanal an zu beginnen, alle zugrunde liegenden Kanäle zu schließen, die möglicherweise Nachrichten senden, um eine komplexe Funktionalität auf Anwendungsebene zu unterstützen.Wenn z. B. ein Vertrag Sitzungen erfordert, versucht eine Bindung eine Sitzung einzurichten, indem Nachrichten mit dem Dienstkanal ausgetauscht werden, bis eine Sitzung eingerichtet ist.Wenn der Kanal geschlossen wird, benachrichtigt der zugrunde liegende Sitzungskanal den Dienst, dass die Sitzung beendet wird.Wenn der Kanal bereits abgebrochen oder geschlossen ist oder aus anderen Gründen nicht verwendet werden kann \(z. B. wenn ein Netzwerkkabel abgezogen wird\), kann der Clientkanal dem Dienstkanal in diesem Fall nicht mitteilen, dass die Sitzung beendet wird, und dies kann zu einer Ausnahme führen.  
  
### Abbrechen des Kanals \(falls erforderlich\)  
 Da das Schließen des Kanals auch Ausnahmen auslösen kann, wird empfohlen, den Kanal, der für den Aufruf in dem catch\-Block verwendet wurde, zusätzlich zum Abfangen von Fehlerausnahmen in der richtigen Reihenfolge abzubrechen.  
  
 Wenn der Fehler Fehlerinformationen übermittelt, die für einen Vorgang spezifisch sind, und andere ihn möglicherweise verwenden können, muss der Kanal nicht abgebrochen werden \(obwohl dies selten vorkommt\).In allen anderen Fällen wird empfohlen, den Kanal abzubrechen.Eine Beispielanwendung, die all dies veranschaulicht, finden Sie unter [Erwartete Ausnahmen](../../../docs/framework/wcf/samples/expected-exceptions.md).  
  
 Das folgende Codebeispiel veranschaulicht die Behandlung von SOAP\-Fehlerausnahmen in einer grundlegenden Clientanwendung einschließlich eines deklarierten Fehlers und eines undeklarierten Fehlers.  
  
> [!NOTE]
>  Dieser Beispielcode verwendet kein `using`\-Konstrukt.Da das Schließen von Kanälen Ausnahmen auslösen kann, ist es empfehlenswert, dass Anwendungen zuerst einen [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Client erstellen und dann den [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Client im selben try\-Block öffnen, verwenden und schließen.Ausführliche Informationen finden Sie unter [Übersicht über den WCF\-Client](../../../docs/framework/wcf/wcf-client-overview.md) und [Vermeiden von Problemen mit der Using\-Anweisung](../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md).  
  
 [!code-csharp[FaultContractAttribute#3](../../../samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/client.cs#3)]
 [!code-vb[FaultContractAttribute#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/client.vb#3)]  
  
## Siehe auch  
 <xref:System.ServiceModel.FaultException>   
 <xref:System.ServiceModel.FaultException%601>   
 <xref:System.ServiceModel.CommunicationException?displayProperty=fullName>   
 [Erwartete Ausnahmen](../../../docs/framework/wcf/samples/expected-exceptions.md)   
 [Vermeiden von Problemen mit der Using\-Anweisung](../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md)