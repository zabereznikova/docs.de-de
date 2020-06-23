---
title: Verwendung von Nachrichtenverträgen
description: Erfahren Sie, wie Sie mit den Nachrichten Vertrags Attributen einen Nachrichten Vertrag erstellen, der die Struktur einer SOAP-Nachricht in WFC angibt.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- message contracts [WCF]
ms.assetid: 1e19c64a-ae84-4c2f-9155-91c54a77c249
ms.openlocfilehash: 0a75298b50df74ddf15904af43a0eb62c5ba8496
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244711"
---
# <a name="using-message-contracts"></a>Verwendung von Nachrichtenverträgen
Beim Entwickeln von Windows Communication Foundation (WCF)-Anwendungen achten Entwickler in der Regel auf die Datenstrukturen und Serialisierungsprobleme und müssen sich nicht mit der Struktur der Nachrichten befassen, in denen die Daten übertragen werden. Für diese Anwendungen ist die Erstellung von Datenverträgen für die Parameter oder Rückgabewerte ein einfacher Vorgang. (Weitere Informationen finden Sie unter [Angeben von Datenübertragung in Dienstverträgen](specifying-data-transfer-in-service-contracts.md).)  
  
 Allerdings ist zuweilen die vollständige Kontrolle über die Struktur einer SOAP-Nachricht wichtiger als die Kontrolle über dessen Inhalte. Dies gilt insbesondere, wenn Interoperabilität wichtig ist oder um Sicherheitsprobleme speziell auf der Ebene der Nachricht oder des Nachrichtenteils zu kontrollieren. In diesen Fällen können Sie einen *Nachrichten Vertrag* erstellen, der es Ihnen ermöglicht, die Struktur der exakten SOAP-Nachricht anzugeben.  
  
 Dieses Thema beschreibt, wie die unterschiedlichen Attribute für Nachrichtenverträge zur Erstellung eines spezifischen Nachrichtenvertrags für Ihren Vorgang verwendet werden.  
  
## <a name="using-message-contracts-in-operations"></a>Verwenden von Nachrichtenverträgen in Vorgängen  
 WCF unterstützt Vorgänge, die entweder für den *Remote Prozedur Aufruf (RPC)* oder den *Messaging Stil*modelliert wurden. Bei einem Vorgang im RPC-Stil können Sie jeden serialisierbaren Typ verwenden, und Sie haben Zugriff auf die Funktionen, die für lokale Aufrufe verfügbar sind, beispielsweise mehrere Parameter sowie der `ref`-Parameter und der `out`-Parameter. In diesem Stil steuert die gewählte Form der Serialisierung die Struktur der Daten in den zugrunde liegenden Nachrichten, und die WCF-Laufzeit erstellt die Nachrichten, um den Vorgang zu unterstützen. Dadurch können Entwickler, die sich mit SOAP und SOAP-Nachrichten nicht auskennen, Dienstanwendungen schnell und einfach erstellen und verwenden.  
  
 Das folgende Codebeispiel zeigt einen im RPC-Stil erstellten Dienstvorgang.  
  
```csharp  
[OperationContract]  
public BankingTransactionResponse PostBankingTransaction(BankingTransaction bt);  
```  
  
 Normalerweise ist ein Datenvertrag ausreichend, um das Schema für die Nachrichten zu definieren. Beispielsweise reicht es im vorherigen Beispiel für die meisten Anwendungen aus, wenn `BankingTransaction` und `BankingTransactionResponse` über Datenverträge für die Inhaltsdefinition der zugrunde liegenden SOAP-Nachrichten verfügen. Weitere Informationen zu Daten Verträgen finden Sie unter [Verwenden von Daten Verträgen](using-data-contracts.md).  
  
 Zuweilen ist es allerdings notwendig, die Struktur der übertragenen SOAP-Nachricht genau zu steuern. Das gängigste Szenario hierfür besteht aus dem Einfügen von benutzerdefinierten SOAP-Headern. Ein weiteres übliches Szenario ist die Definition von Sicherheitseigenschaften für Nachrichtenheader und -text, das heißt, die Entscheidung, ob diese Elemente digital signiert und verschlüsselt werden. Schließlich erfordern eine Reihe von Drittanbieter-SOAP-Stapeln Nachrichten in einem bestimmten Format. Vorgänge im Messagingstil bieten diese Kontrolle.  
  
 Ein Vorgang im Messagingstil verfügt über höchstens einen Parameter und einen Rückgabewert. Bei beiden Typen handelt es sich um Nachrichtentypen, d. h. sie serialisieren direkt in eine festgelegte SOAP-Nachrichtenstruktur. Hierbei kann es sich um jeden Typ mit der Kennzeichnung <xref:System.ServiceModel.MessageContractAttribute> oder um den <xref:System.ServiceModel.Channels.Message>-Typ handeln. Das folgende Codebeispiel zeigt einen Vorgang, der dem vorangehenden Vorgang im RCP-Stil ähnelt, aber den Messagingstil nutzt.  
  
 Wenn sowohl `BankingTransaction` als auch `BankingTransactionResponse` Typen sind, bei denen es sich um Nachrichtenverträge handelt, ist der Code in den folgenden Vorgängen gültig.  
  
```csharp  
[OperationContract]  
BankingTransactionResponse Process(BankingTransaction bt);  
[OperationContract]  
void Store(BankingTransaction bt);  
[OperationContract]  
BankingTransactionResponse GetResponse();  
```  
  
 Der folgende Code ist allerdings ungültig.  
  
```csharp  
[OperationContract]  
bool Validate(BankingTransaction bt);  
// Invalid, the return type is not a message contract.  
[OperationContract]  
void Reconcile(BankingTransaction bt1, BankingTransaction bt2);  
// Invalid, there is more than one parameter.  
```  
  
 Für jeden Vorgang, der einen Nachrichtenvertragstyp beinhaltet und nicht eines der gültigen Muster einhält, wird eine Ausnahme ausgelöst. Natürlich unterliegen Vorgänge, die keine Nachrichtenvertragstypen einschließen, diesen Einschränkungen nicht.  
  
 Verfügt ein Typ sowohl über einen Nachrichtenvertrag als auch über einen Datenvertrag, wird nur der Nachrichtenvertrag berücksichtigt, wenn der Typ in einem Vorgang zum Einsatz kommt.  
  
## <a name="defining-message-contracts"></a>Definition von Nachrichtenverträgen  
 Zur Definition eines Nachrichtenvertrags für einen Typ (d. h. zur Definition der Zuordnung zwischen Typ und SOAP-Umschlag) wenden Sie <xref:System.ServiceModel.MessageContractAttribute> auf den Typ an. Wenden Sie dann das <xref:System.ServiceModel.MessageHeaderAttribute> auf die Member an, die Sie SOAP-Headern machen möchten, und wenden Sie dann das <xref:System.ServiceModel.MessageBodyMemberAttribute> auf die Member an,die Sie zu Teilen des SOAP-Texts der Nachricht machen möchten.  
  
 Der folgende Code stellt ein Beispiel für die Verwendung eines Nachrichtenvertrags dar.  
  
```csharp  
[MessageContract]  
public class BankingTransaction  
{  
  [MessageHeader] public Operation operation;  
  [MessageHeader] public DateTime transactionDate;  
  [MessageBodyMember] private Account sourceAccount;  
  [MessageBodyMember] private Account targetAccount;  
  [MessageBodyMember] public int amount;  
}  
```  
  
 Bei der Verwendung dieses Typs als Vorgangsparameter wird der folgende SOAP-Umschlag generiert:  
  
```xml  
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
  <s:Header>  
    <h:operation xmlns:h="http://tempuri.org/" xmlns="http://tempuri.org/">Deposit</h:operation>  
    <h:transactionDate xmlns:h="http://tempuri.org/" xmlns="http://tempuri.org/">2012-02-16T16:10:00</h:transactionDate>  
  </s:Header>  
  <s:Body xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
    <BankingTransaction xmlns="http://tempuri.org/">  
      <amount>0</amount>  
      <sourceAccount xsi:nil="true"/>  
      <targetAccount xsi:nil="true"/>  
    </BankingTransaction>  
  </s:Body>  
</s:Envelope>  
```  
  
 Beachten Sie, dass `operation` und `transactionDate` als SOAP-Header angezeigt werden und der SOAP-Text aus dem Wrapperelement `BankingTransaction` besteht, das `sourceAccount`,`targetAccount` und `amount` enthält.  
  
 Sie können <xref:System.ServiceModel.MessageHeaderAttribute> und <xref:System.ServiceModel.MessageBodyMemberAttribute> auf alle Felder, Eigenschaften und Ereignisse anwenden, unabhängig davon, ob diese öffentlich, privat, geschützt oder intern sind.  
  
 Das <xref:System.ServiceModel.MessageContractAttribute> ermöglicht Ihnen das Angeben des WrapperName-Attributs und des WrapperNamespace-Attributs, die den Namen des Wrapperelements im Textkörper der SOAP-Nachricht steuern. Standardmäßig wird der Name des Typs des Nachrichtenvertrags für den Wrapper verwendet, und der Namespace, in dem der Nachrichtenvertrag `http://tempuri.org/` definiert ist, fungiert als Standardnamespace.  
  
> [!NOTE]
> <xref:System.Runtime.Serialization.KnownTypeAttribute>-Attribute werden in Nachrichtenverträgen ignoriert. Ist ein <xref:System.Runtime.Serialization.KnownTypeAttribute> erforderlich, platzieren Sie es auf dem Vorgang, der den in Frage kommenden Nachrichtenvertrag nutzt.  
  
## <a name="controlling-header-and-body-part-names-and-namespaces"></a>Kontrollieren von Header- und Textteilnamen und Namespaces  
 In der SOAP-Darstellung eines Nachrichtenvertrags wird jeder Header und jeder Textteil einem XML-Element zugeordnet, das über einen Namen und einen Namespace verfügt.  
  
 Standardmäßig entspricht der Namespace dem Namespace des Dienstvertrags, an dem die Nachricht teilnimmt, und der Name wird durch den Membernamen festgelegt, auf den die Attribute <xref:System.ServiceModel.MessageHeaderAttribute> oder <xref:System.ServiceModel.MessageBodyMemberAttribute> angewandt wurden.  
  
 Die Standardeinstellungen können Sie ändern, indem Sie <xref:System.ServiceModel.MessageContractMemberAttribute.Name%2A?displayProperty=nameWithType> und <xref:System.ServiceModel.MessageContractMemberAttribute.Namespace%2A?displayProperty=nameWithType> bearbeiten (in der übergeordneten Klasse der Attribute <xref:System.ServiceModel.MessageHeaderAttribute> und <xref:System.ServiceModel.MessageBodyMemberAttribute>).  
  
 Betrachten Sie die Klasse im folgenden Codebeispiel.  
  
```csharp  
[MessageContract]  
public class BankingTransaction  
{  
  [MessageHeader] public Operation operation;  
  [MessageHeader(Namespace="http://schemas.contoso.com/auditing/2005")] public bool IsAudited;  
  [MessageBodyMember(Name="transactionData")] public BankingTransactionData theData;  
}  
```  
  
 In diesem Beispiel befindet sich der `IsAudited`-Header im Namespace, der vom Code festgelegt wird, und der Textteil, der den `theData`-Member darstellt, wird von einem XML-Element mit dem Namen `transactionData` abgebildet. Im Folgenden wird der XML-Code angezeigt, der für diesen Nachrichtenvertrag generiert wird.  
  
```xml  
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
  <s:Header>  
    <h:IsAudited xmlns:h="http://schemas.contoso.com/auditing/2005" xmlns="http://schemas.contoso.com/auditing/2005">false</h:IsAudited>  
    <h:operation xmlns:h="http://tempuri.org/" xmlns="http://tempuri.org/">Deposit</h:operation>  
  </s:Header>  
  <s:Body xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
    <AuditedBankingTransaction xmlns="http://tempuri.org/">  
      <transactionData/>  
    </AuditedBankingTransaction>  
  </s:Body>  
</s:Envelope>  
```  
  
## <a name="controlling-whether-the-soap-body-parts-are-wrapped"></a>Kontrolle, ob die SOAP-Textteile umbrochen werden  
 Standardmäßig sind die SOAP-Textteile in einem umbrochenen Element serialisiert. Beispielsweise zeigt der folgende Code das `HelloGreetingMessage`-Wrapperelement, das aus dem Namen des <xref:System.ServiceModel.MessageContractAttribute>-Typs im Nachrichtenvertrag für die `HelloGreetingMessage`-Nachricht generiert wird.  
  
[!code-csharp[MessageHeaderAttribute#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/messageheaderattribute/cs/services.cs#3)]
[!code-vb[MessageHeaderAttribute#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/messageheaderattribute/vb/services.vb#3)]  
  
 Um das Wrapperelement zu unterdrücken, legen Sie die <xref:System.ServiceModel.MessageContractAttribute.IsWrapped%2A>-Eigenschaft auf `false` fest. Um den Namen und den Namespace des Wrapperelements zu kontrollieren, verwenden Sie die Eigenschaften <xref:System.ServiceModel.MessageContractAttribute.WrapperName%2A> und <xref:System.ServiceModel.MessageContractAttribute.WrapperNamespace%2A>.  
  
> [!NOTE]
> Das Vorhandensein von mehr als einem Nachrichtentextteil in nicht umbrochenen Nachrichten ist nicht mit dem WS-I Basic Profile 1.1 kompatibel und wird bei der Gestaltung neuer Nachrichtenverträge nicht empfohlen. Allerdings kann es bei spezifischen Interoperabilitätsszenarien notwendig sein, mehr als einen nicht umbrochenen Nachrichtentextteil zu haben. Wenn Sie mehrere Daten in einem Nachrichtentext übertragen möchten, wird die Verwendung des Standardumbruchmodus empfohlen. Mehr als einen Nachrichtenheader in nicht umbrochenen Nachrichten zu haben, ist vollkommen akzeptabel.  
  
## <a name="using-custom-types-inside-message-contracts"></a>Verwendung von benutzerdefinierten Typen innerhalb von Nachrichtenverträgen  
 Jeder einzelne Nachrichtenheader und Nachrichtentextteil wird mithilfe der ausgewählten Serialisierungs-Engine für den Dienstvertrag, bei dem die Nachricht verwendet wird, serialisiert (in XML konvertiert). Die Standardserialisierungs-Engine, `XmlFormatter`, kann jeden Typ verarbeiten, der über einen Datenvertrag verfügt; entweder explizit (durch <xref:System.Runtime.Serialization.DataContractAttribute?displayProperty=nameWithType>) oder implizit (bei einem primitiven Typ mit <xref:System.SerializableAttribute?displayProperty=nameWithType> usw.). Weitere Informationen finden Sie unter [Verwenden von Daten Verträgen](using-data-contracts.md).  
  
 Im vorangehenden Beispiel müssen die Typen `Operation` und `BankingTransactionData` über einen Datenvertrag verfügen, und `transactionDate` ist serialisierbar, da <xref:System.DateTime> primitiv ist (und über einen impliziten Datenvertrag verfügt).  
  
 Es ist jedoch möglich, zu einer anderen Serialisierungs-Engine, dem `XmlSerializer`, umzuschalten. Wenn Sie umschalten, sollten Sie sicherstellen, dass alle für die Nachrichtenheader und Textteile verwendeten Typen mithilfe des `XmlSerializer` serialisierbar sind.  
  
## <a name="using-arrays-inside-message-contracts"></a>Verwendung von Arrays innerhalb von Nachrichtenverträgen  
 Sie können Arrays von sich wiederholenden Elementen in Nachrichtenverträgen auf zwei Arten verwenden.  
  
 Auf der einen Seite können Sie ein <xref:System.ServiceModel.MessageHeaderAttribute> oder ein <xref:System.ServiceModel.MessageBodyMemberAttribute> direkt auf dem Array anwenden. In diesem Fall wird das gesamte Array als ein Element (d. h. ein Header und ein Textteil) mit mehreren Unterelementen serialisiert. Betrachten Sie die Klasse im folgenden Beispiel.  
  
```csharp  
[MessageContract]  
public class BankingDepositLog  
{  
  [MessageHeader] public int numRecords;  
  [MessageHeader] public DepositRecord[] records;  
  [MessageHeader] public int branchID;  
}  
```  
  
 Das Ergebnis sind SOAP-Header, die den folgenden Beispielen ähneln.  
  
```xml  
<BankingDepositLog>  
<numRecords>3</numRecords>  
<records>  
  <DepositRecord>Record1</DepositRecord>  
  <DepositRecord>Record2</DepositRecord>  
  <DepositRecord>Record3</DepositRecord>  
</records>  
<branchID>20643</branchID>  
</BankingDepositLog>  
```  
  
 Eine Alternative besteht in der Verwendung des <xref:System.ServiceModel.MessageHeaderArrayAttribute>. In diesem Fall wird jedes Arrayelement unabhängig serialisiert, wobei jedes Arrayelement über einen Header verfügt (ähnlich wie im folgenden Beispiel).  
  
```xml  
<numRecords>3</numRecords>  
<records>Record1</records>  
<records>Record2</records>  
<records>Record3</records>  
<branchID>20643</branchID>  
```  
  
 Der Standardname für Arrayeinträge ist der Name des Members, auf den die <xref:System.ServiceModel.MessageHeaderArrayAttribute>-Attribute angewandt werden.  
  
 Das <xref:System.ServiceModel.MessageHeaderArrayAttribute>-Attribut erbt von <xref:System.ServiceModel.MessageHeaderAttribute>. Es verfügt über denselben Funktionssatz wie die Nicht-Arrayattribute. Beispielsweise ist es möglich, die Reihenfolge, den Namen und den Namespace für ein Array von Headern so einzurichten wie für einen Einzelheader. Wenn Sie die `Order`-Eigenschaft auf ein Array verwenden, gilt dies für das gesamte Array.  
  
 Sie können <xref:System.ServiceModel.MessageHeaderArrayAttribute> nur auf Arrays anwenden, nicht auf Sammlungen.  
  
## <a name="using-byte-arrays-in-message-contracts"></a>Verwendung von Bytearrays in Nachrichtenverträgen  
 Bytearrays werden bei der Verwendung mit Nicht-Arrayattributen (<xref:System.ServiceModel.MessageBodyMemberAttribute> und <xref:System.ServiceModel.MessageHeaderAttribute>) nicht als Arrays behandelt, sondern als spezielle primitive Typen, die als Base64-codierte Daten in der resultierenden XML dargestellt werden.  
  
 Wenn Sie Bytearrays mit dem Arrayattribut <xref:System.ServiceModel.MessageHeaderArrayAttribute> verwenden, hängen die Ergebnisse vom verwendeten Serialisierungsprogramm ab. Mit dem Standardserialisierungsprogramm wird das Array als einzelner Eintrag für jedes Byte dargestellt. Ist allerdings `XmlSerializer` ausgewählt (mithilfe von <xref:System.ServiceModel.XmlSerializerFormatAttribute> auf dem Dienstvertrag), werden Bytearrays als Base64-Daten behandelt, unabhängig davon, ob Array- oder Nicht-Arrayattribute verwendet werden.  
  
## <a name="signing-and-encrypting-parts-of-the-message"></a>Signieren und Verschlüsseln von Teilen der Nachricht  
 Ein Nachrichtenvertrag kann angeben, ob die Header und/oder der Text der Nachricht digital signiert und verschlüsselt werden soll.  
  
 Dies wird erreicht, indem die <xref:System.ServiceModel.MessageContractMemberAttribute.ProtectionLevel%2A?displayProperty=nameWithType>-Eigenschaften in den Attributen <xref:System.ServiceModel.MessageHeaderAttribute> und <xref:System.ServiceModel.MessageBodyMemberAttribute> festgelegt wird. Die Eigenschaft ist eine Enumeration des <xref:System.Net.Security.ProtectionLevel?displayProperty=nameWithType>-Typs und kann auf <xref:System.Net.Security.ProtectionLevel.None> (keine Verschlüsselung oder Signatur), <xref:System.Net.Security.ProtectionLevel.Sign> (nur digitale Signatur) oder <xref:System.Net.Security.ProtectionLevel.EncryptAndSign> (sowohl Verschlüsselung als auch digitale Signatur) festgelegt werden. Der Standardwert ist <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>.  
  
 Damit diese Sicherheitsfunktionen arbeiten, müssen Sie die Bindung und das Verhalten ordnungsgemäß konfigurieren. Wenn Sie diese Sicherheitsfunktionen ohne angemessene Konfiguration verwenden (beispielsweise der Versuch der Signierung einer Nachricht ohne Bereitstellung Ihrer Anmeldeinformationen), wird zum Validierungszeitpunkt eine Ausnahme ausgelöst.  
  
 Bei Nachrichtenheadern wird die Schutzebene für jeden Header einzeln festgelegt.  
  
 Für Nachrichtentextteile kann die Schutzebene als "minimale Schutzebene" angesehen werden. Der Text verfügt jedoch unabhängig von der Anzahl der Textteile nur über eine Schutzebene. Die Schutzebene des Texts wird durch die höchste <xref:System.ServiceModel.MessageContractMemberAttribute.ProtectionLevel%2A>-Eigenschaftseinstellung aller Textteile bestimmt. Allerdings sollten Sie die Schutzebene eines jeden Textteils auf die tatsächlich erforderliche minimale Schutzebene festlegen.  
  
 Betrachten Sie die Klasse im folgenden Codebeispiel.  
  
```csharp  
[MessageContract]  
public class PatientRecord  
{  
   [MessageHeader(ProtectionLevel=None)] public int recordID;  
   [MessageHeader(ProtectionLevel=Sign)] public string patientName;  
   [MessageHeader(ProtectionLevel=EncryptAndSign)] public string SSN;  
   [MessageBodyMember(ProtectionLevel=None)] public string comments;  
   [MessageBodyMember(ProtectionLevel=Sign)] public string diagnosis;  
   [MessageBodyMember(ProtectionLevel=EncryptAndSign)] public string medicalHistory;  
}  
```  
  
 In diesem Beispiel ist der `recordID`-Header nicht geschützt, `patientName` ist `signed` und `SSN` ist verschlüsselt und signiert. Auf mindestens einen Textteil, `medicalHistory`, wurde <xref:System.Net.Security.ProtectionLevel.EncryptAndSign> angewandt. Daher ist der gesamte Nachrichtentext verschlüsselt und signiert, auch wenn die Kommentare und Diagnosetextteile niedrigere Schutzebenen festlegen.  
  
## <a name="soap-action"></a>SOAP-Aktion  
 SOAP- und verwandte Webdienststandards definieren eine Eigenschaft mit dem Namen `Action`, die für jede gesendete SOAP-Nachricht vorhanden sein kann. Die Eigenschaften <xref:System.ServiceModel.OperationContractAttribute.Action%2A?displayProperty=nameWithType> und <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A?displayProperty=nameWithType> des Vorgangs kontrollieren den Wert dieser Eigenschaft.  
  
## <a name="soap-header-attributes"></a>SOAP-Header-Attribute  
 Der SOAP-Standard definiert die folgenden Attribute, die in einem Header verwendet werden können:  
  
- `Actor/Role` (`Actor` in SOAP 1.1, `Role` in SOAP 1.2)  
  
- `MustUnderstand`  
  
- `Relay`  
  
 Das `Actor`-Attribut oder das `Role`-Attribut legt den URI (Uniform Resource Identifier) des Knotens fest, für den ein bestimmter Header angegeben wurde. Das `MustUnderstand`-Attribut gibt an, ob der Header die Knotenverarbeitung versteht. Das `Relay`-Attribut gibt an, ob der Header an Downstreamknoten weitergeleitet werden soll. WCF führt keine Verarbeitung dieser Attribute für eingehende Nachrichten aus, mit Ausnahme des- `MustUnderstand` Attributs, wie im Abschnitt "Versionsverwaltung von Nachrichten Verträgen" weiter unten in diesem Thema angegeben. Allerdings wird es Ihnen ermöglicht, diese Attribute wie erforderlich zu lesen und zu schreiben (wie in der folgenden Beschreibung).  
  
 Beim Versand einer Nachricht werden diese Attribute nicht standardmäßig ausgegeben. Sie können diese auf zwei Arten ändern: Sie können die Attribute statisch auf einen gewünschten Wert festlegen, indem Sie die Eigenschaften <xref:System.ServiceModel.MessageHeaderAttribute.Actor%2A?displayProperty=nameWithType>, <xref:System.ServiceModel.MessageHeaderAttribute.MustUnderstand%2A?displayProperty=nameWithType> und <xref:System.ServiceModel.MessageHeaderAttribute.Relay%2A?displayProperty=nameWithType> ändern (siehe folgendes Codebeispiel). (Beachten Sie, dass es keine `Role`-Eigenschaft gibt; die Einrichtung der <xref:System.ServiceModel.MessageHeaderAttribute.Actor%2A>-Eigenschaft gibt das `Role`-Attribut aus, wenn Sie SOAP 1.2 verwenden).  
  
```csharp  
[MessageContract]  
public class BankingTransaction  
{  
  [MessageHeader(Actor="http://auditingservice.contoso.com", MustUnderstand=true)] public bool IsAudited;  
  [MessageHeader] public Operation operation;  
  [MessageBodyMember] public BankingTransactionData theData;  
}  
```  
  
 Darüber hinaus können Sie diese Attribute dynamisch per Code kontrollieren. Dies können Sie erreichen, indem Sie den gewünschten Headertyp im <xref:System.ServiceModel.MessageHeader%601>-Typ umschließen (nicht mit dem nichtgenerischen Typ zu verwechseln) und den Typ zusammen mit dem <xref:System.ServiceModel.MessageHeaderAttribute> verwenden. Daraufhin können Sie die Eigenschaften auf <xref:System.ServiceModel.MessageHeader%601> nutzen, um die SOAP-Attribute einzurichten (siehe folgendes Codebeispiel).  
  
```csharp  
[MessageContract]  
public class BankingTransaction  
{  
  [MessageHeader] public MessageHeader<bool> IsAudited;  
  [MessageHeader] public Operation operation;  
  [MessageBodyMember] public BankingTransactionData theData;  
}  
// application code:  
BankingTransaction bt = new BankingTransaction();  
bt.IsAudited = new MessageHeader<bool>();  
bt.IsAudited.Content = false; // Set IsAudited header value to "false"  
bt.IsAudited.Actor="http://auditingservice.contoso.com";  
bt.IsAudited.MustUnderstand=true;  
```  
  
 Wenn Sie sowohl den dynamischen als auch den statischen Kontrollmechanismus verwenden, werden die statischen Einstellungen als Standard verwendet, wobei diese später allerdings mithilfe des dynamischen Mechanismus überschrieben werden können (siehe folgenden Code).  
  
```csharp  
[MessageHeader(MustUnderstand=true)] public MessageHeader<Person> documentApprover;  
// later on in the code:  
BankingTransaction bt = new BankingTransaction();  
bt.documentApprover = new MessageHeader<Person>();  
bt.documentApprover.MustUnderstand = false; // override the static default of 'true'  
```  
  
 Das Erstellen von wiederholten Headern mit einem dynamischen Attributsteuerelement ist zulässig (siehe folgenden Code).  
  
```csharp  
[MessageHeaderArray] public MessageHeader<Person> documentApprovers[];  
```  
  
 Wenn Sie diese SOAP-Attribute auf Empfängerseite lesen möchten, muss die <xref:System.ServiceModel.MessageHeader%601>-Klasse für den Header im Typ verwendet werden. Überprüfen Sie die Eigenschaften `Actor`, `Relay` oder `MustUnderstand` des Headers des <xref:System.ServiceModel.MessageHeader%601>-Typs, um die Attributeinstellungen für die empfangene Nachricht anzuzeigen.  
  
 Wenn eine Nachricht empfangen und dann zurückgesendet wird, werden die SOAP-Attributeinstellungen nur für Header des <xref:System.ServiceModel.MessageHeader%601>-Typs wiederhergestellt.  
  
## <a name="order-of-soap-body-parts"></a>Reihenfolge von SOAP-Textteilen  
 In einigen Fällen müssen Sie die Reihenfolge der Textteile kontrollieren. Die Reihenfolge der Textelemente ist standardmäßig alphabetisch, kann aber über die <xref:System.ServiceModel.MessageBodyMemberAttribute.Order%2A?displayProperty=nameWithType>-Eigenschaft gesteuert werden. Diese Eigenschaft verfügt über dieselbe Semantik wie die Eigenschaft <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A?displayProperty=nameWithType>, abgesehen vom Verhalten im Vererbungsszenario (in Nachrichtenverträgen werden Textmember vom Basistyp nicht vor den Textmembern des abgeleiteten Typs sortiert). Weitere Informationen finden Sie unter [Datenmember-Reihenfolge](data-member-order.md).  
  
 Im folgenden Beispiel käme `amount` normalerweise zuerst, da es alphabetisch an erster Stelle steht. Die <xref:System.ServiceModel.MessageBodyMemberAttribute.Order%2A>-Eigenschaft setzt es jedoch an die dritte Position.  
  
```csharp  
[MessageContract]  
public class BankingTransaction  
{  
  [MessageHeader] public Operation operation;  
  [MessageBodyMember(Order=1)] public Account sourceAccount;  
  [MessageBodyMember(Order=2)] public Account targetAccount;  
  [MessageBodyMember(Order=3)] public int amount;  
}  
```  
  
## <a name="message-contract-versioning"></a>Versionsverwaltung für Nachrichtenverträge  
 Sie müssen möglicherweise gelegentlich Nachrichtenverträge ändern. Beispielsweise kann eine neue Version Ihrer Anwendung einen zusätzlichen Header zu einer Nachricht hinzufügen. Erfolgt dann ein Versand von der neuen Version zur alten, muss das System den zusätzlichen Header und einen fehlenden Header (in der anderen Richtung) verarbeiten.  
  
 Für Versionsheader gelten die folgenden Regeln:  
  
- WCF ist nicht auf die fehlenden Header – die entsprechenden Member haben die Standardwerte beibehalten.  
  
- WCF ignoriert auch unerwartete zusätzliche Header. Die Ausnahme zu dieser Regel besteht darin, dass der zusätzliche Header über ein `MustUnderstand`-Attribut verfügt, das in der eingehenden SOAP-Nachricht auf `true` festgelegt ist – in diesem Fall wird eine Ausnahme ausgelöst, da ein Header, der verstanden werden muss, nicht verarbeitet werden kann.  
  
 Nachrichtentexte haben ähnliche Versionsregeln – sowohl fehlende als auch zusätzliche Nachrichtentextteile werden ignoriert.  
  
## <a name="inheritance-considerations"></a>Überlegungen zur Vererbung  
 Ein Nachrichtenvertragstyp kann von einem anderen Typ erben, solange der Basistyp ebenfalls über einen Nachrichtenvertrag verfügt.  
  
 Bei der Erstellung einer Nachricht oder beim Zugriff darauf mithilfe eines Nachrichtenvertragstyps, der von anderen Nachrichtenvertragstypen erbt, gelten die folgenden Regeln.  
  
- Alle Nachrichtenheader in der Vererbungshierarchie werden gesammelt, um den vollständigen Satz an Headern für die Nachricht zu bilden.  
  
- Alle Nachrichtentextteile in der Vererbungshierarchie werden gesammelt, um den vollständigen Nachrichtentext zu bilden. Die Textteile werden basierend auf den üblichen Sortierungsregeln sortiert (nach der <xref:System.ServiceModel.MessageBodyMemberAttribute.Order%2A?displayProperty=nameWithType>-Eigenschaft und danach alphabetisch), wobei die Position in der Vererbungshierarchie unbeachtet bleibt. Wenn Nachrichtentextteile in mehreren Ebenen der Vererbungsstruktur auftauchen, wird von der Verwendung der Nachrichtenvertragsvererbung strengstens abgeraten. Wenn eine Basisklasse und eine abgeleitete Klasse einen Header oder einen Textteil mit demselben Namen definieren, wird der Member der Basisklasse verwendet, um den Wert des Headers oder des Textteils zu speichern.  
  
 Betrachten Sie die Klassen im folgenden Codebeispiel.  
  
```csharp  
[MessageContract]  
public class PersonRecord  
{  
  [MessageHeader(Name="ID")] public int personID;  
  [MessageBodyMember] public string patientName;  
}  
  
[MessageContract]  
public class PatientRecord : PersonRecord  
{  
  [MessageHeader(Name="ID")] public int patientID;  
  [MessageBodyMember] public string diagnosis;  
}  
```  
  
 Die `PatientRecord`-Klasse beschreibt eine Nachricht mit einem Header mit dem Namen `ID`. Der Header entspricht der `personID` und nicht dem `patientID`-Member, da der Basismember ausgewählt wird. Somit ist das `patientID`-Feld in diesem Fall unbrauchbar. Der Text der Nachricht enthält das `diagnosis`-Element, gefolgt vom `patientName`-Element, da dies die alphabetische Reihenfolge ist. Beachten Sie, dass das Beispiel ein Muster zeigt, von dem strengstens abgeraten wird: sowohl der Basisklassenvertrag als auch der abgeleitete Klassenvertrag verfügen über Nachrichtentextteile.  
  
## <a name="wsdl-considerations"></a>Überlegungen zu WSDL  
 Bei der Erstellung eines WSDL (Web Services Description Language)-Vertrags aus einem Dienst, der Nachrichtenverträge nutzt, ist es wichtig, daran zu denken, dass nicht alle Nachrichtenvertragsfunktionen in der resultierenden WSDL widergespiegelt werden. Beachten Sie die folgenden Punkte:  
  
- WSDL kann den Begriff eines Arrays aus Headern nicht ausdrücken. Bei der Erstellung von Nachrichten mit einem Array aus Headern mithilfe des <xref:System.ServiceModel.MessageHeaderArrayAttribute> spiegelt die resultierende WSDL nur einen Header wider anstelle eines Array.  
  
- Das resultierende WSDL-Dokument spiegelt möglicherweise einige der Informationen auf Schutzebene nicht wider.  
  
- Der in der WSDL generierte Nachrichtentyp verfügt über denselben Namen wie die Klasse des Nachrichtenvertragstyps.  
  
- Bei Verwendung desselben Nachrichtenvertrags in mehreren Vorgängen werden mehrere Nachrichtentypen im WSDL-Dokument generiert. Die Namen werden durch Hinzufügen der Zahlen "2", "3" usw. für eine aufeinanderfolgende Verwendung eindeutig gekennzeichnet. Beim Rückimport der WSDL werden mehrere Nachrichtenvertragstypen erstellt, die abgesehen von ihren Namen identisch sind.  
  
## <a name="soap-encoding-considerations"></a>Überlegungen zur SOAP-Codierung  
 WCF ermöglicht es Ihnen, die Legacy-SOAP-Codierungsstil von XML zu verwenden. es wird jedoch nicht empfohlen, die Verwendung zu verwenden. Bei der Verwendung dieses Formats (durch Festlegen der `Use`-Eigenschaft auf `Encoded` auf dem <xref:System.ServiceModel.XmlSerializerFormatAttribute?displayProperty=nameWithType>, das auf den Dienstvertrag angewandt wird), gelten die folgenden zusätzlichen Überlegungen:  
  
- Die Nachrichtenheader werden nicht unterstützt. Dies bedeutet, dass das Attribut <xref:System.ServiceModel.MessageHeaderAttribute> und das Arrayattribut <xref:System.ServiceModel.MessageHeaderArrayAttribute> nicht mit der SOAP-Codierung kompatibel sind.  
  
- Wird der Nachrichtenvertrag nicht umbrochen, d. h., ist die Eigenschaft <xref:System.ServiceModel.MessageContractAttribute.IsWrapped%2A> auf `false` festgelegt, kann der Nachrichtenvertrag nur über einen Textteil verfügen.  
  
- Der Name des Wrapperelements für den Anforderungsnachrichtenvertrag muss zum Vorgangsnamen passen. Verwenden Sie hierfür die `WrapperName`-Eigenschaft des Nachrichtenvertrags.  
  
- Der Name des Wrapperelements für den Antwortnachrichtenvertrag muss dem Namen des Vorgangs entsprechen, der über das Suffix "Response" verfügt. Verwenden Sie hierfür die <xref:System.ServiceModel.MessageContractAttribute.WrapperName%2A>-Eigenschaft des Nachrichtenvertrags.  
  
- SOAP-Codierung behält Objektverweise bei. Betrachten Sie hierzu den folgenden Beispielcode:  
  
    ```csharp  
    [MessageContract(WrapperName="updateChangeRecord")]  
    public class ChangeRecordRequest  
    {  
      [MessageBodyMember] Person changedBy;  
      [MessageBodyMember] Person changedFrom;  
      [MessageBodyMember] Person changedTo;  
    }  
  
    [MessageContract(WrapperName="updateChangeRecordResponse")]  
    public class ChangeRecordResponse  
    {  
      [MessageBodyMember] Person changedBy;  
      [MessageBodyMember] Person changedFrom;  
      [MessageBodyMember] Person changedTo;  
    }  
  
    // application code:  
    ChangeRecordRequest cr = new ChangeRecordRequest();  
    Person p = new Person("John Doe");  
    cr.changedBy=p;  
    cr.changedFrom=p;  
    cr.changedTo=p;  
    ```  
  
 Nach der Serialisierung der Nachricht mithilfe von SOAP-Codierung enthalten `changedFrom` und `changedTo` nicht ihre eigenen Kopien von `p`, sondern verweisen auf die Kopie innerhalb des `changedBy`-Elements.  
  
## <a name="performance-considerations"></a>Überlegungen zur Leistung  
 Jeder Nachrichtenheader und jeder Nachrichtentextteil wird unabhängig von den anderen serialisiert. Deshalb können die gleichen Namespaces wieder für jeden Header und jeden Textteil deklariert werden. Zur Verbesserung der Leistung, insbesondere in Bezug auf die Größe der zu übertragenden Nachricht, fassen Sie mehrere Header und Textteile in einem einzelnen Header oder einzelnen Textteil zusammen. Beispielsweise anstelle des folgenden Codes:  
  
```csharp  
[MessageContract]  
public class BankingTransaction  
{  
  [MessageHeader] public Operation operation;  
  [MessageBodyMember] public Account sourceAccount;  
  [MessageBodyMember] public Account targetAccount;  
  [MessageBodyMember] public int amount;  
}  
```  
  
 Verwenden Sie diesen Code.  
  
```csharp  
[MessageContract]  
public class BankingTransaction  
{  
  [MessageHeader] public Operation operation;  
  [MessageBodyMember] public OperationDetails details;  
}  
  
[DataContract]  
public class OperationDetails  
{  
  [DataMember] public Account sourceAccount;  
  [DataMember] public Account targetAccount;  
  [DataMember] public int amount;  
}  
```  
  
### <a name="event-based-asynchronous-and-message-contracts"></a>Ereignisbasiertes asynchrones Modell und Nachrichtenverträge  
 Die Entwurfsrichtlinien für das ereignisbasierte asynchrone Modell besagen, dass in den Fällen, in denen mehr als ein Wert zurückgegeben wird, ein Wert in der `Result`-Eigenschaft und die übrigen Werte in Eigenschaften des <xref:System.EventArgs>-Objekts zurückgegeben werden sollen. Wenn ein Client Metadaten mithilfe der ereignisbasierten asynchronen Befehlsoptionen importiert, und der Vorgang mehr als einen Wert zurückgibt, dann gibt das <xref:System.EventArgs>-Standardobjekt infolgedessen einen Wert in der `Result`-Eigenschaft zurück, während die übrigen Werte in Eigenschaften des <xref:System.EventArgs>-Objekts zurückgegeben werden.  
  
 Wenn das Nachrichtenobjekt in der `Result`-Eigenschaft und die Rückgabewerte als Eigenschaften dieses Objekts übermittelt werden sollen, verwenden Sie die Befehlsoption `/messageContract`. Damit wird eine Signatur generiert, bei der die Antwortnachricht in der `Result`-Eigenschaft des <xref:System.EventArgs>-Objekts zurückgegeben wird. Alle internen Rückgabewerte sind dann Eigenschaften des Antwortnachrichtenobjekts.  
  
## <a name="see-also"></a>Siehe auch

- [Verwenden von Datenverträgen](using-data-contracts.md)
- [Entwerfen und Implementieren von Diensten](../designing-and-implementing-services.md)
