---
title: 'Vorgehensweise: Implementieren eines asynchronen Dienstvorgangs'
description: Erfahren Sie mehr über die Struktur eines asynchronen Dienst Vorgangs in wfc. Ein Dienst Vorgang kann asynchron oder synchron implementiert werden.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4e5d2ea5-d8f8-4712-bd18-ea3c5461702c
ms.openlocfilehash: 7b30fa21e32acf2a462db4f9f39b7e1c459a2949
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90553544"
---
# <a name="how-to-implement-an-asynchronous-service-operation"></a><span data-ttu-id="24ae4-104">Vorgehensweise: Implementieren eines asynchronen Dienstvorgangs</span><span class="sxs-lookup"><span data-stu-id="24ae4-104">How to: Implement an Asynchronous Service Operation</span></span>
<span data-ttu-id="24ae4-105">In Windows Communication Foundation (WCF)-Anwendungen kann ein Dienst Vorgang asynchron oder synchron implementiert werden, ohne dem Client zu diktieren, wie er aufgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="24ae4-105">In Windows Communication Foundation (WCF) applications, a service operation can be implemented asynchronously or synchronously without dictating to the client how to call it.</span></span> <span data-ttu-id="24ae4-106">Asynchrone Dienst Vorgänge können z. b. synchron aufgerufen werden, und synchrone Dienst Vorgänge können asynchron aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="24ae4-106">For example, asynchronous service operations can be called synchronously, and synchronous service operations can be called asynchronously.</span></span> <span data-ttu-id="24ae4-107">Ein Beispiel, das zeigt, wie ein Vorgang asynchron in einer Client Anwendung aufgerufen wird, finden Sie unter Gewusst [wie: Asynchrones Abrufen von Dienst Vorgängen](./feature-details/how-to-call-wcf-service-operations-asynchronously.md).</span><span class="sxs-lookup"><span data-stu-id="24ae4-107">For an example that shows how to call an operation asynchronously in a client application, see [How to: Call Service Operations Asynchronously](./feature-details/how-to-call-wcf-service-operations-asynchronously.md).</span></span> <span data-ttu-id="24ae4-108">Weitere Informationen zu synchronen und asynchronen Vorgängen finden Sie unter [Entwerfen von Dienstverträgen](designing-service-contracts.md) und [synchronen und asynchronen Vorgängen](synchronous-and-asynchronous-operations.md).</span><span class="sxs-lookup"><span data-stu-id="24ae4-108">For more information about synchronous and asynchronous operations, see [Designing Service Contracts](designing-service-contracts.md) and [Synchronous and Asynchronous Operations](synchronous-and-asynchronous-operations.md).</span></span> <span data-ttu-id="24ae4-109">In diesem Thema wird die grundlegende Struktur eines asynchronen Dienstvorgangs beschrieben (der Code ist nicht vollständig).</span><span class="sxs-lookup"><span data-stu-id="24ae4-109">This topic describes the basic structure of an asynchronous service operation, the code is not complete.</span></span> <span data-ttu-id="24ae4-110">Ein umfassendes Beispiel sowohl der Dienst-als auch der Clientseite finden Sie unter [Asynchronous](/previous-versions/dotnet/netframework-4.0/ms751505(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="24ae4-110">For a complete example of both the service and client sides, see [Asynchronous](/previous-versions/dotnet/netframework-4.0/ms751505(v=vs.100)).</span></span>  
  
### <a name="implement-a-service-operation-asynchronously"></a><span data-ttu-id="24ae4-111">Asynchrones Implementieren eines Dienstvorgangs</span><span class="sxs-lookup"><span data-stu-id="24ae4-111">Implement a service operation asynchronously</span></span>  
  
1. <span data-ttu-id="24ae4-112">Deklarieren Sie im Dienstvertrag ein asynchrones Methodenpaar entsprechend den .NET-Richtlinien für den asynchronen Entwurf.</span><span class="sxs-lookup"><span data-stu-id="24ae4-112">In your service contract, declare an asynchronous method pair according to the .NET asynchronous design guidelines.</span></span> <span data-ttu-id="24ae4-113">Die Methode `Begin` nimmt einen Parameter, ein Rückrufobjekt und ein Statusobjekt und gibt eine <xref:System.IAsyncResult?displayProperty=nameWithType>-Methode und eine entsprechende `End`-Methode aus, die ein <xref:System.IAsyncResult?displayProperty=nameWithType> nimmt und den Rückgabewert ausgibt.</span><span class="sxs-lookup"><span data-stu-id="24ae4-113">The `Begin` method takes a parameter, a callback object, and a state object, and returns a <xref:System.IAsyncResult?displayProperty=nameWithType> and a matching `End` method that takes a <xref:System.IAsyncResult?displayProperty=nameWithType> and returns the return value.</span></span> <span data-ttu-id="24ae4-114">Weitere Informationen zu asynchronen Aufrufen finden Sie unter [Entwurfsmuster für die asynchrone Programmierung](../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md).</span><span class="sxs-lookup"><span data-stu-id="24ae4-114">For more information about asynchronous calls, see [Asynchronous Programming Design Patterns](../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md).</span></span>  
  
2. <span data-ttu-id="24ae4-115">Markieren Sie die Methode `Begin` des asynchronen Methodenpaars mit dem Attribut <xref:System.ServiceModel.OperationContractAttribute?displayProperty=nameWithType>, und legen Sie die Eigenschaft <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A?displayProperty=nameWithType> auf `true` fest.</span><span class="sxs-lookup"><span data-stu-id="24ae4-115">Mark the `Begin` method of the asynchronous method pair with the <xref:System.ServiceModel.OperationContractAttribute?displayProperty=nameWithType> attribute and set the <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="24ae4-116">Der folgende Code führt beispielsweise die Schritte 1 und 2 aus.</span><span class="sxs-lookup"><span data-stu-id="24ae4-116">For example, the following code performs steps 1 and 2.</span></span>  
  
     [!code-csharp[C_SyncAsyncClient#6](../../../samples/snippets/csharp/VS_Snippets_CFX/c_syncasyncclient/cs/services.cs#6)]
     [!code-vb[C_SyncAsyncClient#6](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_syncasyncclient/vb/services.vb#6)]  
  
3. <span data-ttu-id="24ae4-117">Implementieren Sie das Methodenpaar `Begin/End` in Ihrer Dienstklasse gemäß den asynchronen Entwurfsrichtlinien von .NET.</span><span class="sxs-lookup"><span data-stu-id="24ae4-117">Implement the `Begin/End` method pair in your service class according to the asynchronous design guidelines.</span></span> <span data-ttu-id="24ae4-118">Das folgende Codebeispiel zeigt eine Implementierung, in der eine Zeichenkette sowohl in den Teilen `Begin` als auch `End` des asynchronen Dienstvorgangs auf die Konsole geschrieben ist, und der Rückgabewert des Vorgangs `End` wird an den Client ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="24ae4-118">For example, the following code example shows an implementation in which a string is written to the console in both the `Begin` and `End` portions of the asynchronous service operation, and the return value of the `End` operation is returned to the client.</span></span> <span data-ttu-id="24ae4-119">Das vollständige Codebeispiel finden Sie im Abschnitt "Beispiel".</span><span class="sxs-lookup"><span data-stu-id="24ae4-119">For the complete code example, see the Example section.</span></span>  
  
     [!code-csharp[C_SyncAsyncClient#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_syncasyncclient/cs/services.cs#3)]
     [!code-vb[C_SyncAsyncClient#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_syncasyncclient/vb/services.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="24ae4-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="24ae4-120">Example</span></span>  
 <span data-ttu-id="24ae4-121">Das folgende Codebeispiel zeigt:</span><span class="sxs-lookup"><span data-stu-id="24ae4-121">The following code examples show:</span></span>  
  
1. <span data-ttu-id="24ae4-122">Eine Dienstvertragschnittstelle mit:</span><span class="sxs-lookup"><span data-stu-id="24ae4-122">A service contract interface with:</span></span>  
  
    1. <span data-ttu-id="24ae4-123">Einem synchronen `SampleMethod`-Vorgang.</span><span class="sxs-lookup"><span data-stu-id="24ae4-123">A synchronous `SampleMethod` operation.</span></span>  
  
    2. <span data-ttu-id="24ae4-124">Einem asynchronen `BeginSampleMethod`-Vorgang.</span><span class="sxs-lookup"><span data-stu-id="24ae4-124">An asynchronous `BeginSampleMethod` operation.</span></span>  
  
    3. <span data-ttu-id="24ae4-125">Ein asynchrones `BeginServiceAsyncMethod` / `EndServiceAsyncMethod` Vorgangs Paar.</span><span class="sxs-lookup"><span data-stu-id="24ae4-125">An asynchronous `BeginServiceAsyncMethod`/`EndServiceAsyncMethod` operation pair.</span></span>  
  
2. <span data-ttu-id="24ae4-126">Einer Dienstimplementierung mit einem <xref:System.IAsyncResult?displayProperty=nameWithType>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="24ae4-126">A service implementation using a <xref:System.IAsyncResult?displayProperty=nameWithType> object.</span></span>  
  
 [!code-csharp[C_SyncAsyncClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_syncasyncclient/cs/services.cs#1)]
 [!code-vb[C_SyncAsyncClient#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_syncasyncclient/vb/services.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="24ae4-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="24ae4-127">See also</span></span>

- [<span data-ttu-id="24ae4-128">Entwerfen von Dienstverträgen</span><span class="sxs-lookup"><span data-stu-id="24ae4-128">Designing Service Contracts</span></span>](designing-service-contracts.md)
- [<span data-ttu-id="24ae4-129">Synchrone und asynchrone Vorgänge</span><span class="sxs-lookup"><span data-stu-id="24ae4-129">Synchronous and Asynchronous Operations</span></span>](synchronous-and-asynchronous-operations.md)
