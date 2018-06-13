---
title: Senden und Empfangen von Fehlern
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- handling faults [WCF], sending
ms.assetid: 7be6fb96-ce2a-450b-aebe-f932c6a4bc5d
ms.openlocfilehash: 5a4b4dc79b0f0dad661d99fae6377d1c86b673b6
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33807706"
---
# <a name="sending-and-receiving-faults"></a>Senden und Empfangen von Fehlern
SOAP-Fehler vermitteln Informationen über Fehlerbedingungen von einem Dienst an einen Client und bei Duplexkommunikation von einem Client an einen Dienst in einem interoperablen Verfahren. In der Regel definiert ein Dienst benutzerdefinierten Fehlerinhalt und legt fest, welche Vorgänge ihn zurückgeben können. (Weitere Informationen finden Sie unter [definieren und Angeben von Fehlern](../../../docs/framework/wcf/defining-and-specifying-faults.md).) In diesem Thema wird erläutert, wie ein Dienst oder ein Duplexclient diese Fehler senden kann, wenn der entsprechende Fehlerzustand aufgetreten ist, und wie eine Client- oder Dienstanwendung diese Fehler verarbeitet. Einen Überblick über die Fehlerbehandlung in Windows Communication Foundation (WCF)-Anwendungen finden Sie unter [angeben und Behandeln von Fehlern in Verträgen und Diensten](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md).  
  
## <a name="sending-soap-faults"></a>Senden von SOAP-Fehlern  
 Bei deklarierten SOAP-Fehlern verfügt ein Vorgang über ein <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType>, das einen benutzerdefinierten SOAP-Fehlertyp angibt. Nicht deklarierte SOAP-Fehler sind Fehler, die nicht im Vertrag eines Vorgangs festgelegt sind.  
  
### <a name="sending-declared-faults"></a>Senden von deklarierten Fehlern  
 Um einen deklarierten SOAP-Fehler zu senden, erkennen Sie die Fehlerbedingung, zu der der SOAP-Fehler passt, und lösen Sie eine neue <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType> aus, bei der der Typparameter ein neues Objekt des Typs ist, der im <xref:System.ServiceModel.FaultContractAttribute> für diesen Vorgang angegeben ist. Im folgenden Codebeispiel wird veranschaulicht, wie mit dem <xref:System.ServiceModel.FaultContractAttribute> angegeben werden kann, dass der `SampleMethod`-Vorgang einen SOAP-Fehler mit dem Detailtyp `GreetingFault` zurückgeben kann.  
  
 [!code-csharp[FaultContractAttribute#4](../../../samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#4)]
 [!code-vb[FaultContractAttribute#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#4)]  
  
 Um die `GreetingFault`-Fehlerinformation an den Client zu übermitteln, fangen Sie die entsprechende Fehlerbedingung ab, und lösen Sie eine <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType> vom Typ `GreetingFault` mit einem neuen `GreetingFault`-Objekt als Argument aus, wie im folgenden Codebeispiel dargestellt. Wenn der Client eine WCF-Clientanwendung befindet, erfährt er dies als eine verwaltete Ausnahme, wobei der Typ ist <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType> vom Typ `GreetingFault`.  
  
 [!code-csharp[FaultContractAttribute#5](../../../samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#5)]
 [!code-vb[FaultContractAttribute#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#5)]  
  
### <a name="sending-undeclared-faults"></a>Senden von undeklarierten Fehlern  
 Senden von undeklarierte Fehlern können sehr hilfreich sein, schnell zu diagnostizieren und zu debuggen Probleme mit WCF-Anwendungen, aber sein nutzen als Debugtool begrenzt ist. Allgemeiner gesagt, ist es empfehlenswert, beim Debuggen die <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType>-Eigenschaft zu verwenden. Wenn Sie diesen Wert auf true festlegen, erfahren Clients solche Fehler als <xref:System.ServiceModel.FaultException%601>-Ausnahmen des Typs <xref:System.ServiceModel.ExceptionDetail>.  
  
> [!IMPORTANT]
>  Da mit verwaltete Ausnahmen interne Anwendungsinformationen verfügbar machen können, der Festlegung <xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> oder <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> auf `true` ermöglicht WCF-Clients zum Abrufen von Informationen über interne dienstvorgangsausnahmen, einschließlich persönlich identifizierbarer oder anderer vertraulicher Informationen.  
>   
>  Daher wird die Festlegung von <xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> für <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> oder `true` nur für das vorübergehende Debuggen einer Dienstanwendung empfohlen. Außerdem beinhaltet die WSDL für eine Methode, die nicht behandelte verwaltete Ausnahmen auf diese Weise zurückgibt, keinen Vertrag für die <xref:System.ServiceModel.FaultException%601> vom Typ <xref:System.ServiceModel.ExceptionDetail>. Clients müssen erwarten, dass die Möglichkeit, einen unbekannten SOAP-Fehler (für WCF-Clients als zurückgegeben <xref:System.ServiceModel.FaultException?displayProperty=nameWithType> Objekte), die Debuginformationen korrekt abrufen.  
  
 Um einen undeklarierten SOAP-Fehler zu senden, lösen Sie ein <xref:System.ServiceModel.FaultException?displayProperty=nameWithType>-Objekt aus (d. h. nicht den generischen Typ <xref:System.ServiceModel.FaultException%601>), und übergeben Sie die Zeichenfolge dem Konstruktor. Wird verfügbar gemacht, die WCF-Clientanwendungen als eine ausgelöste <xref:System.ServiceModel.FaultException?displayProperty=nameWithType> Ausnahme, in die Zeichenfolge durch Aufrufen steht, der <xref:System.ServiceModel.FaultException%601.ToString%2A?displayProperty=nameWithType> Methode.  
  
> [!NOTE]
>  Wenn Sie einen SOAP-Fehler vom Typ Zeichenfolge deklarieren und dies dann in Ihrem Service als <xref:System.ServiceModel.FaultException%601> auslösen, wobei der Typparameter eine <xref:System.String?displayProperty=nameWithType> ist, wird der Zeichenfolgenwert der <xref:System.ServiceModel.FaultException%601.Detail%2A?displayProperty=nameWithType>-Eigenschaft zugewiesen und ist nicht über <xref:System.ServiceModel.FaultException%601.ToString%2A?displayProperty=nameWithType> verfügbar.  
  
## <a name="handling-faults"></a>Behandeln von Fehlern  
 SOAP-Fehler, die auftreten, während der Kommunikation, die für Clientanwendungen relevant sind, werden in WCF-Clients als verwaltete Ausnahmen ausgelöst. Dafür gibt es viele Ausnahmen, die während der Ausführung eines Programms auftreten können, können Anwendungen, die über das Programmiermodell für die WCF-Client davon ausgehen, Ausnahmen von den folgenden zwei Typen als kommunikationsergebnis behandeln.  
  
-   <xref:System.TimeoutException>  
  
-   <xref:System.ServiceModel.CommunicationException>  
  
 <xref:System.TimeoutException>-Objekte werden ausgelöst, wenn ein Vorgang das angegebene Zeitlimit überschreitet.  
  
 <xref:System.ServiceModel.CommunicationException>-Objekte werden ausgelöst, wenn entweder beim Dienst oder beim Client eine behebbare Kommunikationsfehlerbedingung besteht.  
  
 Die <xref:System.ServiceModel.CommunicationException>-Klasse verfügt über zwei wichtige abgeleitete Typen: <xref:System.ServiceModel.FaultException> und den generischen <xref:System.ServiceModel.FaultException%601>-Typ.  
  
 <xref:System.ServiceModel.FaultException>-Ausnahmen werden ausgelöst, wenn ein Listener einen Fehler empfängt, der in dem Vorgangsvertrag nicht erwartet oder festgelegt ist; dies geschieht normalerweise, wenn die Anwendung gedebuggt wird und die <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType>-Eigenschaft des Diensts auf `true` festgelegt ist.  
  
 Am Client werden <xref:System.ServiceModel.FaultException%601>-Ausnahmen ausgelöst, wenn ein im Vorgangsvertrag angegebener Fehler als Antwort auf einen bidirektionalen Vorgang empfangen wird (d. h. eine Methode mit einem <xref:System.ServiceModel.OperationContractAttribute>-Attribut, bei dem <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> auf `false` festgelegt ist).  
  
> [!NOTE]
>  Wenn ein WCF-Dienst hat die <xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> oder <xref:System.ServiceModel.Description.ServiceDebugBehavior.IncludeExceptionDetailInFaults%2A?displayProperty=nameWithType> -Eigenschaftensatz auf `true` der Client erfährt dieses als eine undeklarierte <xref:System.ServiceModel.FaultException%601> vom Typ <xref:System.ServiceModel.ExceptionDetail>. Clients können diesen bestimmten Fehler entweder abfangen oder den Fehler in einem Catch-Block für <xref:System.ServiceModel.FaultException> behandeln.  
  
 In der Regel sind nur <xref:System.ServiceModel.FaultException%601>-, <xref:System.TimeoutException>- und <xref:System.ServiceModel.CommunicationException>-Ausnahmen für Clients und Dienste relevant.  
  
> [!NOTE]
>  Es treten natürlich andere Ausnahmen auf. Unerwartete Ausnahmen schließen schwerwiegende Fehler wie <xref:System.OutOfMemoryException?displayProperty=nameWithType> ein; in der Regel sollten Anwendungen solche Methoden nicht abfangen.  
  
### <a name="catch-fault-exceptions-in-the-correct-order"></a>Abfangen von Fehlerausnahmen in der richtigen Reihenfolge  
 Da <xref:System.ServiceModel.FaultException%601> von <xref:System.ServiceModel.FaultException> abgeleitet wird und <xref:System.ServiceModel.FaultException> von <xref:System.ServiceModel.CommunicationException> abgeleitet wird, müssen diese Ausnahmen in der richtigen Reihenfolge abgefangen werden. Bei einem try/catch-Block, bei dem zuerst <xref:System.ServiceModel.CommunicationException> abgefangen wird, werden z. B. alle angegebenen und nicht angegebenen SOAP-Fehler dort behandelt; nachfolgende catch-Blöcke zum Behandeln einer benutzerdefinierten <xref:System.ServiceModel.FaultException%601>-Ausnahme werden niemals aufgerufen.  
  
 Vergessen Sie nicht, dass ein Vorgang eine beliebige Anzahl angegebener Fehler zurückgeben kann. Jeder Fehler ist ein eindeutiger Typ und muss getrennt behandelt werden.  
  
### <a name="handle-exceptions-when-closing-the-channel"></a>Behandeln von Ausnahmen beim Schließen des Kanals  
 Die meisten die vorangegangenen erläuterungen muss mit Fehlern, die im Verlauf der Verarbeitung von Anwendungsnachrichten, d. h. gesendet nur Nachrichten, die explizit vom Client gesendet werden, wenn die Clientanwendung Vorgänge für den WCF-Clientobjekts aufruft.  
  
 Sogar lokale Objekte, die das Objekt verwerfen, können Ausnahmen, die während des Wiederverwendungsprozesses auftreten, entweder auslösen oder maskieren. Etwas Ähnliches kann auftreten, wenn Sie WCF-Client-Objekte verwenden. Wenn Sie Vorgänge aufrufen, senden Sie Nachrichten über eine hergestellte Verbindung. Das Schließen des Kanals kann Ausnahmen auslösen, wenn die Verbindung nicht ordnungsgemäß getrennt wird oder bereits getrennt ist, selbst wenn alle Vorgänge ordnungsgemäß zurückgegeben werden.  
  
 In der Regel werden Clientobjektkanäle auf eine der folgenden Möglichkeiten geschlossen:  
  
-   Wenn der WCF-Clientobjekt wiederverwendet wird.  
  
-   Wenn die Clientanwendung <xref:System.ServiceModel.ClientBase%601.Close%2A?displayProperty=nameWithType> aufruft.  
  
-   Wenn die Clientanwendung <xref:System.ServiceModel.ICommunicationObject.Close%2A?displayProperty=nameWithType> aufruft.  
  
-   Wenn die Clientanwendung einen Vorgang aufruft, bei dem es sich um einen Vorgang handelt, der eine Sitzung beendet.  
  
 In jedem Fall weist das Schließen des Kanals den Kanal an zu beginnen, alle zugrunde liegenden Kanäle zu schließen, die möglicherweise Nachrichten senden, um eine komplexe Funktionalität auf Anwendungsebene zu unterstützen. Wenn z. B. ein Vertrag Sitzungen erfordert, versucht eine Bindung eine Sitzung einzurichten, indem Nachrichten mit dem Dienstkanal ausgetauscht werden, bis eine Sitzung eingerichtet ist. Wenn der Kanal geschlossen wird, benachrichtigt der zugrunde liegende Sitzungskanal den Dienst, dass die Sitzung beendet wird. Wenn der Kanal bereits abgebrochen oder geschlossen ist oder aus anderen Gründen nicht verwendet werden kann (z. B. wenn ein Netzwerkkabel abgezogen wird), kann der Clientkanal dem Dienstkanal in diesem Fall nicht mitteilen, dass die Sitzung beendet wird, und dies kann zu einer Ausnahme führen.  
  
### <a name="abort-the-channel-if-necessary"></a>Abbrechen des Kanals (falls erforderlich)  
 Da das Schließen des Kanals auch Ausnahmen auslösen kann, wird empfohlen, den Kanal, der für den Aufruf in dem catch-Block verwendet wurde, zusätzlich zum Abfangen von Fehlerausnahmen in der richtigen Reihenfolge abzubrechen.  
  
 Wenn der Fehler Fehlerinformationen übermittelt, die für einen Vorgang spezifisch sind, und andere ihn möglicherweise verwenden können, muss der Kanal nicht abgebrochen werden (obwohl dies selten vorkommt). In allen anderen Fällen wird empfohlen, den Kanal abzubrechen. Ein Beispiel, das alle diese Punkte veranschaulicht, finden Sie unter [Ausnahmen erwartet](../../../docs/framework/wcf/samples/expected-exceptions.md).  
  
 Das folgende Codebeispiel veranschaulicht die Behandlung von SOAP-Fehlerausnahmen in einer grundlegenden Clientanwendung einschließlich eines deklarierten Fehlers und eines undeklarierten Fehlers.  
  
> [!NOTE]
>  Dieser Beispielcode verwendet kein `using`-Konstrukt. Da das Schließen von Kanälen Ausnahmen auslösen kann, empfiehlt es sich, dass Anwendungen erstellen Sie einen WCF-Client zuerst und dann geöffnet ist, verwenden, und Schließen des WCF-Clients in derselben try-Block. Weitere Informationen finden Sie unter [Überblick über WCF-Client](../../../docs/framework/wcf/wcf-client-overview.md) und [Vermeiden von Problemen mit der Using-Anweisung](../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md).  
  
 [!code-csharp[FaultContractAttribute#3](../../../samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/client.cs#3)]
 [!code-vb[FaultContractAttribute#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/client.vb#3)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.FaultException>  
 <xref:System.ServiceModel.FaultException%601>  
 <xref:System.ServiceModel.CommunicationException?displayProperty=nameWithType>  
 [Erwartete Ausnahmen](../../../docs/framework/wcf/samples/expected-exceptions.md)  
 [Vermeiden von Problemen mit der using-Anweisung](../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md)
