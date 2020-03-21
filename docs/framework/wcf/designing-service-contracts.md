---
title: Entwerfen von Dienstverträgen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- service contracts [WCF]
ms.assetid: 8e89cbb9-ac84-4f0d-85ef-0eb6be0022fd
ms.openlocfilehash: 37723011d69e8ea2ead3f7a30a30898dede054cb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176681"
---
# <a name="designing-service-contracts"></a>Entwerfen von Dienstverträgen
In diesem Thema wird erläutert, was Dienstverträge sind, wie sie definiert werden, welche Vorgänge verfügbar sind (und die Implikationen des zugrunde liegenden Meldungsaustauschs), welche Datentypen verwendet werden sowie andere Aspekte, die Sie beim Entwerfen von Vorgängen unterstützen, die den Anforderungen Ihres Szenarios gerecht werden.  
  
## <a name="creating-a-service-contract"></a>Erstellen eines Dienstvertrags  
 Dienste machen eine Reihe von Vorgängen verfügbar. Definieren Sie in Windows Communication Foundation (WCF)-Anwendungen die Vorgänge, indem Sie eine Methode erstellen und mit dem <xref:System.ServiceModel.OperationContractAttribute> Attribut markieren. Zum Erstellen eines Dienstvertrags gruppieren Sie dann die Vorgänge, indem Sie sie in einer Schnittstelle deklarieren, die mit dem <xref:System.ServiceModel.ServiceContractAttribute>-Attribut markiert wurde, oder indem Sie sie in einer Klasse definieren, die mit dem gleichen Attribut markiert wurde. (Ein einfaches Beispiel finden Sie unter [Gewusst wie: Definieren eines Servicevertrags](how-to-define-a-wcf-service-contract.md).)  
  
 Alle Methoden, die <xref:System.ServiceModel.OperationContractAttribute> kein Attribut haben, sind keine Dienstvorgänge und werden nicht von WCF-Diensten verfügbar gemacht.  
  
 In diesem Thema werden die folgenden Entscheidungspunkte beschrieben, wenn ein Dienstvertrag entworfen wird:  
  
- Ob Klassen oder Schnittstellen verwendet werden sollen  
  
- Wie die Datentypen angegeben werden, die Sie austauschen möchten  
  
- Die Typen von Austauschmustern, die Sie verwenden können  
  
- Ob Sie einen expliziten Sicherheitsanforderungen-Teil des Vertrags erstellen können  
  
- Die Einschränkungen für Vorgangseingaben und -ausgaben  
  
## <a name="classes-or-interfaces"></a>Klassen oder Schnittstellen  
 Sowohl Klassen als auch Schnittstellen stellen eine Gruppierung von Funktionen dar, und daher können beide verwendet werden, um einen WCF-Dienstvertrag zu definieren. Es wird allerdings empfohlen, Schnittstellen zu verwenden, da sie Dienstverträge direkt modellieren. Ohne Implementierung definieren Schnittstellen lediglich eine Gruppierung von Methoden mit bestimmten Signaturen. Implementieren Sie eine Dienstvertragsschnittstelle, und Sie haben einen WCF-Dienst implementiert.  
  
 Dienstvertragsschnittstellen bieten dieselben Vorteile wie verwaltete Schnittstellen:  
  
- Dienstvertragsschnittstellen können jede Anzahl anderer Dienstvertragsschnittstellen erweitern.  
  
- Eine einzelne Klasse kann jede Anzahl von Dienstverträgen implementieren, indem sie diese Dienstvertragsschnittstelle implementiert.  
  
- Sie können die Implementierung eines Dienstvertrags bearbeiten, indem Sie die Schnittstellenimplementierung ändern, während der Dienstvertrag unverändert bleibt.  
  
- Sie können verschiedene Versionen eines Diensts erstellen, indem Sie die alte und die neue Schnittstelle implementieren. Alte Clients stellen eine Verbindung mit der ursprünglichen Version her, während neuere Clients eine Verbindung mit der neuen Version herstellen können.  
  
> [!NOTE]
> Bei der Vererbung von anderen Dienstvertragsschnittstellen können Sie Vorgangseigenschaften, wie z. B. den Name und den Namespace, nicht außer Kraft setzen. Wenn Sie dies dennoch versuchen, erstellen Sie im aktuellen Dienstvertrag einen neuen Vorgang.  
  
 Ein Beispiel für die Verwendung einer Schnittstelle zum Erstellen eines Servicevertrags finden Sie unter [Gewusst wie: Erstellen eines Dienstes mit einer Vertragsschnittstelle](./feature-details/how-to-create-a-service-with-a-contract-interface.md).  
  
 Sie können allerdings eine Klasse verwenden, um einen Dienstvertrag zu definieren und gleichzeitig zu implementieren. Der Vorteil des Erstellens Ihrer Dienste durch direktes Anwenden von <xref:System.ServiceModel.ServiceContractAttribute> und <xref:System.ServiceModel.OperationContractAttribute> auf die Klasse und die Methoden der Klasse liegen in der Geschwindigkeit und der Einfachheit. Die Nachteile liegen darin begründet, dass verwaltete Klassen keine mehrfache Vererbung unterstützen. Als Ergebnis kann immer nur ein Dienstvertrag gleichzeitig implementiert werden. Außerdem ändern alle Modifikationen der Klasse oder Methode den öffentlichen Vertrag für diesen Dienst, der unveränderte Clients daran hindern kann, Ihren Dienst zu verwenden. Weitere Informationen finden Sie unter [Implementieren von Serviceverträgen](implementing-service-contracts.md).  
  
 Ein Beispiel, das eine Klasse zum Erstellen eines Servicevertrags verwendet und gleichzeitig implementiert, finden Sie unter [Gewusst wie: Erstellen eines Dienstes mit einer Vertragsklasse](./feature-details/how-to-create-a-wcf-contract-with-a-class.md).  
  
 An diesem Punkt sollten Sie den Unterschied zwischen dem Definieren des Dienstvertrags mithilfe einer Schnittstelle und mithilfe einer Klasse kennen. Der nächste Schritt besteht darin, zu entscheiden, welche Daten zwischen einem Dienst und seinen Clients hin- und herübergeben werden können.  
  
## <a name="parameters-and-return-values"></a>Parameter und Rückgabewerte  
 Jeder Vorgang verfügt über einen Rückgabewert und einen Parameter, auch wenn diese `void` sind. Im Gegensatz zu einer lokalen Methode, in der Sie Verweise auf Objekte von einem Objekt zu einem anderen übergeben können, werden bei Dienstvorgängen keine Verweise auf Objekte übergeben. Stattdessen werden Kopien der Objekte übergeben.  
  
 Das ist wichtig, da jeder in einem Parameter oder einem Rückgabewert verwendete Typ serialisiert werden muss. Das bedeutet, dass es möglich sein muss, ein Objekt dieses Typs in einen Datenstrom und einen Datenstrom in ein Objekt umzuwandeln.  
  
 Primitive Typen sind standardmäßig, wie viele Typen in .NET Framework, serialisierbar.  
  
> [!NOTE]
> Der Wert der Parameternamen in der Vorgangssignatur ist Teil des Vertrags, und die Groß- und Kleinschreibung wird beachtet. Wenn Sie denselben Parameternamen lokal verwenden, aber den Namen in den veröffentlichten Metadaten ändern möchten, finden Sie entsprechende Informationen unter <xref:System.ServiceModel.MessageParameterAttribute?displayProperty=nameWithType>.  
  
#### <a name="data-contracts"></a>Datenverträge  
 Serviceorientierte Anwendungen wie Windows Communication Foundation (WCF)-Anwendungen sind so konzipiert, dass sie mit einer möglichst großen Anzahl von Clientanwendungen sowohl auf Microsoft- als auch auf Nicht-Microsoft-Plattformen zusammenarbeiten. Für die höchstmögliche Interoperabilität sollten Sie Ihre Typen mit dem <xref:System.Runtime.Serialization.DataContractAttribute>- und dem <xref:System.Runtime.Serialization.DataMemberAttribute>-Attribut markieren, um einen Datenvertrag zu erstellen, der dem Teil des Dienstvertrags entspricht, der die Daten beschreibt, die durch die Dienstvorgänge ausgetauscht werden.  
  
 Datenverträge sind Abonnementverträge: Es werden keine Typen- oder Datenmitglieder serialisiert, es sei denn, Sie wenden das Datenvertragsattribut ausdrücklich an. Datenverträge stehen nicht mit dem Zugriffsumfang des verwalteten Codes in Verbindung: Private Datenmitglieder können serialisiert und für den öffentlichen Zugriff an einen beliebigen Ort gesendet werden. (Ein grundlegendes Beispiel für einen Datenvertrag finden Sie unter [Gewusst wie: Erstellen eines Basisdatenvertrags für eine Klasse oder Struktur](./feature-details/how-to-create-a-basic-data-contract-for-a-class-or-structure.md).) WCF verarbeitet die Definition der zugrunde liegenden SOAP-Meldungen, die die Funktionalität des Vorgangs sowie die Serialisierung Ihrer Datentypen in und aus dem Nachrichtentext ermöglichen. Solange Ihre Datentypen serialisierbar sind, müssen Sie sich beim Erstellen von Vorgängen keine Gedanken über die zugrunde liegende Meldungsaustauschinfrastruktur machen.  
  
 Obwohl die typische WCF-Anwendung die <xref:System.Runtime.Serialization.DataContractAttribute> und <xref:System.Runtime.Serialization.DataMemberAttribute> Attribute verwendet, um Datenverträge für Vorgänge zu erstellen, können Sie andere Serialisierungsmechanismen verwenden. Die standardmäßigen <xref:System.Runtime.Serialization.ISerializable>, <xref:System.SerializableAttribute> und <xref:System.Xml.Serialization.IXmlSerializable>-Mechanismen können alle zum Serialisieren Ihrer Datentypen in den zugrunde liegenden SOAP-Meldungen verwendet werden, durch die sie von einer Anwendung zu einer anderen transportiert werden. Sie können weitere Serialisierungsstrategien anwenden, wenn die Datentypen spezielle Unterstützung benötigen. Weitere Informationen zu den Möglichkeiten für die Serialisierung von Datentypen in WCF-Anwendungen finden Sie unter [Angeben der Datenübertragung in Serviceverträgen](./feature-details/specifying-data-transfer-in-service-contracts.md).  
  
#### <a name="mapping-parameters-and-return-values-to-message-exchanges"></a>Zuordnen von Parametern und Rückgabewerten zu Nachrichtenaustauschvorgängen  
 Dienstvorgänge werden von einem zugrunde liegenden Austausch von SOAP-Meldungen unterstützt, die Anwendungsdaten hin- und herübertragen, zusätzlich zu den Daten, die die Anwendung benötigt, um bestimmte standardmäßige Sicherheits-, Transaktions- und Sitzungsfunktionen zu unterstützen. Da dies der Fall ist, diktiert die Signatur eines Dienstvorgangs ein bestimmtes zugrunde liegendes *Nachrichtenaustauschmuster* (MEP), das die Datenübertragung und die Features unterstützen kann, die ein Vorgang erfordert. Sie können drei Muster im WCF-Programmiermodell angeben: Anforderungs-/Antwort-, einweg- und Duplex-Nachrichtenmuster.  
  
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
  
 Diese Vorgangssignatur schreibt die Form des zugrunde liegenden Meldungsaustauschs vor. Wenn keine Korrelation vorhanden war, kann WCF nicht bestimmen, für welchen Vorgang der Rückgabewert vorgesehen ist.  
  
 Beachten Sie, dass, sofern Sie kein anderes `void` zugrunde`Nothing` liegendes Nachrichtenmuster angeben, sogar Dienstvorgänge, die zurückgegeben werden (in Visual Basic), den Austausch von Ansaglichs-/Antwortnachrichten sind. Als Ergebnis für Ihren Vorgang folgt daraus, dass der Client, falls er den Vorgang nicht asynchron aufruft, die Verarbeitung anhält, bis die Antwortmeldung empfangen wird, auch wenn diese Meldung normalerweise leer ist. Das folgende C#-Codebeispiel zeigt einen Vorgang, der erst zurückgegeben wird, wenn der Client als Antwort eine leere Meldung empfangen hat:  
  
```csharp  
[OperationContractAttribute]  
void Hello(string greeting);  
```  
  
 Im Folgenden sehen Sie den entsprechenden Visual Basic-Code:  
  
```vb  
<OperationContractAttribute()>  
Sub Hello (ByVal greeting As String)  
```  
  
 Das vorherige Beispiel kann die Clientleistung und die Antwortzeit verschlechtern, wenn der Vorgang lange Zeit dauert. Anforderungs-/Antwort-Vorgänge haben aber selbst dann Vorteile, wenn sie `void` zurückgeben. Der offensichtlichste Vorteil besteht darin, dass SOAP-Fehler in der Antwortnachricht zurückgegeben werden können, die anzeigen, dass in der Kommunikation oder Verarbeitung dienstbedingte Fehlerbedingungen eingetreten sind. SOAP-Fehler, die in einem Dienstvertrag angegeben werden, werden der Clientanwendung als <xref:System.ServiceModel.FaultException%601>-Objekte übergeben, wobei der Typparameter dem im Dienstvertrag angegebenen Typ entspricht. Dies erleichtert die Benachrichtigung von Clients über Fehlerbedingungen in WCF-Diensten. Weitere Informationen zu Ausnahmen, SOAP-Fehlern und Fehlerbehandlung finden Sie unter [Angeben und Behandeln von Fehlern in Verträgen und Diensten](specifying-and-handling-faults-in-contracts-and-services.md). Ein Beispiel für einen Anforderungs-/Antwortdienst und -client finden Sie unter [Gewusst wie: Erstellen eines Anforderungs-Antwort-Vertrags](./feature-details/how-to-create-a-request-reply-contract.md). Weitere Informationen zu Problemen mit dem Anforderungsantwortmuster finden Sie unter [Request-Reply Services](./feature-details/request-reply-services.md).  
  
##### <a name="one-way"></a>Unidirektional  
 Wenn der Client einer WCF-Dienstanwendung nicht warten soll, bis der Vorgang abgeschlossen ist, und keine SOAP-Fehler verarbeitet, kann der Vorgang ein einseitiges Nachrichtenmuster angeben. Ein einseitiger Vorgang ist ein Vorgang, bei dem ein Client einen Vorgang aufruft und die Verarbeitung fortsetzt, nachdem WCF die Nachricht in das Netzwerk deschreibe. Normalerweise bedeutet dies, dass der Client die Ausführung fast unverzüglich fortsetzt, sofern die in der ausgehenden Nachricht enthaltene Datenmenge nicht übermäßig groß ist (und sofern beim Senden der Daten kein Fehler auftritt). Dieser Typ des Nachrichtenaustauschmusters unterstützt ereignisähnliches Verhalten gegenüber einem Client zu einer Dienstanwendung.  
  
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
  
 Diese Methode ist mit dem vorherigen Anforderungs-/Antwortbeispiel identisch, aber das Festlegen der <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A>-Eigenschaft auf `true` bedeutet, dass der Dienstvorgang, obwohl die Methode identisch ist, keine Rückgabemeldung sendet und Clients unverzüglich zurückgegeben werden, sobald die ausgehende Meldung der Kanalebene übergeben wurde. Ein Beispiel finden Sie unter [Gewusst wie: Erstellen eines einwegigen Vertrags](./feature-details/how-to-create-a-one-way-contract.md). Weitere Informationen zum einwegwegreichen Muster finden Sie unter [One-Way Services](./feature-details/one-way-services.md).  
  
##### <a name="duplex"></a>Duplex  
 Ein Duplexmuster wird durch die Fähigkeit des Diensts und des Clients zum unabhängigen Senden von Nachrichten untereinander charakterisiert, wenn unidirektionale oder Anforderungs-/Antwortmeldungen verwendet werden. Diese Form einer bidirektionalen Kommunikation ist für Dienste nützlich, die direkt mit dem Client kommunizieren müssen, oder zum Bereitstellen einer asynchronen Erfahrung auf beiden Seiten eines Nachrichtenaustauschs, einschließlich ereignisähnlichen Verhaltens.  
  
 Das Duplexmuster ist aufgrund der zusätzlichen Mechanismen für die Kommunikation mit dem Client etwas komplexer als das Anforderungs-/Antwortmuster und das unidirektionale Muster.  
  
 Für einen Duplexvertrag müssen Sie auch einen Rückrufvertrag entwerfen und den Typ dieses Rückrufvertrags der <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A>-Eigenschaft des <xref:System.ServiceModel.ServiceContractAttribute>-Attributs zuweisen, das den Dienstvertrag markiert.  
  
 Zum Implementieren eines Duplexmusters müssen Sie eine zweite Schnittstelle erstellen, die die Methodendeklarierungen enthält, die auf dem Client aufgerufen werden.  
  
 Ein Beispiel für das Erstellen eines Dienstes und eines Clients, der auf diesen Dienst zugreift, finden Sie unter [Gewusst wie: Erstellen eines Duplexvertrags](./feature-details/how-to-create-a-duplex-contract.md) und [Gewusst wie: Zugreifen auf Dienste mit einem Duplexvertrag](./feature-details/how-to-access-services-with-a-duplex-contract.md). Eine Arbeitsprobe finden Sie unter [Duplex](./samples/duplex.md). Weitere Informationen zu Problemen mit Duplexverträgen finden Sie unter [Duplexdienste](./feature-details/duplex-services.md).  
  
> [!CAUTION]
> Wenn ein Dienst eine Duplexmeldung empfängt, überprüft er das `ReplyTo`-Element in dieser eingehenden Meldung, um zu bestimmen, wohin die Antwort gesendet werden soll. Wenn der zum Empfangen der Meldung verwendete Kanal nicht gesichert ist, kann ein nicht vertrauenswürdiger Client eine bösartige Meldung mit dem `ReplyTo`-Element eines Zielcomputers senden, was zu einem Denial Of Service (DOS) auf diesem Zielcomputer führt.  
  
##### <a name="out-and-ref-parameters"></a>Out-Parameter und Ref-Parameter  
 In den meisten Fällen `in` können`ByVal` Sie Parameter `out` (in Visual Basic) und `ref` Parameter (in`ByRef` Visual Basic) verwenden. Da die `out`- und `ref`-Parameter anzeigen, dass Daten aus einem Vorgang zurückgegeben werden, gibt eine Vorgangssignatur wie die folgende an, dass ein Anforderungs-/Antwortvorgang erforderlich ist, obwohl die Vorgangssignatur `void` zurückgibt.  
  
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
> Die Entscheidung über das explizite Festlegen verschiedener Umfänge eines Vertrags auf weniger als die vollständige Schutzebene von <xref:System.Net.Security.ProtectionLevel.EncryptAndSign?displayProperty=nameWithType> ist normalerweise eine Entscheidung, die die Leistung verbessert, während die Sicherheit reduziert wird. In diesen Fällen hängen Ihre Entscheidungen von den Vorgängen und dem Wert der ausgetauschten Daten ab. Weitere Informationen finden Sie unter [Sichern von Diensten](securing-services.md).  
  
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
  
- Die `GetString`-Vorgangsmeldungen werden verschlüsselt und signiert.  
  
- Die `GetInt`-Vorgangsmeldungen werden als unverschlüsselter und unsignierter Text gesendet.  
  
- Der `GetGuid`-Vorgang <xref:System.Guid?displayProperty=nameWithType> wird in einer Nachricht zurückgegeben, die verschlüsselt und signiert wird.  
  
 Weitere Informationen zu Schutzebenen und deren Verwendung finden Sie unter Verstehen der [Schutzebene](understanding-protection-level.md). Weitere Informationen zur Sicherheit finden Sie unter [Sichern von Diensten](securing-services.md).  
  
##### <a name="other-operation-signature-requirements"></a>Andere Vorgangssignaturanforderungen  
 Einige Anwendungsfunktionen erfordern eine besondere Art von Vorgangssignatur. Die <xref:System.ServiceModel.NetMsmqBinding>-Bindung unterstützt beispielsweise permanente Dienste und Clients, in denen eine Anwendung während der Kommunikation neu gestartet und ohne Meldungsverlust genau dort fortgesetzt werden kann, wo sie angehalten wurde. (Weitere Informationen finden Sie unter [Warteschlangen in WCF](./feature-details/queues-in-wcf.md).) Dauerhafte Vorgänge dürfen jedoch `in` nur einen Parameter annehmen und keinen Rückgabewert aufweisen.  
  
 Ein anderes Beispiel ist die Verwendung von <xref:System.IO.Stream>-Typen in Vorgängen. Da der <xref:System.IO.Stream>-Parameter den gesamten Textinhalt einschließt, muss es sich bei einer Ein- oder Ausgabe mit den Parametern `ref`, `out` oder einem Rückgabewert vom Typ <xref:System.IO.Stream> um die einzigen im Vorgang angegebenen Ein- und Ausgaben handeln. Außerdem muss es sich bei dem Parameter oder dem Rückgabetyp um <xref:System.IO.Stream>, <xref:System.ServiceModel.Channels.Message?displayProperty=nameWithType> oder <xref:System.Xml.Serialization.IXmlSerializable?displayProperty=nameWithType> handeln. Weitere Informationen zu Streams finden Sie unter [Große Daten und Streaming](./feature-details/large-data-and-streaming.md).  
  
##### <a name="names-namespaces-and-obfuscation"></a>Namen, Namespaces und Obfuskation  
 Die Namen und Namespaces der .NET-Typen in der Definition von Verträgen und Vorgängen sind wichtig, wenn Verträge in WSDL konvertiert und wenn Vertragsnachrichten erstellt und gesendet werden. Aus diesem Grund sollten Namen und Namespaces von Verträgen unbedingt explizit mithilfe der `Name`- und der `Namespace`-Eigenschaft aller unterstützenden Vertragsattribute (wie <xref:System.ServiceModel.ServiceContractAttribute>, <xref:System.ServiceModel.OperationContractAttribute>, <xref:System.Runtime.Serialization.DataContractAttribute>, <xref:System.Runtime.Serialization.DataMemberAttribute> und anderer Vertragsattribute) festgelegt werden.  
  
 Sind die Namen und Namespaces nicht explizit festgelegt, verändert die Verwendung der IL-Obfuskation für die Assembly die Namen und Namespaces des Vertragstyps. Dadurch ergeben sich Änderungen beim WSDL- und Übertragungsaustausch, wodurch üblicherweise Fehler auftreten. Wenn Sie die Vertragsnamen und -Namespaces nicht explizit festlegen, aber dennoch die Obfuskation verwenden möchten, unterbinden Sie Änderungen an den Namen und Namespaces des Vertragstyps mithilfe des <xref:System.Reflection.ObfuscationAttribute>-Attributs und des <xref:System.Reflection.ObfuscateAssemblyAttribute>-Attributs.  
  
## <a name="see-also"></a>Weitere Informationen

- [Vorgehensweise: Erstellen eines Anforderung-Antwort-Vertrags](./feature-details/how-to-create-a-request-reply-contract.md)
- [Vorgehensweise: Erstellen eines unidirektionalen Vertrags](./feature-details/how-to-create-a-one-way-contract.md)
- [Vorgehensweise: Erstellen eines Duplexvertrags](./feature-details/how-to-create-a-duplex-contract.md)
- [Specifying Data Transfer in Service Contracts](./feature-details/specifying-data-transfer-in-service-contracts.md)
- [Angeben und Behandeln von Fehlern in Verträgen und Diensten](specifying-and-handling-faults-in-contracts-and-services.md)
- [Verwenden von Sitzungen](using-sessions.md)
- [Synchrone und asynchrone Vorgänge](synchronous-and-asynchronous-operations.md)
- [Zuverlässige Dienstleistungen](reliable-services.md)
- [Dienste und Transaktionen](services-and-transactions.md)
