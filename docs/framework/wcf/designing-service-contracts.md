---
title: "Entwerfen von Dienstverträgen"
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
helpviewer_keywords: service contracts [WCF]
ms.assetid: 8e89cbb9-ac84-4f0d-85ef-0eb6be0022fd
caps.latest.revision: "34"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 293d7f8502b39eac6508ba10b2fac128c6aa4879
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="designing-service-contracts"></a>Entwerfen von Dienstverträgen
In diesem Thema wird erläutert, was Dienstverträge sind, wie sie definiert werden, welche Vorgänge verfügbar sind (und die Implikationen des zugrunde liegenden Meldungsaustauschs), welche Datentypen verwendet werden sowie andere Aspekte, die Sie beim Entwerfen von Vorgängen unterstützen, die den Anforderungen Ihres Szenarios gerecht werden.  
  
## <a name="creating-a-service-contract"></a>Erstellen eines Dienstvertrags  
 Dienste machen eine Reihe von Vorgängen verfügbar. In [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]-Anwendungen definieren Sie Vorgänge, indem Sie eine Methode erstellen und diese mit dem <xref:System.ServiceModel.OperationContractAttribute>-Attribut markieren. Zum Erstellen eines Dienstvertrags gruppieren Sie dann die Vorgänge, indem Sie sie in einer Schnittstelle deklarieren, die mit dem <xref:System.ServiceModel.ServiceContractAttribute>-Attribut markiert wurde, oder indem Sie sie in einer Klasse definieren, die mit dem gleichen Attribut markiert wurde. (Ein einfaches Beispiel finden Sie unter [wie: Definieren eines Dienstvertrags](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md).)  
  
 Alle Methoden ohne <xref:System.ServiceModel.OperationContractAttribute>-Attribut sind keine Dienstvorgänge und werden von [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Diensten nicht verfügbar gemacht.  
  
 In diesem Thema werden die folgenden Entscheidungspunkte beschrieben, wenn ein Dienstvertrag entworfen wird:  
  
-   Ob Klassen oder Schnittstellen verwendet werden sollen  
  
-   Wie die Datentypen angegeben werden, die Sie austauschen möchten  
  
-   Die Typen von Austauschmustern, die Sie verwenden können  
  
-   Ob Sie einen expliziten Sicherheitsanforderungen-Teil des Vertrags erstellen können  
  
-   Die Einschränkungen für Vorgangseingaben und -ausgaben  
  
## <a name="classes-or-interfaces"></a>Klassen oder Schnittstellen  
 Klassen und Schnittstellen stellen Funktionsgruppierungen dar und können daher beide zum Definieren eines [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienstvertrags verwendet werden. Es wird allerdings empfohlen, Schnittstellen zu verwenden, da sie Dienstverträge direkt modellieren. Ohne Implementierung definieren Schnittstellen lediglich eine Gruppierung von Methoden mit bestimmten Signaturen. Implementieren Sie eine Dienstvertragsschnittstelle, und Sie haben damit gleichzeitig einen [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienst implementiert.  
  
 Dienstvertragsschnittstellen bieten dieselben Vorteile wie verwaltete Schnittstellen:  
  
-   Dienstvertragsschnittstellen können jede Anzahl anderer Dienstvertragsschnittstellen erweitern.  
  
-   Eine einzelne Klasse kann jede Anzahl von Dienstverträgen implementieren, indem sie diese Dienstvertragsschnittstelle implementiert.  
  
-   Sie können die Implementierung eines Dienstvertrags bearbeiten, indem Sie die Schnittstellenimplementierung ändern, während der Dienstvertrag unverändert bleibt.  
  
-   Sie können verschiedene Versionen eines Diensts erstellen, indem Sie die alte und die neue Schnittstelle implementieren. Alte Clients stellen eine Verbindung mit der ursprünglichen Version her, während neuere Clients eine Verbindung mit der neuen Version herstellen können.  
  
> [!NOTE]
>  Bei der Vererbung von anderen Dienstvertragsschnittstellen können Sie Vorgangseigenschaften, wie z. B. den Name und den Namespace, nicht außer Kraft setzen. Wenn Sie dies dennoch versuchen, erstellen Sie im aktuellen Dienstvertrag einen neuen Vorgang.  
  
 [!INCLUDE[crexample](../../../includes/crexample-md.md)]verwenden eine Schnittstelle zum Erstellen eines Dienstvertrags finden Sie unter [Vorgehensweise: Erstellen eines Diensts mit einer Vertragsschnittstelle](../../../docs/framework/wcf/feature-details/how-to-create-a-service-with-a-contract-interface.md).  
  
 Sie können allerdings eine Klasse verwenden, um einen Dienstvertrag zu definieren und gleichzeitig zu implementieren. Der Vorteil des Erstellens Ihrer Dienste durch direktes Anwenden von <xref:System.ServiceModel.ServiceContractAttribute> und <xref:System.ServiceModel.OperationContractAttribute> auf die Klasse und die Methoden der Klasse liegen in der Geschwindigkeit und der Einfachheit. Die Nachteile liegen darin begründet, dass verwaltete Klassen keine mehrfache Vererbung unterstützen. Als Ergebnis kann immer nur ein Dienstvertrag gleichzeitig implementiert werden. Außerdem ändern alle Modifikationen der Klasse oder Methode den öffentlichen Vertrag für diesen Dienst, der unveränderte Clients daran hindern kann, Ihren Dienst zu verwenden. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Implementieren von Dienstverträgen](../../../docs/framework/wcf/implementing-service-contracts.md).  
  
 Ein Beispiel, verwendet eine Klasse, um einen Dienstvertrag zu erstellen und es gleichzeitig implementiert werden, finden Sie unter [Vorgehensweise: Erstellen eines Diensts mit einer Vertragsklasse](../../../docs/framework/wcf/feature-details/how-to-create-a-wcf-contract-with-a-class.md).  
  
 An diesem Punkt sollten Sie den Unterschied zwischen dem Definieren des Dienstvertrags mithilfe einer Schnittstelle und mithilfe einer Klasse kennen. Der nächste Schritt besteht darin, zu entscheiden, welche Daten zwischen einem Dienst und seinen Clients hin- und herübergeben werden können.  
  
## <a name="parameters-and-return-values"></a>Parameter und Rückgabewerte  
 Jeder Vorgang verfügt über einen Rückgabewert und einen Parameter, auch wenn diese `void` sind. Im Gegensatz zu einer lokalen Methode, in der Sie Verweise auf Objekte von einem Objekt zu einem anderen übergeben können, werden bei Dienstvorgängen keine Verweise auf Objekte übergeben. Stattdessen werden Kopien der Objekte übergeben.  
  
 Das ist wichtig, da jeder in einem Parameter oder einem Rückgabewert verwendete Typ serialisiert werden muss. Das bedeutet, dass es möglich sein muss, ein Objekt dieses Typs in einen Datenstrom und einen Datenstrom in ein Objekt umzuwandeln.  
  
 Primitive Typen sind standardmäßig, wie viele Typen in .NET Framework, serialisierbar.  
  
> [!NOTE]
>  Der Wert der Parameternamen in der Vorgangssignatur ist Teil des Vertrags, und die Groß- und Kleinschreibung wird beachtet. Wenn Sie denselben Parameternamen lokal verwenden, aber den Namen in den veröffentlichten Metadaten ändern möchten, finden Sie entsprechende Informationen unter <xref:System.ServiceModel.MessageParameterAttribute?displayProperty=nameWithType>.  
  
#### <a name="data-contracts"></a>Datenverträge  
 Dienstorientierte Anwendungen wie [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]-Anwendungen wurden entwickelt, um mit einer möglichst großen Anzahl von Clientanwendungen auf Microsoft- und Nicht-Microsoft-Plattformen verwendet werden zu können. Für die höchstmögliche Interoperabilität sollten Sie Ihre Typen mit dem <xref:System.Runtime.Serialization.DataContractAttribute>- und dem <xref:System.Runtime.Serialization.DataMemberAttribute>-Attribut markieren, um einen Datenvertrag zu erstellen, der dem Teil des Dienstvertrags entspricht, der die Daten beschreibt, die durch die Dienstvorgänge ausgetauscht werden.  
  
 Datenverträge sind Abonnementverträge: Es werden keine Typen- oder Datenmitglieder serialisiert, es sei denn, Sie wenden das Datenvertragsattribut ausdrücklich an. Datenverträge stehen nicht mit dem Zugriffsumfang des verwalteten Codes in Verbindung: Private Datenmitglieder können serialisiert und für den öffentlichen Zugriff an einen beliebigen Ort gesendet werden. (Ein einfaches Beispiel einen Datenvertrag, finden Sie unter [Vorgehensweise: Erstellen eines grundlegenden Datenvertrags für eine Klasse oder Struktur](../../../docs/framework/wcf/feature-details/how-to-create-a-basic-data-contract-for-a-class-or-structure.md).) [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] behandelt, die Definition der zugrunde liegenden SOAP-Nachrichten, die Funktionalität des Vorgangs zu ermöglichen als auch für die Serialisierung von Datentypen in und aus dem Text der Nachrichten. Solange Ihre Datentypen serialisierbar sind, müssen Sie sich beim Erstellen von Vorgängen keine Gedanken über die zugrunde liegende Meldungsaustauschinfrastruktur machen.  
  
 Obwohl die typische [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Anwendung die <xref:System.Runtime.Serialization.DataContractAttribute>- und <xref:System.Runtime.Serialization.DataMemberAttribute>-Attribute zum Erstellen von Datenverträgen für Vorgänge verwendet, können Sie auch andere Serialisierungsmechanismen verwenden. Die standardmäßigen <xref:System.Runtime.Serialization.ISerializable>, <xref:System.SerializableAttribute> und <xref:System.Xml.Serialization.IXmlSerializable>-Mechanismen können alle zum Serialisieren Ihrer Datentypen in den zugrunde liegenden SOAP-Meldungen verwendet werden, durch die sie von einer Anwendung zu einer anderen transportiert werden. Sie können weitere Serialisierungsstrategien anwenden, wenn die Datentypen spezielle Unterstützung benötigen. [!INCLUDE[crabout](../../../includes/crabout-md.md)]die Optionen für die Serialisierung von Datentypen in [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] -Anwendungen finden Sie unter [angeben von Datenübertragung in Dienstverträgen](../../../docs/framework/wcf/feature-details/specifying-data-transfer-in-service-contracts.md).  
  
#### <a name="mapping-parameters-and-return-values-to-message-exchanges"></a>Zuordnen von Parametern und Rückgabewerten zu Nachrichtenaustauschvorgängen  
 Dienstvorgänge werden von einem zugrunde liegenden Austausch von SOAP-Meldungen unterstützt, die Anwendungsdaten hin- und herübertragen, zusätzlich zu den Daten, die die Anwendung benötigt, um bestimmte standardmäßige Sicherheits-, Transaktions- und Sitzungsfunktionen zu unterstützen. Da dies der Fall ist, bestimmt die Signatur eines Dienstvorgangs, ein bestimmtes zugrunde liegendes *Nachrichtenaustauschmuster* (MEP), die die Datenübertragung und die Funktionen, die ein Vorgang erfordert unterstützen können. Sie können drei Muster im [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Programmiermodell angeben: Anforderung/Antwort, unidirektional und Duplex-Nachrichtenmuster.  
  
##### <a name="requestreply"></a>Anforderung/Antwort  
 Anforderung/Antwort ist ein Muster, in dem ein Anforderungssender (eine Clientanwendung) eine Antwort empfängt, mit der die Anfrage kombiniert wird. Dabei handelt es sich um das standardmäßige Meldungsaustauschmuster, da es einen Vorgang unterstützt, in dem mindestens ein Parameter an den Vorgang übergeben und ein Rückgabewert zurück an den Aufrufer übergeben wird. Das folgende C#-Codebeispiel zeigt einen einfachen Dienstvorgang, der eine Zeichenfolge als Parameter akzeptiert und eine Zeichenfolge zurückgibt:  
  
```csharp  
[OperationContractAttribute]  
string Hello(string greeting);  
```  
  
 Im Folgenden sehen Sie den entsprechenden Visual Basic-Code:  
  
```vb  
<OperationContractAttribute()>  
Function Hello (ByVal greeting As String) As String  
```  
  
 Diese Vorgangssignatur schreibt die Form des zugrunde liegenden Meldungsaustauschs vor. Wenn keine Korrelation vorhanden wäre, könnte [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] nicht ermitteln, für welchen Vorgang der Rückgabewert vorgesehen ist.  
  
 Beachten Sie, dass, falls Sie kein anderes zugrunde liegendes Meldungsmuster angeben, auch Dienstvorgänge, die `void` (`Nothing` in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) zurückgeben, Anforderungs-/Antwort-Meldungsaustauschvorgängen entsprechen. Als Ergebnis für Ihren Vorgang folgt daraus, dass der Client, falls er den Vorgang nicht asynchron aufruft, die Verarbeitung anhält, bis die Antwortmeldung empfangen wird, auch wenn diese Meldung normalerweise leer ist. Das folgende C#-Codebeispiel zeigt einen Vorgang, der erst zurückgegeben wird, wenn der Client als Antwort eine leere Meldung empfangen hat:  
  
```csharp  
[OperationContractAttribute]  
void Hello(string greeting);  
```  
  
 Im Folgenden sehen Sie den entsprechenden Visual Basic-Code:  
  
```vb  
<OperationContractAttribute()>  
Sub Hello (ByVal greeting As String)  
```  
  
 Das vorherige Beispiel kann die Clientleistung und die Antwortzeit verschlechtern, wenn der Vorgang lange Zeit dauert. Anforderungs-/Antwort-Vorgänge haben aber selbst dann Vorteile, wenn sie `void` zurückgeben. Der offensichtlichste Vorteil besteht darin, dass SOAP-Fehler in der Antwortnachricht zurückgegeben werden können, die anzeigen, dass in der Kommunikation oder Verarbeitung dienstbedingte Fehlerbedingungen eingetreten sind. SOAP-Fehler, die in einem Dienstvertrag angegeben werden, werden der Clientanwendung als <xref:System.ServiceModel.FaultException%601>-Objekte übergeben, wobei der Typparameter dem im Dienstvertrag angegebenen Typ entspricht. Dies vereinfacht das Benachrichtigen von Clients über Fehlerbedingungen in [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Diensten. [!INCLUDE[crabout](../../../includes/crabout-md.md)]Ausnahmen, SOAP-Fehlern und Fehlerbehandlung finden Sie unter [angeben und Behandeln von Fehlern in Verträgen und Diensten](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md). Ein Beispiel für eine Anforderung/Antwort-Dienst und Client finden Sie unter [Vorgehensweise: Erstellen Sie einen Anforderung-Antwort-Vertrag](../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md). [!INCLUDE[crabout](../../../includes/crabout-md.md)]Probleme mit der Anforderung-Antwort-Muster finden Sie unter [Anforderung-Antwort-Dienste](../../../docs/framework/wcf/feature-details/request-reply-services.md).  
  
##### <a name="one-way"></a>Unidirektional  
 Wenn der Client einer [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienstanwendung nicht auf die Beendigung des Vorgangs warten soll und keine SOAP-Fehler verarbeitet, kann ein unidirektionales Nachrichtenmuster angegeben werden. In einem unidirektionalen Vorgang ruft ein Client einen Vorgang auf und fährt mit der Verarbeitung fort, nachdem [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] die Meldung ins Netzwerk geschrieben hat. Normalerweise bedeutet dies, dass der Client die Ausführung fast unverzüglich fortsetzt, sofern die in der ausgehenden Nachricht enthaltene Datenmenge nicht übermäßig groß ist (und sofern beim Senden der Daten kein Fehler auftritt). Dieser Typ des Nachrichtenaustauschmusters unterstützt ereignisähnliches Verhalten gegenüber einem Client zu einer Dienstanwendung.  
  
 Ein Meldungsaustausch, in dem eine Meldung gesendet und keine empfangen wird, kann keinen Dienstvorgang unterstützen, der einen anderen Rückgabewert als `void` angibt. In diesem Fall wird eine <xref:System.InvalidOperationException>-Ausnahme ausgelöst.  
  
 Eine fehlende Rückgabemeldung bedeutet außerdem, dass keine SOAP-Fehler zurückgegeben werden können, um Fehler bei Bearbeitung und Kommunikation anzuzeigen. (Kommunizieren von Fehlerinformationen bei unidirektionalen Vorgängen erfordert ein Duplex-Meldungsaustauschmuster.)  
  
 Um einen unidirektionalen Meldungsaustausch für einen Vorgang anzugeben, der `void` zurückgibt, legen Sie die <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A>-Eigenschaft auf `true` fest, wie im folgenden C#-Codebeispiel gezeigt:  
  
```csharp  
[OperationContractAttribute(IsOneWay=true)]  
void Hello(string greeting);  
```  
  
 Im Folgenden sehen Sie den entsprechenden Visual Basic-Code:  
  
```vb  
<OperationContractAttribute(IsOneWay := True)>  
Sub Hello (ByVal greeting As String)  
```  
  
 Diese Methode ist mit dem vorherigen Anforderungs-/Antwortbeispiel identisch, aber das Festlegen der <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A>-Eigenschaft auf `true` bedeutet, dass der Dienstvorgang, obwohl die Methode identisch ist, keine Rückgabemeldung sendet und Clients unverzüglich zurückgegeben werden, sobald die ausgehende Meldung der Kanalebene übergeben wurde. Ein Beispiel finden Sie unter [Vorgehensweise: Erstellen eines unidirektionalen Vertrags](../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md). [!INCLUDE[crabout](../../../includes/crabout-md.md)]das unidirektionale Muster finden Sie unter [unidirektionaler Services](../../../docs/framework/wcf/feature-details/one-way-services.md).  
  
##### <a name="duplex"></a>Duplex  
 Ein Duplexmuster wird durch die Fähigkeit des Diensts und des Clients zum unabhängigen Senden von Nachrichten untereinander charakterisiert, wenn unidirektionale oder Anforderungs-/Antwortmeldungen verwendet werden. Diese Form einer bidirektionalen Kommunikation ist für Dienste nützlich, die direkt mit dem Client kommunizieren müssen, oder zum Bereitstellen einer asynchronen Erfahrung auf beiden Seiten eines Nachrichtenaustauschs, einschließlich ereignisähnlichen Verhaltens.  
  
 Das Duplexmuster ist aufgrund der zusätzlichen Mechanismen für die Kommunikation mit dem Client etwas komplexer als das Anforderungs-/Antwortmuster und das unidirektionale Muster.  
  
 Für einen Duplexvertrag müssen Sie auch einen Rückrufvertrag entwerfen und den Typ dieses Rückrufvertrags der <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A>-Eigenschaft des <xref:System.ServiceModel.ServiceContractAttribute>-Attributs zuweisen, das den Dienstvertrag markiert.  
  
 Zum Implementieren eines Duplexmusters müssen Sie eine zweite Schnittstelle erstellen, die die Methodendeklarierungen enthält, die auf dem Client aufgerufen werden.  
  
 [!INCLUDE[crexample](../../../includes/crexample-md.md)]Erstellen einen Dienst und einen Client, der diesen Dienst greift auf finden Sie unter [Vorgehensweise: Erstellen eines Duplexvertrags](../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md) und [Vorgehensweise: Access Services mit einem Duplexvertrag](../../../docs/framework/wcf/feature-details/how-to-access-services-with-a-duplex-contract.md). Ein funktionierendes Beispiel finden Sie unter [Duplex](../../../docs/framework/wcf/samples/duplex.md). [!INCLUDE[crabout](../../../includes/crabout-md.md)]Probleme beim Verwenden von Duplexverträgen dazu finden Sie unter [Duplexdienste](../../../docs/framework/wcf/feature-details/duplex-services.md).  
  
> [!CAUTION]
>  Wenn ein Dienst eine Duplexmeldung empfängt, überprüft er das `ReplyTo`-Element in dieser eingehenden Meldung, um zu bestimmen, wohin die Antwort gesendet werden soll. Wenn der zum Empfangen der Meldung verwendete Kanal nicht gesichert ist, kann ein nicht vertrauenswürdiger Client eine bösartige Meldung mit dem `ReplyTo`-Element eines Zielcomputers senden, was zu einem Denial Of Service (DOS) auf diesem Zielcomputer führt.  
  
##### <a name="out-and-ref-parameters"></a>Out-Parameter und Ref-Parameter  
 In den meisten Fällen können Sie `in`-Parameter (`ByVal` in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) und `out`- sowie `ref`-Parameter (`ByRef` in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) verwenden. Da die `out`- und `ref`-Parameter anzeigen, dass Daten aus einem Vorgang zurückgegeben werden, gibt eine Vorgangssignatur wie die folgende an, dass ein Anforderungs-/Antwortvorgang erforderlich ist, obwohl die Vorgangssignatur `void` zurückgibt.  
  
```csharp  
[ServiceContractAttribute]  
public interface IMyContract  
{  
  [OperationContractAttribute]  
  public void PopulateData(ref CustomDataType data);  
}  
```  
  
 Im Folgenden sehen Sie den entsprechenden Visual Basic-Code:  
  
```vb  
<ServiceContractAttribute()> _  
Public Interface IMyContract  
  <OperationContractAttribute()> _  
  Public Sub PopulateData(ByRef data As CustomDataType)  
End Interface  
```  
  
 Die einzigen Ausnahmen sind jene Fälle, in denen die Signatur über eine besondere Struktur verfügt. Sie können beispielsweise die <xref:System.ServiceModel.NetMsmqBinding>-Bindung nur dann zum Kommunizieren mit Clients verwenden, wenn die zum Deklarieren eines Vorgangs verwendete Methode `void` zurückgibt. Es dürfen keine Ausgabewerte vorliegen, weder ein Rückgabewert noch ein `ref`-Parameter oder ein `out`-Parameter.  
  
 Außerdem ist bei der Verwendung der `out`- und `ref`-Parameter erforderlich, dass der Vorgang über eine zugrunde liegende Antwortmeldung verfügt, um das geänderte Objekt zurückzugeben. Wenn es sich bei dem Vorgang um einen unidirektionalen Vorgang handelt, wird zur Laufzeit eine Ausnahme des Typs <xref:System.InvalidOperationException> ausgelöst.  
  
### <a name="specify-message-protection-level-on-the-contract"></a>Angeben einer Meldungsschutzebene für den Vertrag  
 Wenn Sie den Vertrag entwerfen, müssen Sie sich außerdem für eine Meldungsschutzebene für Dienste entscheiden, die den Vertrag implementieren. Dies ist nur notwendig, wenn Meldungssicherheit auf die Bindung im Endpunkt des Vertrags angewendet wird. Wenn die Sicherheit für die Bindung deaktivert wurde (wenn also die vom System bereitgestellte Bindung den <xref:System.ServiceModel.SecurityMode?displayProperty=nameWithType> auf den Wert <xref:System.ServiceModel.SecurityMode.None?displayProperty=nameWithType> festlegt), müssen Sie sich nicht für eine Meldungsschutzebene für den Vertrag entscheiden. In den meisten Fällen bieten vom System bereitgestellte Bindungen mit angewendeter Sicherheit auf Nachrichtenebenen eine ausreichende Schutzebene, sodass Sie sich nicht bei jedem Vorgang oder jeder Nachricht Gedanken um die Schutzebene machen müssen.  
  
 Die Schutzebene ist ein Wert, der angibt, ob die Meldungen (oder Meldungsteile), die einen Dienst unterstützen, signiert, signiert und verschlüsselt oder ohne Signaturen und Verschlüsselung gesendet werden. Die Schutzebene kann in unterschiedlichem Umfang festgelegt werden: auf Dienstebene, für einen bestimmten Vorgang, für eine Meldung innerhalb dieses Vorgangs oder für einen Meldungsteil. Auf einen Bereich festgelegte Werte werden zum Standardwert für kleinere Bereiche, außer wenn diese explizit außer Kraft gesetzt werden. Wenn eine Bindungskonfiguration die erforderliche Mindestschutzebene für den Vertrag nicht bereitstellen kann, wird eine Ausnahme ausgegeben. Wenn für den Vertrag keine Schutzebenenwerte explizit festgelegt sind, steuert die Bindungskonfiguration die Schutzebene für alle Meldungen, sofern die Bindung über Meldungssicherheit verfügt. Dies ist das Standardverhalten.  
  
> [!IMPORTANT]
>  Die Entscheidung über das explizite Festlegen verschiedener Umfänge eines Vertrags auf weniger als die vollständige Schutzebene von <xref:System.Net.Security.ProtectionLevel.EncryptAndSign?displayProperty=nameWithType> ist normalerweise eine Entscheidung, die die Leistung verbessert, während die Sicherheit reduziert wird. In diesen Fällen hängen Ihre Entscheidungen von den Vorgängen und dem Wert der ausgetauschten Daten ab. [!INCLUDE[crdefault](../../../includes/crdefault-md.md)][Sichern von Diensten](../../../docs/framework/wcf/securing-services.md).  
  
 Im folgenden Codebeispiel wird weder die <xref:System.ServiceModel.ServiceContractAttribute.ProtectionLevel%2A>- noch die <xref:System.ServiceModel.OperationContractAttribute.ProtectionLevel%2A>-Eigenschaft für den Vertrag festgelegt.  
  
```csharp  
[ServiceContract]  
public interface ISampleService  
{  
  [OperationContractAttribute]  
  public string GetString();  
  
  [OperationContractAttribute]  
  public int GetInt();    
}  
```  
  
 Im Folgenden sehen Sie den entsprechenden Visual Basic-Code:  
  
```vb  
<ServiceContractAttribute()> _  
Public Interface ISampleService  
  
  <OperationContractAttribute()> _  
  Public Function GetString()As String  
  
  <OperationContractAttribute()> _  
  Public Function GetData() As Integer  
  
End Interface  
```  
  
 Beim Interagieren mit einer `ISampleService`-Implementierung in einem Endpunkt mit einer standardmäßigen <xref:System.ServiceModel.WSHttpBinding> (der standardmäßige <xref:System.ServiceModel.SecurityMode?displayProperty=nameWithType> ist <xref:System.ServiceModel.SecurityMode.Message>) werden alle Meldungen verschlüsselt und signiert, da es sich dabei um die Standardschutzebene handelt. Wenn jedoch ein `ISampleService`-Dienst mit einer standardmäßigen <xref:System.ServiceModel.BasicHttpBinding> verwendet wird (der standardmäßige <xref:System.ServiceModel.SecurityMode> ist <xref:System.ServiceModel.SecurityMode.None>), werden alle Nachrichten als Text gesendet, da es keine Sicherheit für diese Bindung gibt und somit die Schutzebene ignoriert wird (die Nachrichten werden also weder verschlüsselt noch signiert). Würde der <xref:System.ServiceModel.SecurityMode> in <xref:System.ServiceModel.SecurityMode.Message> geändert, würden die Nachrichten verschlüsselt und signiert (da es sich in diesem Fall um die Standardschutzebene der Bindung handeln würde).  
  
 Wenn Sie die Schutzanforderungen für den Vertrag explizit angeben oder anpassen möchten, legen Sie die <xref:System.ServiceModel.ServiceContractAttribute.ProtectionLevel%2A>-Eigenschaft (oder die `ProtectionLevel`-Eigenschaften im kleineren Umfang) auf die für den Dienstvertrag erforderliche Ebene fest. In diesem Fall ist bei der Verwendung einer expliziten Einstellung erforderlich, dass die Bindung diese Einstellung mindestens für den verwendeten Umfang unterstützt. Im folgenden Codebeispiel wird ein <xref:System.ServiceModel.OperationContractAttribute.ProtectionLevel%2A>-Wert explizit für den `GetGuid`-Vorgang angegeben.  
  
```csharp  
[ServiceContract]  
public interface IExplicitProtectionLevelSampleService  
{  
  [OperationContractAttribute]  
  public string GetString();  
  
  [OperationContractAttribute(ProtectionLevel=ProtectionLevel.None)]  
  public int GetInt();    
  [OperationContractAttribute(ProtectionLevel=ProtectionLevel.EncryptAndSign)]  
  public int GetGuid();    
}  
```  
  
 Im Folgenden sehen Sie den entsprechenden Visual Basic-Code:  
  
```vb  
<ServiceContract()> _   
Public Interface IExplicitProtectionLevelSampleService   
    <OperationContract()> _   
    Public Function GetString() As String   
    End Function   
  
    <OperationContract(ProtectionLevel := ProtectionLevel.None)> _   
    Public Function GetInt() As Integer   
    End Function   
  
    <OperationContractAttribute(ProtectionLevel := ProtectionLevel.EncryptAndSign)> _   
    Public Function GetGuid() As Integer   
    End Function   
  
End Interface  
```  
  
 Ein Dienst, der diesen `IExplicitProtectionLevelSampleService`-Vertrag implementiert und über einen Endpunkt verfügt, der die standardmäßige <xref:System.ServiceModel.WSHttpBinding> (der standardmäßige <xref:System.ServiceModel.SecurityMode?displayProperty=nameWithType> ist <xref:System.ServiceModel.SecurityMode.Message>) verwendet, hat das folgende Verhalten:  
  
-   Die `GetString`-Vorgangsmeldungen werden verschlüsselt und signiert.  
  
-   Die `GetInt`-Vorgangsmeldungen werden als unverschlüsselter und unsignierter Text gesendet.  
  
-   Der `GetGuid`-Vorgang <xref:System.Guid?displayProperty=nameWithType> wird in einer Nachricht zurückgegeben, die verschlüsselt und signiert wird.  
  
 [!INCLUDE[crabout](../../../includes/crabout-md.md)]Schutzebenen und deren Verwendung finden Sie in [Verständnis Schutzebene](../../../docs/framework/wcf/understanding-protection-level.md). [!INCLUDE[crabout](../../../includes/crabout-md.md)]Sicherheit, finden Sie unter [Sichern von Services](../../../docs/framework/wcf/securing-services.md).  
  
##### <a name="other-operation-signature-requirements"></a>Andere Vorgangssignaturanforderungen  
 Einige Anwendungsfunktionen erfordern eine besondere Art von Vorgangssignatur. Die <xref:System.ServiceModel.NetMsmqBinding>-Bindung unterstützt beispielsweise permanente Dienste und Clients, in denen eine Anwendung während der Kommunikation neu gestartet und ohne Meldungsverlust genau dort fortgesetzt werden kann, wo sie angehalten wurde. ([!INCLUDE[crdefault](../../../includes/crdefault-md.md)] [Warteschlangen in WCF](../../../docs/framework/wcf/feature-details/queues-in-wcf.md).) Permanente Vorgänge dürfen allerdings nur einen `in`-Parameter verwenden und haben keinen Rückgabewert.  
  
 Ein anderes Beispiel ist die Verwendung von <xref:System.IO.Stream>-Typen in Vorgängen. Da der <xref:System.IO.Stream>-Parameter den gesamten Textinhalt einschließt, muss es sich bei einer Ein- oder Ausgabe mit den Parametern `ref`, `out` oder einem Rückgabewert vom Typ <xref:System.IO.Stream> um die einzigen im Vorgang angegebenen Ein- und Ausgaben handeln. Außerdem muss es sich bei dem Parameter oder dem Rückgabetyp um <xref:System.IO.Stream>, <xref:System.ServiceModel.Channels.Message?displayProperty=nameWithType> oder <xref:System.Xml.Serialization.IXmlSerializable?displayProperty=nameWithType> handeln. [!INCLUDE[crabout](../../../includes/crabout-md.md)]Streams, finden Sie unter [umfangreiche Daten und Streaming](../../../docs/framework/wcf/feature-details/large-data-and-streaming.md).  
  
##### <a name="names-namespaces-and-obfuscation"></a>Namen, Namespaces und Obfuskation  
 Die Namen und Namespaces der .NET-Typen in der Definition von Verträgen und Vorgängen sind wichtig, wenn Verträge in WSDL konvertiert und wenn Vertragsnachrichten erstellt und gesendet werden. Aus diesem Grund sollten Namen und Namespaces von Verträgen unbedingt explizit mithilfe der `Name`- und der `Namespace`-Eigenschaft aller unterstützenden Vertragsattribute (wie <xref:System.ServiceModel.ServiceContractAttribute>, <xref:System.ServiceModel.OperationContractAttribute>, <xref:System.Runtime.Serialization.DataContractAttribute>, <xref:System.Runtime.Serialization.DataMemberAttribute> und anderer Vertragsattribute) festgelegt werden.  
  
 Sind die Namen und Namespaces nicht explizit festgelegt, verändert die Verwendung der IL-Obfuskation für die Assembly die Namen und Namespaces des Vertragstyps. Dadurch ergeben sich Änderungen beim WSDL- und Übertragungsaustausch, wodurch üblicherweise Fehler auftreten. Wenn Sie die Vertragsnamen und -Namespaces nicht explizit festlegen, aber dennoch das Verbergen verwenden möchten, unterbinden Sie Änderungen an den Namen und Namespaces des Vertragstyps mithilfe des <xref:System.Reflection.ObfuscationAttribute>-Attributs und des <xref:System.Reflection.ObfuscateAssemblyAttribute>-Attributs.  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Erstellen eines Anforderung-Antwort-Vertrags](../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md)  
 [Vorgehensweise: Erstellen eines unidirektionalen Vertrags](../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md)  
 [Vorgehensweise: Erstellen eines Duplexvertrags](../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)  
 [Angeben von Datenübertragung in Dienstverträgen](../../../docs/framework/wcf/feature-details/specifying-data-transfer-in-service-contracts.md)  
 [Angeben und Behandeln von Fehlern in Verträgen und Diensten](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)  
 [Verwenden von Sitzungen](../../../docs/framework/wcf/using-sessions.md)  
 [Synchrone und asynchrone Vorgänge](../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md)  
 [Zuverlässige Dienste](../../../docs/framework/wcf/reliable-services.md)  
 [Dienste und Transaktionen](../../../docs/framework/wcf/services-and-transactions.md)
