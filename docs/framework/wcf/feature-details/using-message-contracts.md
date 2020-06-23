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
# <a name="using-message-contracts"></a><span data-ttu-id="0a062-103">Verwendung von Nachrichtenverträgen</span><span class="sxs-lookup"><span data-stu-id="0a062-103">Using Message Contracts</span></span>
<span data-ttu-id="0a062-104">Beim Entwickeln von Windows Communication Foundation (WCF)-Anwendungen achten Entwickler in der Regel auf die Datenstrukturen und Serialisierungsprobleme und müssen sich nicht mit der Struktur der Nachrichten befassen, in denen die Daten übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="0a062-104">Typically when building Windows Communication Foundation (WCF) applications, developers pay close attention to the data structures and serialization issues and do not need to concern themselves with the structure of the messages in which the data is carried.</span></span> <span data-ttu-id="0a062-105">Für diese Anwendungen ist die Erstellung von Datenverträgen für die Parameter oder Rückgabewerte ein einfacher Vorgang.</span><span class="sxs-lookup"><span data-stu-id="0a062-105">For these applications, creating data contracts for the parameters or return values is straightforward.</span></span> <span data-ttu-id="0a062-106">(Weitere Informationen finden Sie unter [Angeben von Datenübertragung in Dienstverträgen](specifying-data-transfer-in-service-contracts.md).)</span><span class="sxs-lookup"><span data-stu-id="0a062-106">(For more information, see [Specifying Data Transfer in Service Contracts](specifying-data-transfer-in-service-contracts.md).)</span></span>  
  
 <span data-ttu-id="0a062-107">Allerdings ist zuweilen die vollständige Kontrolle über die Struktur einer SOAP-Nachricht wichtiger als die Kontrolle über dessen Inhalte.</span><span class="sxs-lookup"><span data-stu-id="0a062-107">However, sometimes complete control over the structure of a SOAP message is just as important as control over its contents.</span></span> <span data-ttu-id="0a062-108">Dies gilt insbesondere, wenn Interoperabilität wichtig ist oder um Sicherheitsprobleme speziell auf der Ebene der Nachricht oder des Nachrichtenteils zu kontrollieren.</span><span class="sxs-lookup"><span data-stu-id="0a062-108">This is especially true when interoperability is important or to specifically control security issues at the level of the message or message part.</span></span> <span data-ttu-id="0a062-109">In diesen Fällen können Sie einen *Nachrichten Vertrag* erstellen, der es Ihnen ermöglicht, die Struktur der exakten SOAP-Nachricht anzugeben.</span><span class="sxs-lookup"><span data-stu-id="0a062-109">In these cases, you can create a *message contract* that enables you to specify the structure of the precise SOAP message required.</span></span>  
  
 <span data-ttu-id="0a062-110">Dieses Thema beschreibt, wie die unterschiedlichen Attribute für Nachrichtenverträge zur Erstellung eines spezifischen Nachrichtenvertrags für Ihren Vorgang verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0a062-110">This topic discusses how to use the various message contract attributes to create a specific message contract for your operation.</span></span>  
  
## <a name="using-message-contracts-in-operations"></a><span data-ttu-id="0a062-111">Verwenden von Nachrichtenverträgen in Vorgängen</span><span class="sxs-lookup"><span data-stu-id="0a062-111">Using Message Contracts in Operations</span></span>  
 <span data-ttu-id="0a062-112">WCF unterstützt Vorgänge, die entweder für den *Remote Prozedur Aufruf (RPC)* oder den *Messaging Stil*modelliert wurden.</span><span class="sxs-lookup"><span data-stu-id="0a062-112">WCF supports operations modeled on either the *remote procedure call (RPC) style* or the *messaging style*.</span></span> <span data-ttu-id="0a062-113">Bei einem Vorgang im RPC-Stil können Sie jeden serialisierbaren Typ verwenden, und Sie haben Zugriff auf die Funktionen, die für lokale Aufrufe verfügbar sind, beispielsweise mehrere Parameter sowie der `ref`-Parameter und der `out`-Parameter.</span><span class="sxs-lookup"><span data-stu-id="0a062-113">In an RPC-style operation, you can use any serializable type, and you have access to the features that are available to local calls, such as multiple parameters and `ref` and `out` parameters.</span></span> <span data-ttu-id="0a062-114">In diesem Stil steuert die gewählte Form der Serialisierung die Struktur der Daten in den zugrunde liegenden Nachrichten, und die WCF-Laufzeit erstellt die Nachrichten, um den Vorgang zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="0a062-114">In this style, the form of serialization chosen controls the structure of the data in the underlying messages, and the WCF runtime creates the messages to support the operation.</span></span> <span data-ttu-id="0a062-115">Dadurch können Entwickler, die sich mit SOAP und SOAP-Nachrichten nicht auskennen, Dienstanwendungen schnell und einfach erstellen und verwenden.</span><span class="sxs-lookup"><span data-stu-id="0a062-115">This enables developers who are not familiar with SOAP and SOAP messages to quickly and easily create and use service applications.</span></span>  
  
 <span data-ttu-id="0a062-116">Das folgende Codebeispiel zeigt einen im RPC-Stil erstellten Dienstvorgang.</span><span class="sxs-lookup"><span data-stu-id="0a062-116">The following code example shows a service operation modeled on the RPC style.</span></span>  
  
```csharp  
[OperationContract]  
public BankingTransactionResponse PostBankingTransaction(BankingTransaction bt);  
```  
  
 <span data-ttu-id="0a062-117">Normalerweise ist ein Datenvertrag ausreichend, um das Schema für die Nachrichten zu definieren.</span><span class="sxs-lookup"><span data-stu-id="0a062-117">Normally, a data contract is sufficient to define the schema for the messages.</span></span> <span data-ttu-id="0a062-118">Beispielsweise reicht es im vorherigen Beispiel für die meisten Anwendungen aus, wenn `BankingTransaction` und `BankingTransactionResponse` über Datenverträge für die Inhaltsdefinition der zugrunde liegenden SOAP-Nachrichten verfügen.</span><span class="sxs-lookup"><span data-stu-id="0a062-118">For instance, in the preceding example, it is sufficient for most applications if `BankingTransaction` and `BankingTransactionResponse` have data contracts to define the contents of the underlying SOAP messages.</span></span> <span data-ttu-id="0a062-119">Weitere Informationen zu Daten Verträgen finden Sie unter [Verwenden von Daten Verträgen](using-data-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="0a062-119">For more information about data contracts, see [Using Data Contracts](using-data-contracts.md).</span></span>  
  
 <span data-ttu-id="0a062-120">Zuweilen ist es allerdings notwendig, die Struktur der übertragenen SOAP-Nachricht genau zu steuern.</span><span class="sxs-lookup"><span data-stu-id="0a062-120">However, occasionally it is necessary to precisely control how the structure of the SOAP message transmitted over the wire.</span></span> <span data-ttu-id="0a062-121">Das gängigste Szenario hierfür besteht aus dem Einfügen von benutzerdefinierten SOAP-Headern.</span><span class="sxs-lookup"><span data-stu-id="0a062-121">The most common scenario for this is inserting custom SOAP headers.</span></span> <span data-ttu-id="0a062-122">Ein weiteres übliches Szenario ist die Definition von Sicherheitseigenschaften für Nachrichtenheader und -text, das heißt, die Entscheidung, ob diese Elemente digital signiert und verschlüsselt werden.</span><span class="sxs-lookup"><span data-stu-id="0a062-122">Another common scenario is to define security properties for the message's headers and body, that is, to decide whether these elements are digitally signed and encrypted.</span></span> <span data-ttu-id="0a062-123">Schließlich erfordern eine Reihe von Drittanbieter-SOAP-Stapeln Nachrichten in einem bestimmten Format.</span><span class="sxs-lookup"><span data-stu-id="0a062-123">Finally, some third-party SOAP stacks require messages be in a specific format.</span></span> <span data-ttu-id="0a062-124">Vorgänge im Messagingstil bieten diese Kontrolle.</span><span class="sxs-lookup"><span data-stu-id="0a062-124">Messaging-style operations provide this control.</span></span>  
  
 <span data-ttu-id="0a062-125">Ein Vorgang im Messagingstil verfügt über höchstens einen Parameter und einen Rückgabewert. Bei beiden Typen handelt es sich um Nachrichtentypen, d. h. sie serialisieren direkt in eine festgelegte SOAP-Nachrichtenstruktur.</span><span class="sxs-lookup"><span data-stu-id="0a062-125">A messaging-style operation has at most one parameter and one return value where both types are message types; that is, they serialize directly into a specified SOAP message structure.</span></span> <span data-ttu-id="0a062-126">Hierbei kann es sich um jeden Typ mit der Kennzeichnung <xref:System.ServiceModel.MessageContractAttribute> oder um den <xref:System.ServiceModel.Channels.Message>-Typ handeln.</span><span class="sxs-lookup"><span data-stu-id="0a062-126">This may be any type marked with the <xref:System.ServiceModel.MessageContractAttribute> or the <xref:System.ServiceModel.Channels.Message> type.</span></span> <span data-ttu-id="0a062-127">Das folgende Codebeispiel zeigt einen Vorgang, der dem vorangehenden Vorgang im RCP-Stil ähnelt, aber den Messagingstil nutzt.</span><span class="sxs-lookup"><span data-stu-id="0a062-127">The following code example shows an operation similar to the preceding RCP-style, but which uses the messaging style.</span></span>  
  
 <span data-ttu-id="0a062-128">Wenn sowohl `BankingTransaction` als auch `BankingTransactionResponse` Typen sind, bei denen es sich um Nachrichtenverträge handelt, ist der Code in den folgenden Vorgängen gültig.</span><span class="sxs-lookup"><span data-stu-id="0a062-128">For example, if `BankingTransaction` and `BankingTransactionResponse` are both types that are message contracts, then the code in the following operations is valid.</span></span>  
  
```csharp  
[OperationContract]  
BankingTransactionResponse Process(BankingTransaction bt);  
[OperationContract]  
void Store(BankingTransaction bt);  
[OperationContract]  
BankingTransactionResponse GetResponse();  
```  
  
 <span data-ttu-id="0a062-129">Der folgende Code ist allerdings ungültig.</span><span class="sxs-lookup"><span data-stu-id="0a062-129">However, the following code is invalid.</span></span>  
  
```csharp  
[OperationContract]  
bool Validate(BankingTransaction bt);  
// Invalid, the return type is not a message contract.  
[OperationContract]  
void Reconcile(BankingTransaction bt1, BankingTransaction bt2);  
// Invalid, there is more than one parameter.  
```  
  
 <span data-ttu-id="0a062-130">Für jeden Vorgang, der einen Nachrichtenvertragstyp beinhaltet und nicht eines der gültigen Muster einhält, wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="0a062-130">An exception is thrown for any operation that involves a message contract type and that does not follow one of the valid patterns.</span></span> <span data-ttu-id="0a062-131">Natürlich unterliegen Vorgänge, die keine Nachrichtenvertragstypen einschließen, diesen Einschränkungen nicht.</span><span class="sxs-lookup"><span data-stu-id="0a062-131">Of course, operations that do not involve message contract types are not subject to these restrictions.</span></span>  
  
 <span data-ttu-id="0a062-132">Verfügt ein Typ sowohl über einen Nachrichtenvertrag als auch über einen Datenvertrag, wird nur der Nachrichtenvertrag berücksichtigt, wenn der Typ in einem Vorgang zum Einsatz kommt.</span><span class="sxs-lookup"><span data-stu-id="0a062-132">If a type has both a message contract and a data contract, only its message contract is considered when the type is used in an operation.</span></span>  
  
## <a name="defining-message-contracts"></a><span data-ttu-id="0a062-133">Definition von Nachrichtenverträgen</span><span class="sxs-lookup"><span data-stu-id="0a062-133">Defining Message Contracts</span></span>  
 <span data-ttu-id="0a062-134">Zur Definition eines Nachrichtenvertrags für einen Typ (d. h. zur Definition der Zuordnung zwischen Typ und SOAP-Umschlag) wenden Sie <xref:System.ServiceModel.MessageContractAttribute> auf den Typ an.</span><span class="sxs-lookup"><span data-stu-id="0a062-134">To define a message contract for a type (that is, to define the mapping between the type and a SOAP envelope), apply the <xref:System.ServiceModel.MessageContractAttribute> to the type.</span></span> <span data-ttu-id="0a062-135">Wenden Sie dann das <xref:System.ServiceModel.MessageHeaderAttribute> auf die Member an, die Sie SOAP-Headern machen möchten, und wenden Sie dann das <xref:System.ServiceModel.MessageBodyMemberAttribute> auf die Member an,die Sie zu Teilen des SOAP-Texts der Nachricht machen möchten.</span><span class="sxs-lookup"><span data-stu-id="0a062-135">Then apply the <xref:System.ServiceModel.MessageHeaderAttribute> to those members of the type you want to make into SOAP headers, and apply the <xref:System.ServiceModel.MessageBodyMemberAttribute> to those members you want to make into parts of the SOAP body of the message.</span></span>  
  
 <span data-ttu-id="0a062-136">Der folgende Code stellt ein Beispiel für die Verwendung eines Nachrichtenvertrags dar.</span><span class="sxs-lookup"><span data-stu-id="0a062-136">The following code provides an example of using a message contract.</span></span>  
  
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
  
 <span data-ttu-id="0a062-137">Bei der Verwendung dieses Typs als Vorgangsparameter wird der folgende SOAP-Umschlag generiert:</span><span class="sxs-lookup"><span data-stu-id="0a062-137">When using this type as an operation parameter, the following SOAP envelope is generated:</span></span>  
  
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
  
 <span data-ttu-id="0a062-138">Beachten Sie, dass `operation` und `transactionDate` als SOAP-Header angezeigt werden und der SOAP-Text aus dem Wrapperelement `BankingTransaction` besteht, das `sourceAccount`,`targetAccount` und `amount` enthält.</span><span class="sxs-lookup"><span data-stu-id="0a062-138">Notice that `operation` and `transactionDate` appear as SOAP headers and the SOAP body consists of a wrapper element `BankingTransaction` containing `sourceAccount`,`targetAccount`, and `amount`.</span></span>  
  
 <span data-ttu-id="0a062-139">Sie können <xref:System.ServiceModel.MessageHeaderAttribute> und <xref:System.ServiceModel.MessageBodyMemberAttribute> auf alle Felder, Eigenschaften und Ereignisse anwenden, unabhängig davon, ob diese öffentlich, privat, geschützt oder intern sind.</span><span class="sxs-lookup"><span data-stu-id="0a062-139">You can apply the <xref:System.ServiceModel.MessageHeaderAttribute> and <xref:System.ServiceModel.MessageBodyMemberAttribute> to all fields, properties, and events, regardless of whether they are public, private, protected, or internal.</span></span>  
  
 <span data-ttu-id="0a062-140">Das <xref:System.ServiceModel.MessageContractAttribute> ermöglicht Ihnen das Angeben des WrapperName-Attributs und des WrapperNamespace-Attributs, die den Namen des Wrapperelements im Textkörper der SOAP-Nachricht steuern.</span><span class="sxs-lookup"><span data-stu-id="0a062-140">The <xref:System.ServiceModel.MessageContractAttribute> allows you to specify the WrapperName and WrapperNamespace attributes which control the name of the wrapper element in the body of the SOAP message.</span></span> <span data-ttu-id="0a062-141">Standardmäßig wird der Name des Typs des Nachrichtenvertrags für den Wrapper verwendet, und der Namespace, in dem der Nachrichtenvertrag `http://tempuri.org/` definiert ist, fungiert als Standardnamespace.</span><span class="sxs-lookup"><span data-stu-id="0a062-141">By default the name of the message contract type is used for the wrapper and the namespace in which the message contract is defined `http://tempuri.org/` is used as the default namespace.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0a062-142"><xref:System.Runtime.Serialization.KnownTypeAttribute>-Attribute werden in Nachrichtenverträgen ignoriert.</span><span class="sxs-lookup"><span data-stu-id="0a062-142"><xref:System.Runtime.Serialization.KnownTypeAttribute> attributes are ignored in message contracts.</span></span> <span data-ttu-id="0a062-143">Ist ein <xref:System.Runtime.Serialization.KnownTypeAttribute> erforderlich, platzieren Sie es auf dem Vorgang, der den in Frage kommenden Nachrichtenvertrag nutzt.</span><span class="sxs-lookup"><span data-stu-id="0a062-143">If a <xref:System.Runtime.Serialization.KnownTypeAttribute> is required, place it on the operation that is using the message contract in question.</span></span>  
  
## <a name="controlling-header-and-body-part-names-and-namespaces"></a><span data-ttu-id="0a062-144">Kontrollieren von Header- und Textteilnamen und Namespaces</span><span class="sxs-lookup"><span data-stu-id="0a062-144">Controlling Header and Body Part Names and Namespaces</span></span>  
 <span data-ttu-id="0a062-145">In der SOAP-Darstellung eines Nachrichtenvertrags wird jeder Header und jeder Textteil einem XML-Element zugeordnet, das über einen Namen und einen Namespace verfügt.</span><span class="sxs-lookup"><span data-stu-id="0a062-145">In the SOAP representation of a message contract, each header and body part maps to an XML element that has a name and a namespace.</span></span>  
  
 <span data-ttu-id="0a062-146">Standardmäßig entspricht der Namespace dem Namespace des Dienstvertrags, an dem die Nachricht teilnimmt, und der Name wird durch den Membernamen festgelegt, auf den die Attribute <xref:System.ServiceModel.MessageHeaderAttribute> oder <xref:System.ServiceModel.MessageBodyMemberAttribute> angewandt wurden.</span><span class="sxs-lookup"><span data-stu-id="0a062-146">By default, the namespace is the same as the namespace of the service contract that the message is participating in, and the name is determined by the member name to which the <xref:System.ServiceModel.MessageHeaderAttribute> or the <xref:System.ServiceModel.MessageBodyMemberAttribute> attributes are applied.</span></span>  
  
 <span data-ttu-id="0a062-147">Die Standardeinstellungen können Sie ändern, indem Sie <xref:System.ServiceModel.MessageContractMemberAttribute.Name%2A?displayProperty=nameWithType> und <xref:System.ServiceModel.MessageContractMemberAttribute.Namespace%2A?displayProperty=nameWithType> bearbeiten (in der übergeordneten Klasse der Attribute <xref:System.ServiceModel.MessageHeaderAttribute> und <xref:System.ServiceModel.MessageBodyMemberAttribute>).</span><span class="sxs-lookup"><span data-stu-id="0a062-147">You can change these defaults by manipulating the <xref:System.ServiceModel.MessageContractMemberAttribute.Name%2A?displayProperty=nameWithType> and <xref:System.ServiceModel.MessageContractMemberAttribute.Namespace%2A?displayProperty=nameWithType> (on the parent class of the <xref:System.ServiceModel.MessageHeaderAttribute> and <xref:System.ServiceModel.MessageBodyMemberAttribute> attributes).</span></span>  
  
 <span data-ttu-id="0a062-148">Betrachten Sie die Klasse im folgenden Codebeispiel.</span><span class="sxs-lookup"><span data-stu-id="0a062-148">Consider the class in the following code example.</span></span>  
  
```csharp  
[MessageContract]  
public class BankingTransaction  
{  
  [MessageHeader] public Operation operation;  
  [MessageHeader(Namespace="http://schemas.contoso.com/auditing/2005")] public bool IsAudited;  
  [MessageBodyMember(Name="transactionData")] public BankingTransactionData theData;  
}  
```  
  
 <span data-ttu-id="0a062-149">In diesem Beispiel befindet sich der `IsAudited`-Header im Namespace, der vom Code festgelegt wird, und der Textteil, der den `theData`-Member darstellt, wird von einem XML-Element mit dem Namen `transactionData` abgebildet.</span><span class="sxs-lookup"><span data-stu-id="0a062-149">In this example, the `IsAudited` header is in the namespace specified in the code, and the body part that represents the `theData` member is represented by an XML element with the name `transactionData`.</span></span> <span data-ttu-id="0a062-150">Im Folgenden wird der XML-Code angezeigt, der für diesen Nachrichtenvertrag generiert wird.</span><span class="sxs-lookup"><span data-stu-id="0a062-150">The following shows the XML generated for this message contract.</span></span>  
  
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
  
## <a name="controlling-whether-the-soap-body-parts-are-wrapped"></a><span data-ttu-id="0a062-151">Kontrolle, ob die SOAP-Textteile umbrochen werden</span><span class="sxs-lookup"><span data-stu-id="0a062-151">Controlling Whether the SOAP Body Parts Are Wrapped</span></span>  
 <span data-ttu-id="0a062-152">Standardmäßig sind die SOAP-Textteile in einem umbrochenen Element serialisiert.</span><span class="sxs-lookup"><span data-stu-id="0a062-152">By default, the SOAP body parts are serialized inside a wrapped element.</span></span> <span data-ttu-id="0a062-153">Beispielsweise zeigt der folgende Code das `HelloGreetingMessage`-Wrapperelement, das aus dem Namen des <xref:System.ServiceModel.MessageContractAttribute>-Typs im Nachrichtenvertrag für die `HelloGreetingMessage`-Nachricht generiert wird.</span><span class="sxs-lookup"><span data-stu-id="0a062-153">For example, the following code shows the `HelloGreetingMessage` wrapper element generated from the name of the <xref:System.ServiceModel.MessageContractAttribute> type in the message contract for the `HelloGreetingMessage` message.</span></span>  
  
[!code-csharp[MessageHeaderAttribute#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/messageheaderattribute/cs/services.cs#3)]
[!code-vb[MessageHeaderAttribute#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/messageheaderattribute/vb/services.vb#3)]  
  
 <span data-ttu-id="0a062-154">Um das Wrapperelement zu unterdrücken, legen Sie die <xref:System.ServiceModel.MessageContractAttribute.IsWrapped%2A>-Eigenschaft auf `false` fest.</span><span class="sxs-lookup"><span data-stu-id="0a062-154">To suppress the wrapper element, set the <xref:System.ServiceModel.MessageContractAttribute.IsWrapped%2A> property to `false`.</span></span> <span data-ttu-id="0a062-155">Um den Namen und den Namespace des Wrapperelements zu kontrollieren, verwenden Sie die Eigenschaften <xref:System.ServiceModel.MessageContractAttribute.WrapperName%2A> und <xref:System.ServiceModel.MessageContractAttribute.WrapperNamespace%2A>.</span><span class="sxs-lookup"><span data-stu-id="0a062-155">To control the name and the namespace of the wrapper element, use the <xref:System.ServiceModel.MessageContractAttribute.WrapperName%2A> and <xref:System.ServiceModel.MessageContractAttribute.WrapperNamespace%2A> properties.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0a062-156">Das Vorhandensein von mehr als einem Nachrichtentextteil in nicht umbrochenen Nachrichten ist nicht mit dem WS-I Basic Profile 1.1 kompatibel und wird bei der Gestaltung neuer Nachrichtenverträge nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="0a062-156">Having more than one message body part in messages that are not wrapped is not compliant with WS-I Basic Profile 1.1 and is not recommended when designing new message contracts.</span></span> <span data-ttu-id="0a062-157">Allerdings kann es bei spezifischen Interoperabilitätsszenarien notwendig sein, mehr als einen nicht umbrochenen Nachrichtentextteil zu haben.</span><span class="sxs-lookup"><span data-stu-id="0a062-157">However, it may be necessary to have more than one unwrapped message body part in certain specific interoperability scenarios.</span></span> <span data-ttu-id="0a062-158">Wenn Sie mehrere Daten in einem Nachrichtentext übertragen möchten, wird die Verwendung des Standardumbruchmodus empfohlen.</span><span class="sxs-lookup"><span data-stu-id="0a062-158">If you are going to transmit more than one piece of data in a message body, it is recommended to use the default (wrapped) mode.</span></span> <span data-ttu-id="0a062-159">Mehr als einen Nachrichtenheader in nicht umbrochenen Nachrichten zu haben, ist vollkommen akzeptabel.</span><span class="sxs-lookup"><span data-stu-id="0a062-159">Having more than one message header in unwrapped messages is completely acceptable.</span></span>  
  
## <a name="using-custom-types-inside-message-contracts"></a><span data-ttu-id="0a062-160">Verwendung von benutzerdefinierten Typen innerhalb von Nachrichtenverträgen</span><span class="sxs-lookup"><span data-stu-id="0a062-160">Using Custom Types Inside Message Contracts</span></span>  
 <span data-ttu-id="0a062-161">Jeder einzelne Nachrichtenheader und Nachrichtentextteil wird mithilfe der ausgewählten Serialisierungs-Engine für den Dienstvertrag, bei dem die Nachricht verwendet wird, serialisiert (in XML konvertiert).</span><span class="sxs-lookup"><span data-stu-id="0a062-161">Each individual message header and message body part is serialized (turned into XML) using the chosen serialization engine for the service contract where the message is used.</span></span> <span data-ttu-id="0a062-162">Die Standardserialisierungs-Engine, `XmlFormatter`, kann jeden Typ verarbeiten, der über einen Datenvertrag verfügt; entweder explizit (durch <xref:System.Runtime.Serialization.DataContractAttribute?displayProperty=nameWithType>) oder implizit (bei einem primitiven Typ mit <xref:System.SerializableAttribute?displayProperty=nameWithType> usw.).</span><span class="sxs-lookup"><span data-stu-id="0a062-162">The default serialization engine, the `XmlFormatter`, can handle any type that has a data contract, either explicitly (by having the <xref:System.Runtime.Serialization.DataContractAttribute?displayProperty=nameWithType>) or implicitly (by being a primitive type, having the <xref:System.SerializableAttribute?displayProperty=nameWithType>, and so on).</span></span> <span data-ttu-id="0a062-163">Weitere Informationen finden Sie unter [Verwenden von Daten Verträgen](using-data-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="0a062-163">For more information, see [Using Data Contracts](using-data-contracts.md).</span></span>  
  
 <span data-ttu-id="0a062-164">Im vorangehenden Beispiel müssen die Typen `Operation` und `BankingTransactionData` über einen Datenvertrag verfügen, und `transactionDate` ist serialisierbar, da <xref:System.DateTime> primitiv ist (und über einen impliziten Datenvertrag verfügt).</span><span class="sxs-lookup"><span data-stu-id="0a062-164">In the preceding example, the `Operation` and `BankingTransactionData` types must have a data contract, and `transactionDate` is serializable because <xref:System.DateTime> is a primitive (and so has an implicit data contract).</span></span>  
  
 <span data-ttu-id="0a062-165">Es ist jedoch möglich, zu einer anderen Serialisierungs-Engine, dem `XmlSerializer`, umzuschalten.</span><span class="sxs-lookup"><span data-stu-id="0a062-165">However, it is possible to switch to a different serialization engine, the `XmlSerializer`.</span></span> <span data-ttu-id="0a062-166">Wenn Sie umschalten, sollten Sie sicherstellen, dass alle für die Nachrichtenheader und Textteile verwendeten Typen mithilfe des `XmlSerializer` serialisierbar sind.</span><span class="sxs-lookup"><span data-stu-id="0a062-166">If you make such a switch, you should ensure that all of the types used for message headers and body parts are serializable using the `XmlSerializer`.</span></span>  
  
## <a name="using-arrays-inside-message-contracts"></a><span data-ttu-id="0a062-167">Verwendung von Arrays innerhalb von Nachrichtenverträgen</span><span class="sxs-lookup"><span data-stu-id="0a062-167">Using Arrays Inside Message Contracts</span></span>  
 <span data-ttu-id="0a062-168">Sie können Arrays von sich wiederholenden Elementen in Nachrichtenverträgen auf zwei Arten verwenden.</span><span class="sxs-lookup"><span data-stu-id="0a062-168">You can use arrays of repeating elements in message contracts in two ways.</span></span>  
  
 <span data-ttu-id="0a062-169">Auf der einen Seite können Sie ein <xref:System.ServiceModel.MessageHeaderAttribute> oder ein <xref:System.ServiceModel.MessageBodyMemberAttribute> direkt auf dem Array anwenden.</span><span class="sxs-lookup"><span data-stu-id="0a062-169">The first is to use a <xref:System.ServiceModel.MessageHeaderAttribute> or a <xref:System.ServiceModel.MessageBodyMemberAttribute> directly on the array.</span></span> <span data-ttu-id="0a062-170">In diesem Fall wird das gesamte Array als ein Element (d. h. ein Header und ein Textteil) mit mehreren Unterelementen serialisiert.</span><span class="sxs-lookup"><span data-stu-id="0a062-170">In this case, the entire array is serialized as one element (that is, one header or one body part) with multiple child elements.</span></span> <span data-ttu-id="0a062-171">Betrachten Sie die Klasse im folgenden Beispiel.</span><span class="sxs-lookup"><span data-stu-id="0a062-171">Consider the class in the following example.</span></span>  
  
```csharp  
[MessageContract]  
public class BankingDepositLog  
{  
  [MessageHeader] public int numRecords;  
  [MessageHeader] public DepositRecord[] records;  
  [MessageHeader] public int branchID;  
}  
```  
  
 <span data-ttu-id="0a062-172">Das Ergebnis sind SOAP-Header, die den folgenden Beispielen ähneln.</span><span class="sxs-lookup"><span data-stu-id="0a062-172">This results in SOAP headers is similar to the following.</span></span>  
  
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
  
 <span data-ttu-id="0a062-173">Eine Alternative besteht in der Verwendung des <xref:System.ServiceModel.MessageHeaderArrayAttribute>.</span><span class="sxs-lookup"><span data-stu-id="0a062-173">An alternative to this is to use the <xref:System.ServiceModel.MessageHeaderArrayAttribute>.</span></span> <span data-ttu-id="0a062-174">In diesem Fall wird jedes Arrayelement unabhängig serialisiert, wobei jedes Arrayelement über einen Header verfügt (ähnlich wie im folgenden Beispiel).</span><span class="sxs-lookup"><span data-stu-id="0a062-174">In this case, each array element is serialized independently and so that each array element has one header, similar to the following.</span></span>  
  
```xml  
<numRecords>3</numRecords>  
<records>Record1</records>  
<records>Record2</records>  
<records>Record3</records>  
<branchID>20643</branchID>  
```  
  
 <span data-ttu-id="0a062-175">Der Standardname für Arrayeinträge ist der Name des Members, auf den die <xref:System.ServiceModel.MessageHeaderArrayAttribute>-Attribute angewandt werden.</span><span class="sxs-lookup"><span data-stu-id="0a062-175">The default name for array entries is the name of the member to which the <xref:System.ServiceModel.MessageHeaderArrayAttribute> attributes is applied.</span></span>  
  
 <span data-ttu-id="0a062-176">Das <xref:System.ServiceModel.MessageHeaderArrayAttribute>-Attribut erbt von <xref:System.ServiceModel.MessageHeaderAttribute>.</span><span class="sxs-lookup"><span data-stu-id="0a062-176">The <xref:System.ServiceModel.MessageHeaderArrayAttribute> attribute inherits from the <xref:System.ServiceModel.MessageHeaderAttribute>.</span></span> <span data-ttu-id="0a062-177">Es verfügt über denselben Funktionssatz wie die Nicht-Arrayattribute. Beispielsweise ist es möglich, die Reihenfolge, den Namen und den Namespace für ein Array von Headern so einzurichten wie für einen Einzelheader.</span><span class="sxs-lookup"><span data-stu-id="0a062-177">It has the same set of features as the non-array attributes, for example, it is possible to set the order, name, and namespace for an array of headers in the same way you set it for a single header.</span></span> <span data-ttu-id="0a062-178">Wenn Sie die `Order`-Eigenschaft auf ein Array verwenden, gilt dies für das gesamte Array.</span><span class="sxs-lookup"><span data-stu-id="0a062-178">When you use the `Order` property on an array, it applies to the entire array.</span></span>  
  
 <span data-ttu-id="0a062-179">Sie können <xref:System.ServiceModel.MessageHeaderArrayAttribute> nur auf Arrays anwenden, nicht auf Sammlungen.</span><span class="sxs-lookup"><span data-stu-id="0a062-179">You can apply the <xref:System.ServiceModel.MessageHeaderArrayAttribute> only to arrays, not collections.</span></span>  
  
## <a name="using-byte-arrays-in-message-contracts"></a><span data-ttu-id="0a062-180">Verwendung von Bytearrays in Nachrichtenverträgen</span><span class="sxs-lookup"><span data-stu-id="0a062-180">Using Byte Arrays in Message Contracts</span></span>  
 <span data-ttu-id="0a062-181">Bytearrays werden bei der Verwendung mit Nicht-Arrayattributen (<xref:System.ServiceModel.MessageBodyMemberAttribute> und <xref:System.ServiceModel.MessageHeaderAttribute>) nicht als Arrays behandelt, sondern als spezielle primitive Typen, die als Base64-codierte Daten in der resultierenden XML dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="0a062-181">Byte arrays, when used with the non-array attributes (<xref:System.ServiceModel.MessageBodyMemberAttribute> and <xref:System.ServiceModel.MessageHeaderAttribute>), are not treated as arrays but as a special primitive type represented as Base64-encoded data in the resulting XML.</span></span>  
  
 <span data-ttu-id="0a062-182">Wenn Sie Bytearrays mit dem Arrayattribut <xref:System.ServiceModel.MessageHeaderArrayAttribute> verwenden, hängen die Ergebnisse vom verwendeten Serialisierungsprogramm ab.</span><span class="sxs-lookup"><span data-stu-id="0a062-182">When you use byte arrays with the array attribute <xref:System.ServiceModel.MessageHeaderArrayAttribute>, the results depend on the serializer in use.</span></span> <span data-ttu-id="0a062-183">Mit dem Standardserialisierungsprogramm wird das Array als einzelner Eintrag für jedes Byte dargestellt.</span><span class="sxs-lookup"><span data-stu-id="0a062-183">With the default serializer, the array is represented as an individual entry for each byte.</span></span> <span data-ttu-id="0a062-184">Ist allerdings `XmlSerializer` ausgewählt (mithilfe von <xref:System.ServiceModel.XmlSerializerFormatAttribute> auf dem Dienstvertrag), werden Bytearrays als Base64-Daten behandelt, unabhängig davon, ob Array- oder Nicht-Arrayattribute verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0a062-184">However, when the `XmlSerializer` is selected, (using the <xref:System.ServiceModel.XmlSerializerFormatAttribute> on the service contract), byte arrays are treated as Base64 data regardless of whether the array or non-array attributes are used.</span></span>  
  
## <a name="signing-and-encrypting-parts-of-the-message"></a><span data-ttu-id="0a062-185">Signieren und Verschlüsseln von Teilen der Nachricht</span><span class="sxs-lookup"><span data-stu-id="0a062-185">Signing and Encrypting Parts of the Message</span></span>  
 <span data-ttu-id="0a062-186">Ein Nachrichtenvertrag kann angeben, ob die Header und/oder der Text der Nachricht digital signiert und verschlüsselt werden soll.</span><span class="sxs-lookup"><span data-stu-id="0a062-186">A message contract can indicate whether the headers and/or body of the message should be digitally signed and encrypted.</span></span>  
  
 <span data-ttu-id="0a062-187">Dies wird erreicht, indem die <xref:System.ServiceModel.MessageContractMemberAttribute.ProtectionLevel%2A?displayProperty=nameWithType>-Eigenschaften in den Attributen <xref:System.ServiceModel.MessageHeaderAttribute> und <xref:System.ServiceModel.MessageBodyMemberAttribute> festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="0a062-187">This is done by setting the <xref:System.ServiceModel.MessageContractMemberAttribute.ProtectionLevel%2A?displayProperty=nameWithType> property on the <xref:System.ServiceModel.MessageHeaderAttribute> and <xref:System.ServiceModel.MessageBodyMemberAttribute> attributes.</span></span> <span data-ttu-id="0a062-188">Die Eigenschaft ist eine Enumeration des <xref:System.Net.Security.ProtectionLevel?displayProperty=nameWithType>-Typs und kann auf <xref:System.Net.Security.ProtectionLevel.None> (keine Verschlüsselung oder Signatur), <xref:System.Net.Security.ProtectionLevel.Sign> (nur digitale Signatur) oder <xref:System.Net.Security.ProtectionLevel.EncryptAndSign> (sowohl Verschlüsselung als auch digitale Signatur) festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="0a062-188">The property is an enumeration of the <xref:System.Net.Security.ProtectionLevel?displayProperty=nameWithType> type and can be set to <xref:System.Net.Security.ProtectionLevel.None> (no encryption or signature), <xref:System.Net.Security.ProtectionLevel.Sign> (digital signature only), or <xref:System.Net.Security.ProtectionLevel.EncryptAndSign> (both encryption and a digital signature).</span></span> <span data-ttu-id="0a062-189">Der Standardwert ist <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>.</span><span class="sxs-lookup"><span data-stu-id="0a062-189">The default is <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>.</span></span>  
  
 <span data-ttu-id="0a062-190">Damit diese Sicherheitsfunktionen arbeiten, müssen Sie die Bindung und das Verhalten ordnungsgemäß konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="0a062-190">For these security features to work, you must properly configure the binding and behaviors.</span></span> <span data-ttu-id="0a062-191">Wenn Sie diese Sicherheitsfunktionen ohne angemessene Konfiguration verwenden (beispielsweise der Versuch der Signierung einer Nachricht ohne Bereitstellung Ihrer Anmeldeinformationen), wird zum Validierungszeitpunkt eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="0a062-191">If you use these security features without the proper configuration (for example, attempting to sign a message without supplying your credentials), an exception is thrown at validation time.</span></span>  
  
 <span data-ttu-id="0a062-192">Bei Nachrichtenheadern wird die Schutzebene für jeden Header einzeln festgelegt.</span><span class="sxs-lookup"><span data-stu-id="0a062-192">For message headers, the protection level is determined individually for each header.</span></span>  
  
 <span data-ttu-id="0a062-193">Für Nachrichtentextteile kann die Schutzebene als "minimale Schutzebene" angesehen werden.</span><span class="sxs-lookup"><span data-stu-id="0a062-193">For message body parts, the protection level can be thought of as the "minimum protection level."</span></span> <span data-ttu-id="0a062-194">Der Text verfügt jedoch unabhängig von der Anzahl der Textteile nur über eine Schutzebene.</span><span class="sxs-lookup"><span data-stu-id="0a062-194">The body has only one protection level, regardless of the number of body parts.</span></span> <span data-ttu-id="0a062-195">Die Schutzebene des Texts wird durch die höchste <xref:System.ServiceModel.MessageContractMemberAttribute.ProtectionLevel%2A>-Eigenschaftseinstellung aller Textteile bestimmt.</span><span class="sxs-lookup"><span data-stu-id="0a062-195">The protection level of the body is determined by the highest <xref:System.ServiceModel.MessageContractMemberAttribute.ProtectionLevel%2A> property setting of all the body parts.</span></span> <span data-ttu-id="0a062-196">Allerdings sollten Sie die Schutzebene eines jeden Textteils auf die tatsächlich erforderliche minimale Schutzebene festlegen.</span><span class="sxs-lookup"><span data-stu-id="0a062-196">However, you should set the protection level of each body part to the actual minimum protection level required.</span></span>  
  
 <span data-ttu-id="0a062-197">Betrachten Sie die Klasse im folgenden Codebeispiel.</span><span class="sxs-lookup"><span data-stu-id="0a062-197">Consider the class in the following code example.</span></span>  
  
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
  
 <span data-ttu-id="0a062-198">In diesem Beispiel ist der `recordID`-Header nicht geschützt, `patientName` ist `signed` und `SSN` ist verschlüsselt und signiert.</span><span class="sxs-lookup"><span data-stu-id="0a062-198">In this example, the `recordID` header is not protected, `patientName` is `signed`, and `SSN` is encrypted and signed.</span></span> <span data-ttu-id="0a062-199">Auf mindestens einen Textteil, `medicalHistory`, wurde <xref:System.Net.Security.ProtectionLevel.EncryptAndSign> angewandt. Daher ist der gesamte Nachrichtentext verschlüsselt und signiert, auch wenn die Kommentare und Diagnosetextteile niedrigere Schutzebenen festlegen.</span><span class="sxs-lookup"><span data-stu-id="0a062-199">At least one body part, `medicalHistory`, has <xref:System.Net.Security.ProtectionLevel.EncryptAndSign> applied, and thus the entire message body is encrypted and signed, even though the comments and diagnosis body parts specify lower protection levels.</span></span>  
  
## <a name="soap-action"></a><span data-ttu-id="0a062-200">SOAP-Aktion</span><span class="sxs-lookup"><span data-stu-id="0a062-200">SOAP Action</span></span>  
 <span data-ttu-id="0a062-201">SOAP- und verwandte Webdienststandards definieren eine Eigenschaft mit dem Namen `Action`, die für jede gesendete SOAP-Nachricht vorhanden sein kann.</span><span class="sxs-lookup"><span data-stu-id="0a062-201">SOAP and related Web services standards define a property called `Action` that can be present for every SOAP message sent.</span></span> <span data-ttu-id="0a062-202">Die Eigenschaften <xref:System.ServiceModel.OperationContractAttribute.Action%2A?displayProperty=nameWithType> und <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A?displayProperty=nameWithType> des Vorgangs kontrollieren den Wert dieser Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="0a062-202">The operation's <xref:System.ServiceModel.OperationContractAttribute.Action%2A?displayProperty=nameWithType> and <xref:System.ServiceModel.OperationContractAttribute.ReplyAction%2A?displayProperty=nameWithType> properties control the value of this property.</span></span>  
  
## <a name="soap-header-attributes"></a><span data-ttu-id="0a062-203">SOAP-Header-Attribute</span><span class="sxs-lookup"><span data-stu-id="0a062-203">SOAP Header Attributes</span></span>  
 <span data-ttu-id="0a062-204">Der SOAP-Standard definiert die folgenden Attribute, die in einem Header verwendet werden können:</span><span class="sxs-lookup"><span data-stu-id="0a062-204">The SOAP standard defines the following attributes that may exist on a header:</span></span>  
  
- <span data-ttu-id="0a062-205">`Actor/Role` (`Actor` in SOAP 1.1, `Role` in SOAP 1.2)</span><span class="sxs-lookup"><span data-stu-id="0a062-205">`Actor/Role` (`Actor` in SOAP 1.1, `Role` in SOAP 1.2)</span></span>  
  
- `MustUnderstand`  
  
- `Relay`  
  
 <span data-ttu-id="0a062-206">Das `Actor`-Attribut oder das `Role`-Attribut legt den URI (Uniform Resource Identifier) des Knotens fest, für den ein bestimmter Header angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="0a062-206">The `Actor` or `Role` attribute specifies the Uniform Resource Identifier (URI) of the node for which a given header is intended.</span></span> <span data-ttu-id="0a062-207">Das `MustUnderstand`-Attribut gibt an, ob der Header die Knotenverarbeitung versteht.</span><span class="sxs-lookup"><span data-stu-id="0a062-207">The `MustUnderstand` attribute specifies whether the node processing the header must understand it.</span></span> <span data-ttu-id="0a062-208">Das `Relay`-Attribut gibt an, ob der Header an Downstreamknoten weitergeleitet werden soll.</span><span class="sxs-lookup"><span data-stu-id="0a062-208">The `Relay` attribute specifies whether the header is to be relayed to downstream nodes.</span></span> <span data-ttu-id="0a062-209">WCF führt keine Verarbeitung dieser Attribute für eingehende Nachrichten aus, mit Ausnahme des- `MustUnderstand` Attributs, wie im Abschnitt "Versionsverwaltung von Nachrichten Verträgen" weiter unten in diesem Thema angegeben.</span><span class="sxs-lookup"><span data-stu-id="0a062-209">WCF does not perform any processing of these attributes on incoming messages, except for the `MustUnderstand` attribute, as specified in the "Message Contract Versioning" section later in this topic.</span></span> <span data-ttu-id="0a062-210">Allerdings wird es Ihnen ermöglicht, diese Attribute wie erforderlich zu lesen und zu schreiben (wie in der folgenden Beschreibung).</span><span class="sxs-lookup"><span data-stu-id="0a062-210">However, it allows you to read and write these attributes as necessary, as in the following description.</span></span>  
  
 <span data-ttu-id="0a062-211">Beim Versand einer Nachricht werden diese Attribute nicht standardmäßig ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="0a062-211">When sending a message, these attributes are not emitted by default.</span></span> <span data-ttu-id="0a062-212">Sie können diese auf zwei Arten ändern:</span><span class="sxs-lookup"><span data-stu-id="0a062-212">You can change this in two ways.</span></span> <span data-ttu-id="0a062-213">Sie können die Attribute statisch auf einen gewünschten Wert festlegen, indem Sie die Eigenschaften <xref:System.ServiceModel.MessageHeaderAttribute.Actor%2A?displayProperty=nameWithType>, <xref:System.ServiceModel.MessageHeaderAttribute.MustUnderstand%2A?displayProperty=nameWithType> und <xref:System.ServiceModel.MessageHeaderAttribute.Relay%2A?displayProperty=nameWithType> ändern (siehe folgendes Codebeispiel).</span><span class="sxs-lookup"><span data-stu-id="0a062-213">First, you may statically set the attributes to any desired values by changing the <xref:System.ServiceModel.MessageHeaderAttribute.Actor%2A?displayProperty=nameWithType>, <xref:System.ServiceModel.MessageHeaderAttribute.MustUnderstand%2A?displayProperty=nameWithType>, and <xref:System.ServiceModel.MessageHeaderAttribute.Relay%2A?displayProperty=nameWithType> properties, as shown in the following code example.</span></span> <span data-ttu-id="0a062-214">(Beachten Sie, dass es keine `Role`-Eigenschaft gibt; die Einrichtung der <xref:System.ServiceModel.MessageHeaderAttribute.Actor%2A>-Eigenschaft gibt das `Role`-Attribut aus, wenn Sie SOAP 1.2 verwenden).</span><span class="sxs-lookup"><span data-stu-id="0a062-214">(Note that there is no `Role` property; setting the <xref:System.ServiceModel.MessageHeaderAttribute.Actor%2A> property emits the `Role` attribute if you are using SOAP 1.2).</span></span>  
  
```csharp  
[MessageContract]  
public class BankingTransaction  
{  
  [MessageHeader(Actor="http://auditingservice.contoso.com", MustUnderstand=true)] public bool IsAudited;  
  [MessageHeader] public Operation operation;  
  [MessageBodyMember] public BankingTransactionData theData;  
}  
```  
  
 <span data-ttu-id="0a062-215">Darüber hinaus können Sie diese Attribute dynamisch per Code kontrollieren.</span><span class="sxs-lookup"><span data-stu-id="0a062-215">The second way to control these attributes is dynamically, through code.</span></span> <span data-ttu-id="0a062-216">Dies können Sie erreichen, indem Sie den gewünschten Headertyp im <xref:System.ServiceModel.MessageHeader%601>-Typ umschließen (nicht mit dem nichtgenerischen Typ zu verwechseln) und den Typ zusammen mit dem <xref:System.ServiceModel.MessageHeaderAttribute> verwenden.</span><span class="sxs-lookup"><span data-stu-id="0a062-216">You can achieve this by wrapping the desired header type in the <xref:System.ServiceModel.MessageHeader%601> type (be sure not to confuse this type with the non-generic version) and by using the type together with the <xref:System.ServiceModel.MessageHeaderAttribute>.</span></span> <span data-ttu-id="0a062-217">Daraufhin können Sie die Eigenschaften auf <xref:System.ServiceModel.MessageHeader%601> nutzen, um die SOAP-Attribute einzurichten (siehe folgendes Codebeispiel).</span><span class="sxs-lookup"><span data-stu-id="0a062-217">Then, you can use properties on the <xref:System.ServiceModel.MessageHeader%601> to set the SOAP attributes, as shown in the following code example.</span></span>  
  
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
  
 <span data-ttu-id="0a062-218">Wenn Sie sowohl den dynamischen als auch den statischen Kontrollmechanismus verwenden, werden die statischen Einstellungen als Standard verwendet, wobei diese später allerdings mithilfe des dynamischen Mechanismus überschrieben werden können (siehe folgenden Code).</span><span class="sxs-lookup"><span data-stu-id="0a062-218">If you use both the dynamic and the static control mechanisms, the static settings are used as a default but can later be overridden by using the dynamic mechanism, as shown in the following code.</span></span>  
  
```csharp  
[MessageHeader(MustUnderstand=true)] public MessageHeader<Person> documentApprover;  
// later on in the code:  
BankingTransaction bt = new BankingTransaction();  
bt.documentApprover = new MessageHeader<Person>();  
bt.documentApprover.MustUnderstand = false; // override the static default of 'true'  
```  
  
 <span data-ttu-id="0a062-219">Das Erstellen von wiederholten Headern mit einem dynamischen Attributsteuerelement ist zulässig (siehe folgenden Code).</span><span class="sxs-lookup"><span data-stu-id="0a062-219">Creating repeated headers with dynamic attribute control is allowed, as shown in the following code.</span></span>  
  
```csharp  
[MessageHeaderArray] public MessageHeader<Person> documentApprovers[];  
```  
  
 <span data-ttu-id="0a062-220">Wenn Sie diese SOAP-Attribute auf Empfängerseite lesen möchten, muss die <xref:System.ServiceModel.MessageHeader%601>-Klasse für den Header im Typ verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0a062-220">On the receiving side, reading these SOAP attributes can only be done if the <xref:System.ServiceModel.MessageHeader%601> class is used for the header in the type.</span></span> <span data-ttu-id="0a062-221">Überprüfen Sie die Eigenschaften `Actor`, `Relay` oder `MustUnderstand` des Headers des <xref:System.ServiceModel.MessageHeader%601>-Typs, um die Attributeinstellungen für die empfangene Nachricht anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="0a062-221">Examine the `Actor`, `Relay`, or `MustUnderstand` properties of a header of the <xref:System.ServiceModel.MessageHeader%601> type to discover the attribute settings on the received message.</span></span>  
  
 <span data-ttu-id="0a062-222">Wenn eine Nachricht empfangen und dann zurückgesendet wird, werden die SOAP-Attributeinstellungen nur für Header des <xref:System.ServiceModel.MessageHeader%601>-Typs wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="0a062-222">When a message is received and then sent back, the SOAP attribute settings only go round-trip for headers of the <xref:System.ServiceModel.MessageHeader%601> type.</span></span>  
  
## <a name="order-of-soap-body-parts"></a><span data-ttu-id="0a062-223">Reihenfolge von SOAP-Textteilen</span><span class="sxs-lookup"><span data-stu-id="0a062-223">Order of SOAP Body Parts</span></span>  
 <span data-ttu-id="0a062-224">In einigen Fällen müssen Sie die Reihenfolge der Textteile kontrollieren.</span><span class="sxs-lookup"><span data-stu-id="0a062-224">In some circumstances, you may need to control the order of the body parts.</span></span> <span data-ttu-id="0a062-225">Die Reihenfolge der Textelemente ist standardmäßig alphabetisch, kann aber über die <xref:System.ServiceModel.MessageBodyMemberAttribute.Order%2A?displayProperty=nameWithType>-Eigenschaft gesteuert werden.</span><span class="sxs-lookup"><span data-stu-id="0a062-225">The order of the body elements is alphabetical by default, but can be controlled by the <xref:System.ServiceModel.MessageBodyMemberAttribute.Order%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="0a062-226">Diese Eigenschaft verfügt über dieselbe Semantik wie die Eigenschaft <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A?displayProperty=nameWithType>, abgesehen vom Verhalten im Vererbungsszenario (in Nachrichtenverträgen werden Textmember vom Basistyp nicht vor den Textmembern des abgeleiteten Typs sortiert).</span><span class="sxs-lookup"><span data-stu-id="0a062-226">This property has the same semantics as the <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A?displayProperty=nameWithType> property, except for the behavior in inheritance scenarios (in message contracts, base type body members are not sorted before the derived type body members).</span></span> <span data-ttu-id="0a062-227">Weitere Informationen finden Sie unter [Datenmember-Reihenfolge](data-member-order.md).</span><span class="sxs-lookup"><span data-stu-id="0a062-227">For more information, see [Data Member Order](data-member-order.md).</span></span>  
  
 <span data-ttu-id="0a062-228">Im folgenden Beispiel käme `amount` normalerweise zuerst, da es alphabetisch an erster Stelle steht.</span><span class="sxs-lookup"><span data-stu-id="0a062-228">In the following example, `amount` would normally come first because it is first alphabetically.</span></span> <span data-ttu-id="0a062-229">Die <xref:System.ServiceModel.MessageBodyMemberAttribute.Order%2A>-Eigenschaft setzt es jedoch an die dritte Position.</span><span class="sxs-lookup"><span data-stu-id="0a062-229">However, the <xref:System.ServiceModel.MessageBodyMemberAttribute.Order%2A> property puts it into the third position.</span></span>  
  
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
  
## <a name="message-contract-versioning"></a><span data-ttu-id="0a062-230">Versionsverwaltung für Nachrichtenverträge</span><span class="sxs-lookup"><span data-stu-id="0a062-230">Message Contract Versioning</span></span>  
 <span data-ttu-id="0a062-231">Sie müssen möglicherweise gelegentlich Nachrichtenverträge ändern.</span><span class="sxs-lookup"><span data-stu-id="0a062-231">Occasionally, you may need to change message contracts.</span></span> <span data-ttu-id="0a062-232">Beispielsweise kann eine neue Version Ihrer Anwendung einen zusätzlichen Header zu einer Nachricht hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="0a062-232">For example, a new version of your application may add an extra header to a message.</span></span> <span data-ttu-id="0a062-233">Erfolgt dann ein Versand von der neuen Version zur alten, muss das System den zusätzlichen Header und einen fehlenden Header (in der anderen Richtung) verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="0a062-233">Then, when sending from the new version to the old, the system must deal with an extra header, as well as a missing header when going in the other direction.</span></span>  
  
 <span data-ttu-id="0a062-234">Für Versionsheader gelten die folgenden Regeln:</span><span class="sxs-lookup"><span data-stu-id="0a062-234">The following rules apply for versioning headers:</span></span>  
  
- <span data-ttu-id="0a062-235">WCF ist nicht auf die fehlenden Header – die entsprechenden Member haben die Standardwerte beibehalten.</span><span class="sxs-lookup"><span data-stu-id="0a062-235">WCF does not object to the missing headers—the corresponding members are left at their default values.</span></span>  
  
- <span data-ttu-id="0a062-236">WCF ignoriert auch unerwartete zusätzliche Header.</span><span class="sxs-lookup"><span data-stu-id="0a062-236">WCF also ignores unexpected extra headers.</span></span> <span data-ttu-id="0a062-237">Die Ausnahme zu dieser Regel besteht darin, dass der zusätzliche Header über ein `MustUnderstand`-Attribut verfügt, das in der eingehenden SOAP-Nachricht auf `true` festgelegt ist – in diesem Fall wird eine Ausnahme ausgelöst, da ein Header, der verstanden werden muss, nicht verarbeitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="0a062-237">The one exception to this rule is if the extra header has a `MustUnderstand` attribute set to `true` in the incoming SOAP message—in this case, an exception is thrown because a header that must be understood cannot be processed.</span></span>  
  
 <span data-ttu-id="0a062-238">Nachrichtentexte haben ähnliche Versionsregeln – sowohl fehlende als auch zusätzliche Nachrichtentextteile werden ignoriert.</span><span class="sxs-lookup"><span data-stu-id="0a062-238">Message bodies have similar versioning rules—both missing and additional message body parts are ignored.</span></span>  
  
## <a name="inheritance-considerations"></a><span data-ttu-id="0a062-239">Überlegungen zur Vererbung</span><span class="sxs-lookup"><span data-stu-id="0a062-239">Inheritance Considerations</span></span>  
 <span data-ttu-id="0a062-240">Ein Nachrichtenvertragstyp kann von einem anderen Typ erben, solange der Basistyp ebenfalls über einen Nachrichtenvertrag verfügt.</span><span class="sxs-lookup"><span data-stu-id="0a062-240">A message contract type can inherit from another type, as long as the base type also has a message contract.</span></span>  
  
 <span data-ttu-id="0a062-241">Bei der Erstellung einer Nachricht oder beim Zugriff darauf mithilfe eines Nachrichtenvertragstyps, der von anderen Nachrichtenvertragstypen erbt, gelten die folgenden Regeln.</span><span class="sxs-lookup"><span data-stu-id="0a062-241">When creating or accessing a message using a message contract type that inherits from other message contract types, the following rules apply:</span></span>  
  
- <span data-ttu-id="0a062-242">Alle Nachrichtenheader in der Vererbungshierarchie werden gesammelt, um den vollständigen Satz an Headern für die Nachricht zu bilden.</span><span class="sxs-lookup"><span data-stu-id="0a062-242">All of the message headers in the inheritance hierarchy are collected together to form the full set of headers for the message.</span></span>  
  
- <span data-ttu-id="0a062-243">Alle Nachrichtentextteile in der Vererbungshierarchie werden gesammelt, um den vollständigen Nachrichtentext zu bilden.</span><span class="sxs-lookup"><span data-stu-id="0a062-243">All of the message body parts in the inheritance hierarchy are collected together to form the full message body.</span></span> <span data-ttu-id="0a062-244">Die Textteile werden basierend auf den üblichen Sortierungsregeln sortiert (nach der <xref:System.ServiceModel.MessageBodyMemberAttribute.Order%2A?displayProperty=nameWithType>-Eigenschaft und danach alphabetisch), wobei die Position in der Vererbungshierarchie unbeachtet bleibt.</span><span class="sxs-lookup"><span data-stu-id="0a062-244">The body parts are ordered according to the usual ordering rules (by <xref:System.ServiceModel.MessageBodyMemberAttribute.Order%2A?displayProperty=nameWithType> property and then alphabetical), with no relevance to their place in the inheritance hierarchy.</span></span> <span data-ttu-id="0a062-245">Wenn Nachrichtentextteile in mehreren Ebenen der Vererbungsstruktur auftauchen, wird von der Verwendung der Nachrichtenvertragsvererbung strengstens abgeraten.</span><span class="sxs-lookup"><span data-stu-id="0a062-245">Using message contract inheritance where message body parts occur at multiple levels of the inheritance tree is strongly discouraged.</span></span> <span data-ttu-id="0a062-246">Wenn eine Basisklasse und eine abgeleitete Klasse einen Header oder einen Textteil mit demselben Namen definieren, wird der Member der Basisklasse verwendet, um den Wert des Headers oder des Textteils zu speichern.</span><span class="sxs-lookup"><span data-stu-id="0a062-246">If a base class and a derived class define a header or a body part with the same name, the member from the base-most class is used to store the value of that header or body part.</span></span>  
  
 <span data-ttu-id="0a062-247">Betrachten Sie die Klassen im folgenden Codebeispiel.</span><span class="sxs-lookup"><span data-stu-id="0a062-247">Consider the classes in the following code example.</span></span>  
  
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
  
 <span data-ttu-id="0a062-248">Die `PatientRecord`-Klasse beschreibt eine Nachricht mit einem Header mit dem Namen `ID`.</span><span class="sxs-lookup"><span data-stu-id="0a062-248">The `PatientRecord` class describes a message with one header called `ID`.</span></span> <span data-ttu-id="0a062-249">Der Header entspricht der `personID` und nicht dem `patientID`-Member, da der Basismember ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="0a062-249">The header corresponds to the `personID` and not the `patientID` member, because the base-most member is chosen.</span></span> <span data-ttu-id="0a062-250">Somit ist das `patientID`-Feld in diesem Fall unbrauchbar.</span><span class="sxs-lookup"><span data-stu-id="0a062-250">Thus, the `patientID` field is useless in this case.</span></span> <span data-ttu-id="0a062-251">Der Text der Nachricht enthält das `diagnosis`-Element, gefolgt vom `patientName`-Element, da dies die alphabetische Reihenfolge ist.</span><span class="sxs-lookup"><span data-stu-id="0a062-251">The body of the message contains the `diagnosis` element followed by the `patientName` element, because that is the alphabetical order.</span></span> <span data-ttu-id="0a062-252">Beachten Sie, dass das Beispiel ein Muster zeigt, von dem strengstens abgeraten wird: sowohl der Basisklassenvertrag als auch der abgeleitete Klassenvertrag verfügen über Nachrichtentextteile.</span><span class="sxs-lookup"><span data-stu-id="0a062-252">Notice that the example shows a pattern that is strongly discouraged: both the base and the derived message contracts have message body parts.</span></span>  
  
## <a name="wsdl-considerations"></a><span data-ttu-id="0a062-253">Überlegungen zu WSDL</span><span class="sxs-lookup"><span data-stu-id="0a062-253">WSDL Considerations</span></span>  
 <span data-ttu-id="0a062-254">Bei der Erstellung eines WSDL (Web Services Description Language)-Vertrags aus einem Dienst, der Nachrichtenverträge nutzt, ist es wichtig, daran zu denken, dass nicht alle Nachrichtenvertragsfunktionen in der resultierenden WSDL widergespiegelt werden.</span><span class="sxs-lookup"><span data-stu-id="0a062-254">When generating a Web Services Description Language (WSDL) contract from a service that uses message contracts, it is important to remember that not all message contract features are reflected in the resulting WSDL.</span></span> <span data-ttu-id="0a062-255">Beachten Sie die folgenden Punkte:</span><span class="sxs-lookup"><span data-stu-id="0a062-255">Consider the following points:</span></span>  
  
- <span data-ttu-id="0a062-256">WSDL kann den Begriff eines Arrays aus Headern nicht ausdrücken.</span><span class="sxs-lookup"><span data-stu-id="0a062-256">WSDL cannot express the concept of an array of headers.</span></span> <span data-ttu-id="0a062-257">Bei der Erstellung von Nachrichten mit einem Array aus Headern mithilfe des <xref:System.ServiceModel.MessageHeaderArrayAttribute> spiegelt die resultierende WSDL nur einen Header wider anstelle eines Array.</span><span class="sxs-lookup"><span data-stu-id="0a062-257">When creating messages with an array of headers using the <xref:System.ServiceModel.MessageHeaderArrayAttribute>, the resulting WSDL reflects only one header instead of the array.</span></span>  
  
- <span data-ttu-id="0a062-258">Das resultierende WSDL-Dokument spiegelt möglicherweise einige der Informationen auf Schutzebene nicht wider.</span><span class="sxs-lookup"><span data-stu-id="0a062-258">The resulting WSDL document may not reflect some protection-level information.</span></span>  
  
- <span data-ttu-id="0a062-259">Der in der WSDL generierte Nachrichtentyp verfügt über denselben Namen wie die Klasse des Nachrichtenvertragstyps.</span><span class="sxs-lookup"><span data-stu-id="0a062-259">The message type generated in the WSDL has the same name as the class name of the message contract type.</span></span>  
  
- <span data-ttu-id="0a062-260">Bei Verwendung desselben Nachrichtenvertrags in mehreren Vorgängen werden mehrere Nachrichtentypen im WSDL-Dokument generiert.</span><span class="sxs-lookup"><span data-stu-id="0a062-260">When using the same message contract in multiple operations, multiple message types are generated in the WSDL document.</span></span> <span data-ttu-id="0a062-261">Die Namen werden durch Hinzufügen der Zahlen "2", "3" usw. für eine aufeinanderfolgende Verwendung eindeutig gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="0a062-261">The names are made unique by adding the numbers "2", "3", and so on, for subsequent uses.</span></span> <span data-ttu-id="0a062-262">Beim Rückimport der WSDL werden mehrere Nachrichtenvertragstypen erstellt, die abgesehen von ihren Namen identisch sind.</span><span class="sxs-lookup"><span data-stu-id="0a062-262">When importing back the WSDL, multiple message contract types are created and are identical except for their names.</span></span>  
  
## <a name="soap-encoding-considerations"></a><span data-ttu-id="0a062-263">Überlegungen zur SOAP-Codierung</span><span class="sxs-lookup"><span data-stu-id="0a062-263">SOAP Encoding Considerations</span></span>  
 <span data-ttu-id="0a062-264">WCF ermöglicht es Ihnen, die Legacy-SOAP-Codierungsstil von XML zu verwenden. es wird jedoch nicht empfohlen, die Verwendung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="0a062-264">WCF allows you to use the legacy SOAP encoding style of XML, however, its use is not recommended.</span></span> <span data-ttu-id="0a062-265">Bei der Verwendung dieses Formats (durch Festlegen der `Use`-Eigenschaft auf `Encoded` auf dem <xref:System.ServiceModel.XmlSerializerFormatAttribute?displayProperty=nameWithType>, das auf den Dienstvertrag angewandt wird), gelten die folgenden zusätzlichen Überlegungen:</span><span class="sxs-lookup"><span data-stu-id="0a062-265">When using this style (by setting the `Use` property to `Encoded` on the <xref:System.ServiceModel.XmlSerializerFormatAttribute?displayProperty=nameWithType> applied to the service contract), the following additional considerations apply:</span></span>  
  
- <span data-ttu-id="0a062-266">Die Nachrichtenheader werden nicht unterstützt. Dies bedeutet, dass das Attribut <xref:System.ServiceModel.MessageHeaderAttribute> und das Arrayattribut <xref:System.ServiceModel.MessageHeaderArrayAttribute> nicht mit der SOAP-Codierung kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="0a062-266">The message headers are not supported; this means that the attribute <xref:System.ServiceModel.MessageHeaderAttribute> and the array attribute <xref:System.ServiceModel.MessageHeaderArrayAttribute> are incompatible with SOAP encoding.</span></span>  
  
- <span data-ttu-id="0a062-267">Wird der Nachrichtenvertrag nicht umbrochen, d. h., ist die Eigenschaft <xref:System.ServiceModel.MessageContractAttribute.IsWrapped%2A> auf `false` festgelegt, kann der Nachrichtenvertrag nur über einen Textteil verfügen.</span><span class="sxs-lookup"><span data-stu-id="0a062-267">If the message contract is not wrapped, that is, if the property <xref:System.ServiceModel.MessageContractAttribute.IsWrapped%2A> is set to `false`, the message contract can have only one body part.</span></span>  
  
- <span data-ttu-id="0a062-268">Der Name des Wrapperelements für den Anforderungsnachrichtenvertrag muss zum Vorgangsnamen passen.</span><span class="sxs-lookup"><span data-stu-id="0a062-268">The name of the wrapper element for the request message contract must match the operation name.</span></span> <span data-ttu-id="0a062-269">Verwenden Sie hierfür die `WrapperName`-Eigenschaft des Nachrichtenvertrags.</span><span class="sxs-lookup"><span data-stu-id="0a062-269">Use the `WrapperName` property of the message contract for this.</span></span>  
  
- <span data-ttu-id="0a062-270">Der Name des Wrapperelements für den Antwortnachrichtenvertrag muss dem Namen des Vorgangs entsprechen, der über das Suffix "Response" verfügt.</span><span class="sxs-lookup"><span data-stu-id="0a062-270">The name of the wrapper element for the response message contract must be the same as the name of the operation suffixed by 'Response'.</span></span> <span data-ttu-id="0a062-271">Verwenden Sie hierfür die <xref:System.ServiceModel.MessageContractAttribute.WrapperName%2A>-Eigenschaft des Nachrichtenvertrags.</span><span class="sxs-lookup"><span data-stu-id="0a062-271">Use the <xref:System.ServiceModel.MessageContractAttribute.WrapperName%2A> property of the message contract for this.</span></span>  
  
- <span data-ttu-id="0a062-272">SOAP-Codierung behält Objektverweise bei.</span><span class="sxs-lookup"><span data-stu-id="0a062-272">SOAP encoding preserves object references.</span></span> <span data-ttu-id="0a062-273">Betrachten Sie hierzu den folgenden Beispielcode:</span><span class="sxs-lookup"><span data-stu-id="0a062-273">For example, consider the following code.</span></span>  
  
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
  
 <span data-ttu-id="0a062-274">Nach der Serialisierung der Nachricht mithilfe von SOAP-Codierung enthalten `changedFrom` und `changedTo` nicht ihre eigenen Kopien von `p`, sondern verweisen auf die Kopie innerhalb des `changedBy`-Elements.</span><span class="sxs-lookup"><span data-stu-id="0a062-274">After serializing the message using SOAP encoding, `changedFrom` and `changedTo` do not contain their own copies of `p`, but instead point to the copy inside the `changedBy` element.</span></span>  
  
## <a name="performance-considerations"></a><span data-ttu-id="0a062-275">Überlegungen zur Leistung</span><span class="sxs-lookup"><span data-stu-id="0a062-275">Performance Considerations</span></span>  
 <span data-ttu-id="0a062-276">Jeder Nachrichtenheader und jeder Nachrichtentextteil wird unabhängig von den anderen serialisiert.</span><span class="sxs-lookup"><span data-stu-id="0a062-276">Every message header and message body part is serialized independently of the others.</span></span> <span data-ttu-id="0a062-277">Deshalb können die gleichen Namespaces wieder für jeden Header und jeden Textteil deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="0a062-277">Therefore, the same namespaces can be declared again for each header and body part.</span></span> <span data-ttu-id="0a062-278">Zur Verbesserung der Leistung, insbesondere in Bezug auf die Größe der zu übertragenden Nachricht, fassen Sie mehrere Header und Textteile in einem einzelnen Header oder einzelnen Textteil zusammen.</span><span class="sxs-lookup"><span data-stu-id="0a062-278">To improve performance, especially in terms of the size of the message on the wire, consolidate multiple headers and body parts into a single header or body part.</span></span> <span data-ttu-id="0a062-279">Beispielsweise anstelle des folgenden Codes:</span><span class="sxs-lookup"><span data-stu-id="0a062-279">For example, instead of the following code:</span></span>  
  
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
  
 <span data-ttu-id="0a062-280">Verwenden Sie diesen Code.</span><span class="sxs-lookup"><span data-stu-id="0a062-280">Use this code.</span></span>  
  
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
  
### <a name="event-based-asynchronous-and-message-contracts"></a><span data-ttu-id="0a062-281">Ereignisbasiertes asynchrones Modell und Nachrichtenverträge</span><span class="sxs-lookup"><span data-stu-id="0a062-281">Event-based Asynchronous and Message Contracts</span></span>  
 <span data-ttu-id="0a062-282">Die Entwurfsrichtlinien für das ereignisbasierte asynchrone Modell besagen, dass in den Fällen, in denen mehr als ein Wert zurückgegeben wird, ein Wert in der `Result`-Eigenschaft und die übrigen Werte in Eigenschaften des <xref:System.EventArgs>-Objekts zurückgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0a062-282">The design guidelines for the event-based asynchronous model state that if more than one value is returned, one value is returned as the `Result` property and the others are returned as properties on the <xref:System.EventArgs> object.</span></span> <span data-ttu-id="0a062-283">Wenn ein Client Metadaten mithilfe der ereignisbasierten asynchronen Befehlsoptionen importiert, und der Vorgang mehr als einen Wert zurückgibt, dann gibt das <xref:System.EventArgs>-Standardobjekt infolgedessen einen Wert in der `Result`-Eigenschaft zurück, während die übrigen Werte in Eigenschaften des <xref:System.EventArgs>-Objekts zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="0a062-283">One result of this is that if a client imports metadata using the event-based asynchronous command options and the operation returns more than one value, the default <xref:System.EventArgs> object returns one value as the `Result` property and the remainder are properties of the <xref:System.EventArgs> object.</span></span>  
  
 <span data-ttu-id="0a062-284">Wenn das Nachrichtenobjekt in der `Result`-Eigenschaft und die Rückgabewerte als Eigenschaften dieses Objekts übermittelt werden sollen, verwenden Sie die Befehlsoption `/messageContract`.</span><span class="sxs-lookup"><span data-stu-id="0a062-284">If you want to receive the message object as the `Result` property and have the returned values as properties on that object, use the `/messageContract` command option.</span></span> <span data-ttu-id="0a062-285">Damit wird eine Signatur generiert, bei der die Antwortnachricht in der `Result`-Eigenschaft des <xref:System.EventArgs>-Objekts zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="0a062-285">This generates a signature that returns the response message as the `Result` property on the <xref:System.EventArgs> object.</span></span> <span data-ttu-id="0a062-286">Alle internen Rückgabewerte sind dann Eigenschaften des Antwortnachrichtenobjekts.</span><span class="sxs-lookup"><span data-stu-id="0a062-286">All internal return values are then properties of the response message object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a062-287">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0a062-287">See also</span></span>

- [<span data-ttu-id="0a062-288">Verwenden von Datenverträgen</span><span class="sxs-lookup"><span data-stu-id="0a062-288">Using Data Contracts</span></span>](using-data-contracts.md)
- [<span data-ttu-id="0a062-289">Entwerfen und Implementieren von Diensten</span><span class="sxs-lookup"><span data-stu-id="0a062-289">Designing and Implementing Services</span></span>](../designing-and-implementing-services.md)
