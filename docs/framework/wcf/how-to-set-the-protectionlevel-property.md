---
title: 'Vorgehensweise: Festlegen der ProtectionLevel-Eigenschaft'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, security
- ProtectionLevel property
ms.assetid: 3d4e8f80-0f9e-4a26-9899-beb6584e78df
ms.openlocfilehash: 4ff835f767852da586a3a35b7f4ce2edf99db283
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320910"
---
# <a name="how-to-set-the-protectionlevel-property"></a><span data-ttu-id="51990-102">Vorgehensweise: Festlegen der ProtectionLevel-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="51990-102">How to: Set the ProtectionLevel Property</span></span>
<span data-ttu-id="51990-103">Sie können die Schutzebene festlegen, indem Sie ein entsprechendes Attribut anwenden und die Eigenschaft einrichten.</span><span class="sxs-lookup"><span data-stu-id="51990-103">You can set the protection level by applying an appropriate attribute and setting the property.</span></span> <span data-ttu-id="51990-104">Sie können den Schutz auf Dienstebene einrichten, um alle Teile einer Nachricht anzupassen. Darüber hinaus können Sie den Schutz auf stärker unterteilten Ebenen einrichten – von den Methoden zu den Nachrichtenteilen.</span><span class="sxs-lookup"><span data-stu-id="51990-104">You can set protection at the service level to affect all parts of every message, or you can set protection at increasingly granular levels, from methods to message parts.</span></span> <span data-ttu-id="51990-105">Weitere Informationen zur `ProtectionLevel`-Eigenschaft finden Sie Untergrund Legendes zu [Schutz Ebenen](understanding-protection-level.md).</span><span class="sxs-lookup"><span data-stu-id="51990-105">For more information about the `ProtectionLevel` property, see [Understanding Protection Level](understanding-protection-level.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="51990-106">Schutzebenen können nur im Code, nicht in der Konfiguration festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="51990-106">You can set protection levels only in code, not in configuration.</span></span>  
  
### <a name="to-sign-all-messages-for-a-service"></a><span data-ttu-id="51990-107">So signieren Sie alle Nachrichten für einen Dienst</span><span class="sxs-lookup"><span data-stu-id="51990-107">To sign all messages for a service</span></span>  
  
1. <span data-ttu-id="51990-108">Erstellen Sie eine Schnittstelle für den Dienst.</span><span class="sxs-lookup"><span data-stu-id="51990-108">Create an interface for the service.</span></span>  
  
2. <span data-ttu-id="51990-109">Wenden Sie das <xref:System.ServiceModel.ServiceContractAttribute>-Attribut für den Dienst an, und legen Sie die <xref:System.ServiceModel.ServiceContractAttribute.ProtectionLevel%2A>-Eigenschaft auf <xref:System.Net.Security.ProtectionLevel.Sign> fest. Dies wird im folgenden Code veranschaulicht (die Standardebene ist <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>).</span><span class="sxs-lookup"><span data-stu-id="51990-109">Apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute to the service and set the <xref:System.ServiceModel.ServiceContractAttribute.ProtectionLevel%2A> property to <xref:System.Net.Security.ProtectionLevel.Sign>, as shown in the following code (the default level is <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>).</span></span>  
  
     [!code-csharp[C_ProtectionLevel#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#1)]
     [!code-vb[C_ProtectionLevel#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#1)]  
  
### <a name="to-sign-all-message-parts-for-an-operation"></a><span data-ttu-id="51990-110">So signieren Sie alle Nachrichtenteile für einen Vorgang</span><span class="sxs-lookup"><span data-stu-id="51990-110">To sign all message parts for an operation</span></span>  
  
1. <span data-ttu-id="51990-111">Erstellen Sie eine Schnittstelle für den Dienst, und wenden Sie das <xref:System.ServiceModel.ServiceContractAttribute>-Attribut auf die Schnittstelle an.</span><span class="sxs-lookup"><span data-stu-id="51990-111">Create an interface for the service and apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute to the interface.</span></span>  
  
2. <span data-ttu-id="51990-112">Fügen Sie der Schnittstelle eine Methodendeklaration hinzu.</span><span class="sxs-lookup"><span data-stu-id="51990-112">Add a method declaration to the interface.</span></span>  
  
3. <span data-ttu-id="51990-113">Wenden Sie das <xref:System.ServiceModel.OperationContractAttribute>-Attribut auf die Methode an, und setzen Sie die <xref:System.ServiceModel.ServiceContractAttribute.ProtectionLevel%2A>-Eigenschaft auf <xref:System.Net.Security.ProtectionLevel.Sign>. Dies wird im folgenden Code veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="51990-113">Apply the <xref:System.ServiceModel.OperationContractAttribute> attribute to the method, and set the <xref:System.ServiceModel.ServiceContractAttribute.ProtectionLevel%2A> property to <xref:System.Net.Security.ProtectionLevel.Sign>, as shown in the following code.</span></span>  
  
     [!code-csharp[C_ProtectionLevel#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#2)]
     [!code-vb[C_ProtectionLevel#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#2)]  
  
## <a name="protecting-fault-messages"></a><span data-ttu-id="51990-114">Schützen von Fehlernachrichten</span><span class="sxs-lookup"><span data-stu-id="51990-114">Protecting Fault Messages</span></span>  
 <span data-ttu-id="51990-115">Ausnahmen, die für einen Dienst ausgelöst werden, können als SOAP-Fehler an einen Client gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="51990-115">Exceptions that are thrown on a service can be sent to a client as SOAP faults.</span></span> <span data-ttu-id="51990-116">Weitere Informationen zum Erstellen stark typisierter Fehler finden Sie unter [angeben und behandeln von Fehlern in Verträgen und Diensten](specifying-and-handling-faults-in-contracts-and-services.md) und Gewusst [wie: Deklarieren von Fehlern in Dienstverträgen](how-to-declare-faults-in-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="51990-116">For more information about creating strongly typed faults, see [Specifying and Handling Faults in Contracts and Services](specifying-and-handling-faults-in-contracts-and-services.md) and [How to: Declare Faults in Service Contracts](how-to-declare-faults-in-service-contracts.md).</span></span>  
  
#### <a name="to-protect-a-fault-message"></a><span data-ttu-id="51990-117">So schützen Sie eine Fehlernachricht</span><span class="sxs-lookup"><span data-stu-id="51990-117">To protect a fault message</span></span>  
  
1. <span data-ttu-id="51990-118">Erstellen Sie einen Typ, der die Fehlernachricht darstellt.</span><span class="sxs-lookup"><span data-stu-id="51990-118">Create a type that represents the fault message.</span></span> <span data-ttu-id="51990-119">Das folgende Beispiel erstellt eine Klasse mit dem Namen `MathFault` und zwei Feldern.</span><span class="sxs-lookup"><span data-stu-id="51990-119">The following example creates a class named `MathFault` with two fields.</span></span>  
  
2. <span data-ttu-id="51990-120">Wenden Sie das <xref:System.Runtime.Serialization.DataContractAttribute>-Attribut auf den Typ und das <xref:System.Runtime.Serialization.DataMemberAttribute>-Attribut für jedes Feld an, das serialisiert werden soll. Der folgende Code veranschaulicht dies.</span><span class="sxs-lookup"><span data-stu-id="51990-120">Apply the <xref:System.Runtime.Serialization.DataContractAttribute> attribute to the type and a <xref:System.Runtime.Serialization.DataMemberAttribute> attribute to each field that should be serialized, as shown in the following code.</span></span>  
  
     [!code-csharp[C_ProtectionLevel#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#3)]
     [!code-vb[C_ProtectionLevel#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#3)]  
  
3. <span data-ttu-id="51990-121">Wenden Sie in der Schnittstelle, die den Fehler zurückgibt, das <xref:System.ServiceModel.FaultContractAttribute>-Attribut auf die Methode an, die den Fehler zurückgibt, und setzen Sie den `detailType`-Parameter auf den Typ der Fehlerklasse.</span><span class="sxs-lookup"><span data-stu-id="51990-121">In the interface that will return the fault, apply the <xref:System.ServiceModel.FaultContractAttribute> attribute to the method that will return the fault and set the `detailType` parameter to the type of the fault class.</span></span>  
  
4. <span data-ttu-id="51990-122">Setzen Sie ebenfalls im Konstruktor die <xref:System.ServiceModel.FaultContractAttribute.ProtectionLevel%2A>-Eigenschaft auf <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>. Dies wird im folgenden Code veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="51990-122">Also in the constructor, set the <xref:System.ServiceModel.FaultContractAttribute.ProtectionLevel%2A> property to <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>, as shown in the following code.</span></span>  
  
     [!code-csharp[C_ProtectionLevel#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#4)]
     [!code-vb[C_ProtectionLevel#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#4)]  
  
## <a name="protecting-message-parts"></a><span data-ttu-id="51990-123">Schützen von Nachrichtenteilen</span><span class="sxs-lookup"><span data-stu-id="51990-123">Protecting Message Parts</span></span>  
 <span data-ttu-id="51990-124">Verwenden Sie einen Nachrichtenvertrag, um Teile einer Nachricht zu schützen.</span><span class="sxs-lookup"><span data-stu-id="51990-124">Use a message contract to protect parts of a message.</span></span> <span data-ttu-id="51990-125">Weitere Informationen zu Nachrichten Verträgen finden Sie unter [Verwenden von Nachrichten Verträgen](./feature-details/using-message-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="51990-125">For more information about message contracts, see [Using Message Contracts](./feature-details/using-message-contracts.md).</span></span>  
  
#### <a name="to-protect-a-message-body"></a><span data-ttu-id="51990-126">So schützen Sie einen Nachrichtentext</span><span class="sxs-lookup"><span data-stu-id="51990-126">To protect a message body</span></span>  
  
1. <span data-ttu-id="51990-127">Erstellen Sie einen Typ, der die Nachricht darstellt.</span><span class="sxs-lookup"><span data-stu-id="51990-127">Create a type that represents the message.</span></span> <span data-ttu-id="51990-128">Das folgende Beispiel erstellt eine `Company`-Klasse mit zwei Feldern, `CompanyName` und `CompanyID`.</span><span class="sxs-lookup"><span data-stu-id="51990-128">The following example creates a `Company` class with two fields, `CompanyName` and `CompanyID`.</span></span>  
  
2. <span data-ttu-id="51990-129">Wenden Sie das <xref:System.ServiceModel.MessageContractAttribute>-Attribut auf die Klasse an, und setzen Sie die <xref:System.ServiceModel.MessageContractAttribute.ProtectionLevel%2A>-Eigenschaft auf <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>.</span><span class="sxs-lookup"><span data-stu-id="51990-129">Apply the <xref:System.ServiceModel.MessageContractAttribute> attribute to the class and set the <xref:System.ServiceModel.MessageContractAttribute.ProtectionLevel%2A> property to <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>.</span></span>  
  
3. <span data-ttu-id="51990-130">Wenden Sie das <xref:System.ServiceModel.MessageHeaderAttribute>-Attribut auf ein Feld an, das als Nachrichtenheader ausgedrückt wird, und setzen Sie die `ProtectionLevel`-Eigenschaft auf <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>.</span><span class="sxs-lookup"><span data-stu-id="51990-130">Apply the <xref:System.ServiceModel.MessageHeaderAttribute> attribute to a field that will be expressed as a message header and set the `ProtectionLevel` property to <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>.</span></span>  
  
4. <span data-ttu-id="51990-131">Wenden Sie die <xref:System.ServiceModel.MessageBodyMemberAttribute> auf jedes Feld an, das als Teil des Nachrichten Texts ausgedrückt wird, und legen Sie die Eigenschaft `ProtectionLevel` auf <xref:System.Net.Security.ProtectionLevel.EncryptAndSign> fest, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="51990-131">Apply the <xref:System.ServiceModel.MessageBodyMemberAttribute> to any field that will be expressed as part of the message body, and set the `ProtectionLevel` property to <xref:System.Net.Security.ProtectionLevel.EncryptAndSign>, as shown in the following example.</span></span>  
  
     [!code-csharp[C_ProtectionLevel#5](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#5)]
     [!code-vb[C_ProtectionLevel#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="51990-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="51990-132">Example</span></span>  
 <span data-ttu-id="51990-133">Im folgenden Beispiel wird die `ProtectionLevel`-Eigenschaft mehrerer Attributklassen an verschiedenen Stellen in einem Dienst festgelegt.</span><span class="sxs-lookup"><span data-stu-id="51990-133">The following example sets the `ProtectionLevel` property of several attribute classes at various places in a service.</span></span>  
  
 [!code-csharp[C_ProtectionLevel#6](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#6)]
 [!code-vb[C_ProtectionLevel#6](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#6)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="51990-134">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="51990-134">Compiling the Code</span></span>  
 <span data-ttu-id="51990-135">Der folgende Code zeigt die für die Kompilierung des Beispielcodes erforderlichen Namespaces.</span><span class="sxs-lookup"><span data-stu-id="51990-135">The following code shows the namespaces required to compile the example code.</span></span>  
  
 [!code-csharp[C_ProtectionLevel#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_protectionlevel/cs/source.cs#0)]
 [!code-vb[C_ProtectionLevel#0](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_protectionlevel/vb/source.vb#0)]  
  
## <a name="see-also"></a><span data-ttu-id="51990-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="51990-136">See also</span></span>

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
- <xref:System.ServiceModel.FaultContractAttribute>
- <xref:System.ServiceModel.MessageContractAttribute>
- <xref:System.ServiceModel.MessageBodyMemberAttribute>
- [<span data-ttu-id="51990-137">Grundlagen der Schutzebene</span><span class="sxs-lookup"><span data-stu-id="51990-137">Understanding Protection Level</span></span>](understanding-protection-level.md)
