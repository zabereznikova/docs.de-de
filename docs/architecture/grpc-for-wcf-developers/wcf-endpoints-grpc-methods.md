---
title: 'WCF-Endpunkte und GrpC-Methoden: GrpC für WCF-Entwickler'
description: Vergleich von WCF-Endpunkten, die mit den Attributen ServiceContract und OperationContract deklariert wurden, und den in protobuf deklarierten GrpC-Methoden
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 1cb7fedf1fbb632438134375306801f356d7b921
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841300"
---
# <a name="wcf-endpoints-and-grpc-methods"></a><span data-ttu-id="f2c36-103">WCF-Endpunkte und GrpC-Methoden</span><span class="sxs-lookup"><span data-stu-id="f2c36-103">WCF endpoints and gRPC methods</span></span>

<span data-ttu-id="f2c36-104">Wenn Sie in WCF den Anwendungscode schreiben, verwenden Sie eine der folgenden Methoden:</span><span class="sxs-lookup"><span data-stu-id="f2c36-104">In WCF, when you're writing your application code, you use one of the following methods:</span></span>

- <span data-ttu-id="f2c36-105">Sie schreiben den Anwendungscode in einer Klasse und ergänzen Methoden mit dem [OperationContract](xref:System.ServiceModel.OperationContractAttribute) -Attribut.</span><span class="sxs-lookup"><span data-stu-id="f2c36-105">You write the application code in a class and decorate methods with the [OperationContract](xref:System.ServiceModel.OperationContractAttribute) attribute.</span></span>
- <span data-ttu-id="f2c36-106">Sie deklarieren eine Schnittstelle für den Dienst und fügen [OperationContract](xref:System.ServiceModel.OperationContractAttribute) -Attribute zur Schnittstelle hinzu.</span><span class="sxs-lookup"><span data-stu-id="f2c36-106">You declare an interface for the service and add [OperationContract](xref:System.ServiceModel.OperationContractAttribute) attributes to the interface.</span></span>

<span data-ttu-id="f2c36-107">Beispielsweise könnte die WCF-Entsprechung des `greet.proto` Greeter-Dienstanbieter wie folgt geschrieben werden:</span><span class="sxs-lookup"><span data-stu-id="f2c36-107">For example, the WCF equivalent of the `greet.proto` Greeter service might be written as follows:</span></span>

```csharp
[ServiceContract]
public interface IGreeterService
{
    [OperationContract]
    string SayHello(string name);
}
```

<span data-ttu-id="f2c36-108">Kapitel 3 zeigte, dass protobuf-Nachrichten Definitionen verwendet werden, um Daten Klassen zu generieren.</span><span class="sxs-lookup"><span data-stu-id="f2c36-108">Chapter 3 showed that Protobuf message definitions are used to generate data classes.</span></span> <span data-ttu-id="f2c36-109">Dienst-und Methoden Deklarationen werden verwendet, um Basisklassen zu generieren, von denen Sie erben, um den Dienst zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="f2c36-109">Service and method declarations are used to generate base classes that you inherit from to implement the service.</span></span> <span data-ttu-id="f2c36-110">Sie deklarieren nur die Methoden, die in der `.proto`-Datei implementiert werden sollen, und der Compiler generiert eine Basisklasse mit virtuellen Methoden, die Sie überschreiben müssen.</span><span class="sxs-lookup"><span data-stu-id="f2c36-110">You just declare the methods to be implemented in the `.proto` file, and the compiler generates a base class with virtual methods you must override.</span></span>

## <a name="operationcontract-properties"></a><span data-ttu-id="f2c36-111">OperationContract-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="f2c36-111">OperationContract properties</span></span>

<span data-ttu-id="f2c36-112">Das [OperationContract](xref:System.ServiceModel.OperationContractAttribute) -Attribut verfügt über Eigenschaften zum Steuern oder verfeinern der Funktionsweise.</span><span class="sxs-lookup"><span data-stu-id="f2c36-112">The [OperationContract](xref:System.ServiceModel.OperationContractAttribute) attribute has properties to control or refine how it works.</span></span> <span data-ttu-id="f2c36-113">GrpC-Methoden bieten diese Art von Kontrolle nicht.</span><span class="sxs-lookup"><span data-stu-id="f2c36-113">gRPC methods don’t offer this type of control.</span></span> <span data-ttu-id="f2c36-114">In der folgenden Tabelle werden diese `OperationContract` Eigenschaften festgelegt, und es wird erläutert, wie die von Ihnen angegebene Funktionalität in GrpC behandelt wird:</span><span class="sxs-lookup"><span data-stu-id="f2c36-114">The following table sets out those `OperationContract` properties and how the functionality they specify is (or isn’t) dealt with in gRPC:</span></span>

| <span data-ttu-id="f2c36-115">`OperationContract` -Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="f2c36-115">`OperationContract` property</span></span> | <span data-ttu-id="f2c36-116">gRPC</span><span class="sxs-lookup"><span data-stu-id="f2c36-116">gRPC</span></span>                                             |
| ---------------------------- | ------------------------------------------------ |
| <xref:System.ServiceModel.OperationContractAttribute.Action>             | <span data-ttu-id="f2c36-117">Der URI, der den Vorgang identifiziert.</span><span class="sxs-lookup"><span data-stu-id="f2c36-117">URI identifying the operation.</span></span> <span data-ttu-id="f2c36-118">GrpC verwendet den Namen der `package`, `service` und `rpc` aus der `.proto` Datei.</span><span class="sxs-lookup"><span data-stu-id="f2c36-118">gRPC uses the name of the `package`, `service` and `rpc` from the `.proto` file.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern>       | <span data-ttu-id="f2c36-119">Alle GrpC-Dienst Methoden geben `Task` Objekte zurück.</span><span class="sxs-lookup"><span data-stu-id="f2c36-119">All gRPC service methods return `Task` objects.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.IsInitiating>       | <span data-ttu-id="f2c36-120">Siehe den Hinweis unten.</span><span class="sxs-lookup"><span data-stu-id="f2c36-120">See note below.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.IsOneWay>           | <span data-ttu-id="f2c36-121">Unidirektionale GrpC-Methoden geben `Empty` Ergebnisse zurück oder verwenden Client-Streaming.</span><span class="sxs-lookup"><span data-stu-id="f2c36-121">One-way gRPC methods return `Empty` results or use client streaming.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.IsTerminating>      | <span data-ttu-id="f2c36-122">Siehe den Hinweis unten.</span><span class="sxs-lookup"><span data-stu-id="f2c36-122">See note below.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.Name>               | <span data-ttu-id="f2c36-123">SOAP-bezogen, keine Bedeutung in GrpC.</span><span class="sxs-lookup"><span data-stu-id="f2c36-123">SOAP-related, no meaning in gRPC.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.ProtectionLevel>    | <span data-ttu-id="f2c36-124">Keine Nachrichten Verschlüsselung; die Netzwerk Verschlüsselung wird auf Transport Ebene (TLS über http/2) verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="f2c36-124">No message encryption; network encryption handled at the transport layer (TLS over HTTP/2).</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.ReplyAction>        | <span data-ttu-id="f2c36-125">SOAP-bezogen, keine Bedeutung in GrpC.</span><span class="sxs-lookup"><span data-stu-id="f2c36-125">SOAP-related, no meaning in gRPC.</span></span> |

<span data-ttu-id="f2c36-126">Mit der `IsInitiating`-Eigenschaft können Sie angeben, dass eine Methode in einem [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) nicht als erste Methode aufgerufen werden kann, die als Teil einer Sitzung aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="f2c36-126">The `IsInitiating` property lets you indicate that a method within a [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) can't be the first method called as part of a session.</span></span> <span data-ttu-id="f2c36-127">Die `IsTerminating`-Eigenschaft bewirkt, dass der Server die Sitzung schließt, nachdem ein Vorgang aufgerufen wurde (oder der Client, wenn er auf einem Rückruf Client verwendet wird).</span><span class="sxs-lookup"><span data-stu-id="f2c36-127">The `IsTerminating` property causes the server to close the session after an operation is called (or the client, if used on a callback client).</span></span> <span data-ttu-id="f2c36-128">In GrpC werden Streams von einzelnen Methoden erstellt und explizit geschlossen.</span><span class="sxs-lookup"><span data-stu-id="f2c36-128">In gRPC, streams are created by single methods and closed explicitly.</span></span> <span data-ttu-id="f2c36-129">Siehe [GrpC Streaming](rpc-types.md#grpc-streaming).</span><span class="sxs-lookup"><span data-stu-id="f2c36-129">See [gRPC streaming](rpc-types.md#grpc-streaming).</span></span>

<span data-ttu-id="f2c36-130">Weitere Informationen zur Sicherheit und Verschlüsselung von GrpC finden Sie in [Kapitel 6](security.md).</span><span class="sxs-lookup"><span data-stu-id="f2c36-130">For more information on gRPC security and encryption, see [chapter 6](security.md).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="f2c36-131">[Zurück](wcf-services-to-grpc-comparison.md)
>[Weiter](wcf-bindings.md)</span><span class="sxs-lookup"><span data-stu-id="f2c36-131">[Previous](wcf-services-to-grpc-comparison.md)
[Next](wcf-bindings.md)</span></span>
