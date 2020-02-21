---
title: 'WCF-Endpunkte und GrpC-Methoden: GrpC für WCF-Entwickler'
description: Vergleich von WCF-Endpunkten, die mit den Attributen ServiceContract und OperationContract deklariert wurden, und den in protobuf deklarierten GrpC-Methoden
ms.date: 09/02/2019
ms.openlocfilehash: 1bc6ecbc73bfc0a58393e4c28672b897ed6f2f15
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503429"
---
# <a name="wcf-endpoints-and-grpc-methods"></a><span data-ttu-id="bcb5e-103">WCF-Endpunkte und GrpC-Methoden</span><span class="sxs-lookup"><span data-stu-id="bcb5e-103">WCF endpoints and gRPC methods</span></span>

<span data-ttu-id="bcb5e-104">Wenn Sie in Windows Communication Foundation (WCF) den Anwendungscode schreiben, verwenden Sie eine der folgenden Methoden:</span><span class="sxs-lookup"><span data-stu-id="bcb5e-104">In Windows Communication Foundation (WCF), when you're writing your application code, you use one of the following methods:</span></span>

- <span data-ttu-id="bcb5e-105">Sie schreiben den Anwendungscode in einer Klasse und ergänzen Methoden mit dem [OperationContract](xref:System.ServiceModel.OperationContractAttribute) -Attribut.</span><span class="sxs-lookup"><span data-stu-id="bcb5e-105">You write the application code in a class and decorate methods with the [OperationContract](xref:System.ServiceModel.OperationContractAttribute) attribute.</span></span>
- <span data-ttu-id="bcb5e-106">Sie deklarieren eine Schnittstelle für den Dienst und fügen [OperationContract](xref:System.ServiceModel.OperationContractAttribute) -Attribute zur Schnittstelle hinzu.</span><span class="sxs-lookup"><span data-stu-id="bcb5e-106">You declare an interface for the service and add [OperationContract](xref:System.ServiceModel.OperationContractAttribute) attributes to the interface.</span></span>

<span data-ttu-id="bcb5e-107">Beispielsweise könnte die WCF-Entsprechung des `greet.proto` Greeter-Dienstanbieter wie folgt geschrieben werden:</span><span class="sxs-lookup"><span data-stu-id="bcb5e-107">For example, the WCF equivalent of the `greet.proto` Greeter service might be written as follows:</span></span>

```csharp
[ServiceContract]
public interface IGreeterService
{
    [OperationContract]
    string SayHello(string name);
}
```

<span data-ttu-id="bcb5e-108">Kapitel 3 zeigte, dass protobuf-Nachrichten Definitionen verwendet werden, um Daten Klassen zu generieren.</span><span class="sxs-lookup"><span data-stu-id="bcb5e-108">Chapter 3 showed that Protobuf message definitions are used to generate data classes.</span></span> <span data-ttu-id="bcb5e-109">Dienst-und Methoden Deklarationen werden verwendet, um Basisklassen zu generieren, von denen Sie erben, um den Dienst zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="bcb5e-109">Service and method declarations are used to generate base classes that you inherit from to implement the service.</span></span> <span data-ttu-id="bcb5e-110">Sie deklarieren nur die Methoden, die in der `.proto`-Datei implementiert werden sollen, und der Compiler generiert eine Basisklasse mit virtuellen Methoden, die Sie überschreiben müssen.</span><span class="sxs-lookup"><span data-stu-id="bcb5e-110">You just declare the methods to be implemented in the `.proto` file, and the compiler generates a base class with virtual methods that you must override.</span></span>

## <a name="operationcontract-properties"></a><span data-ttu-id="bcb5e-111">OperationContract-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="bcb5e-111">OperationContract properties</span></span>

<span data-ttu-id="bcb5e-112">Das [OperationContract](xref:System.ServiceModel.OperationContractAttribute) -Attribut verfügt über Eigenschaften zum Steuern oder verfeinern der Funktionsweise.</span><span class="sxs-lookup"><span data-stu-id="bcb5e-112">The [OperationContract](xref:System.ServiceModel.OperationContractAttribute) attribute has properties to control or refine how it works.</span></span> <span data-ttu-id="bcb5e-113">GrpC-Methoden bieten diese Art von Kontrolle nicht.</span><span class="sxs-lookup"><span data-stu-id="bcb5e-113">gRPC methods don't offer this type of control.</span></span> <span data-ttu-id="bcb5e-114">In der folgenden Tabelle sind die `OperationContract` Eigenschaften aufgeführt, und es wird beschrieben, wie die von Ihnen angegebenen Funktionen in GrpC behandelt werden:</span><span class="sxs-lookup"><span data-stu-id="bcb5e-114">The following table lists those `OperationContract` properties and describes how the functionality that they specify is (or isn't) dealt with in gRPC:</span></span>

| <span data-ttu-id="bcb5e-115">`OperationContract`-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="bcb5e-115">`OperationContract` property</span></span> | <span data-ttu-id="bcb5e-116">gRPC</span><span class="sxs-lookup"><span data-stu-id="bcb5e-116">gRPC</span></span>                                             |
| ---------------------------- | ------------------------------------------------ |
| <xref:System.ServiceModel.OperationContractAttribute.Action>             | <span data-ttu-id="bcb5e-117">Ein URI identifiziert den Vorgang.</span><span class="sxs-lookup"><span data-stu-id="bcb5e-117">A URI identifies the operation.</span></span> <span data-ttu-id="bcb5e-118">GrpC verwendet den Namen `package`, `service`und `rpc` aus der `.proto` Datei.</span><span class="sxs-lookup"><span data-stu-id="bcb5e-118">gRPC uses the name of `package`, `service`, and `rpc` from the `.proto` file.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern>       | <span data-ttu-id="bcb5e-119">Alle GrpC-Dienst Methoden geben `Task` Objekte zurück.</span><span class="sxs-lookup"><span data-stu-id="bcb5e-119">All gRPC service methods return `Task` objects.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.IsInitiating>       | <span data-ttu-id="bcb5e-120">Weitere Informationen finden Sie im Absatz nach dieser Tabelle.</span><span class="sxs-lookup"><span data-stu-id="bcb5e-120">See the paragraph after this table.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.IsOneWay>           | <span data-ttu-id="bcb5e-121">Unidirektionale GrpC-Methoden geben `Empty` Ergebnisse zurück oder verwenden Client-Streaming.</span><span class="sxs-lookup"><span data-stu-id="bcb5e-121">One-way gRPC methods return `Empty` results or use client streaming.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.IsTerminating>      | <span data-ttu-id="bcb5e-122">Weitere Informationen finden Sie im Absatz nach dieser Tabelle.</span><span class="sxs-lookup"><span data-stu-id="bcb5e-122">See the paragraph after this table.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.Name>               | <span data-ttu-id="bcb5e-123">Diese Eigenschaft ist SOAP-bezogen und hat keine Bedeutung in GrpC.</span><span class="sxs-lookup"><span data-stu-id="bcb5e-123">This property is SOAP related and has no meaning in gRPC.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.ProtectionLevel>    | <span data-ttu-id="bcb5e-124">Es gibt keine Nachrichten Verschlüsselung.</span><span class="sxs-lookup"><span data-stu-id="bcb5e-124">There's no message encryption.</span></span> <span data-ttu-id="bcb5e-125">Die Netzwerk Verschlüsselung wird auf Transport Ebene (TLS über http/2) gehandhabt.</span><span class="sxs-lookup"><span data-stu-id="bcb5e-125">Network encryption is handled at the transport layer (TLS over HTTP/2).</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.ReplyAction>        | <span data-ttu-id="bcb5e-126">Diese Eigenschaft ist SOAP-bezogen und hat keine Bedeutung in GrpC.</span><span class="sxs-lookup"><span data-stu-id="bcb5e-126">This property is SOAP related and has no meaning in gRPC.</span></span> |

<span data-ttu-id="bcb5e-127">Mit der `IsInitiating`-Eigenschaft können Sie angeben, dass eine Methode in [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) nicht als erste Methode aufgerufen werden kann, die als Teil einer Sitzung aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="bcb5e-127">The `IsInitiating` property lets you indicate that a method within [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) can't be the first method called as part of a session.</span></span> <span data-ttu-id="bcb5e-128">Die `IsTerminating`-Eigenschaft bewirkt, dass der Server die Sitzung schließt, nachdem ein Vorgang aufgerufen wurde (oder der Client, wenn die-Eigenschaft auf einem Rückruf Client verwendet wird).</span><span class="sxs-lookup"><span data-stu-id="bcb5e-128">The `IsTerminating` property causes the server to close the session after an operation is called (or the client, if the property is used on a callback client).</span></span> <span data-ttu-id="bcb5e-129">In GrpC werden Streams von einzelnen Methoden erstellt und explizit geschlossen.</span><span class="sxs-lookup"><span data-stu-id="bcb5e-129">In gRPC, streams are created by single methods and closed explicitly.</span></span> <span data-ttu-id="bcb5e-130">Siehe [GrpC Streaming](rpc-types.md#grpc-streaming).</span><span class="sxs-lookup"><span data-stu-id="bcb5e-130">See [gRPC streaming](rpc-types.md#grpc-streaming).</span></span>

<span data-ttu-id="bcb5e-131">Weitere Informationen zur Sicherheit und Verschlüsselung von GrpC finden Sie in [Kapitel 6](security.md).</span><span class="sxs-lookup"><span data-stu-id="bcb5e-131">For more information on gRPC security and encryption, see [chapter 6](security.md).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="bcb5e-132">[Zurück](wcf-services-to-grpc-comparison.md)
>[Weiter](wcf-bindings.md)</span><span class="sxs-lookup"><span data-stu-id="bcb5e-132">[Previous](wcf-services-to-grpc-comparison.md)
[Next](wcf-bindings.md)</span></span>
