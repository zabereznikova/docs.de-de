---
title: 'Vorgehensweise: Deklarieren von Fehlern in Dienstverträgen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e8da98e7-d22f-4f60-ac82-3fb0928a353f
ms.openlocfilehash: 90abb29550ce7e027244b220f30e9fe46e282ff3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59129492"
---
# <a name="how-to-declare-faults-in-service-contracts"></a><span data-ttu-id="b30a7-102">Vorgehensweise: Deklarieren von Fehlern in Dienstverträgen</span><span class="sxs-lookup"><span data-stu-id="b30a7-102">How to: Declare Faults in Service Contracts</span></span>
<span data-ttu-id="b30a7-103">In verwaltetem Code werden Ausnahmen bei Auftreten von Fehlerbedingungen ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="b30a7-103">In managed code, exceptions are thrown when error conditions occur.</span></span> <span data-ttu-id="b30a7-104">In Windows Communication Foundation (WCF)-Anwendungen geben jedoch Dienstverträge Fehlerinformationen an Clients zurückgegeben wird, durch das Deklarieren von SOAP-Fehlern in den Dienstvertrag.</span><span class="sxs-lookup"><span data-stu-id="b30a7-104">In Windows Communication Foundation (WCF) applications, however, service contracts specify what error information is returned to clients by declaring SOAP faults in the service contract.</span></span> <span data-ttu-id="b30a7-105">Eine Übersicht über die Beziehung zwischen Ausnahmen und Fehlern, finden Sie unter [angeben und Behandeln von Fehlern in Verträgen und Diensten](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md).</span><span class="sxs-lookup"><span data-stu-id="b30a7-105">For an overview of the relationship between exceptions and faults, see [Specifying and Handling Faults in Contracts and Services](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md).</span></span>  
  
### <a name="create-a-service-contract-that-specifies-a-soap-fault"></a><span data-ttu-id="b30a7-106">Erstellen eines Dienstvertrags zum Angeben eines SOAP-Fehlers</span><span class="sxs-lookup"><span data-stu-id="b30a7-106">Create a service contract that specifies a SOAP fault</span></span>  
  
1.  <span data-ttu-id="b30a7-107">Erstellen Sie einen Dienstvertrag, der mindestens einen Vorgang enthält.</span><span class="sxs-lookup"><span data-stu-id="b30a7-107">Create a service contract that contains at least one operation.</span></span> <span data-ttu-id="b30a7-108">Ein Beispiel finden Sie unter [Gewusst wie: Definieren eines Dienstvertrags](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md).</span><span class="sxs-lookup"><span data-stu-id="b30a7-108">For an example, see [How to: Define a Service Contract](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md).</span></span>  
  
2.  <span data-ttu-id="b30a7-109">Wählen Sie einen Vorgang aus, der sich zum Angeben einer Fehlerbedingung eignet, aufgrund derer die Clients eine entsprechende Benachrichtigung erhalten.</span><span class="sxs-lookup"><span data-stu-id="b30a7-109">Select an operation that can specify an error condition about which clients can expect to be notified.</span></span> <span data-ttu-id="b30a7-110">Um zu entscheiden, welche fehlerbedingungen zu rechtfertigen, SOAP-Fehler an Clients zurückgegeben wird, finden Sie unter [angeben und Behandeln von Fehlern in Verträgen und Diensten](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md).</span><span class="sxs-lookup"><span data-stu-id="b30a7-110">To decide which error conditions justify returning SOAP faults to clients, see [Specifying and Handling Faults in Contracts and Services](../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md).</span></span>  
  
3.  <span data-ttu-id="b30a7-111">Wenden Sie ein <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType> auf den ausgewählten Vorgang an, und geben Sie einen serialisierbaren Fehlertyp an den Konstruktor weiter.</span><span class="sxs-lookup"><span data-stu-id="b30a7-111">Apply a <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType> to the selected operation and pass a serializable fault type to the constructor.</span></span> <span data-ttu-id="b30a7-112">Weitere Informationen zum Erstellen und verwenden serialisierbarer Typen finden Sie unter [Specifying Data Transfer in Service Contracts](../../../docs/framework/wcf/feature-details/specifying-data-transfer-in-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="b30a7-112">For details about creating and using serializable types, see [Specifying Data Transfer in Service Contracts](../../../docs/framework/wcf/feature-details/specifying-data-transfer-in-service-contracts.md).</span></span> <span data-ttu-id="b30a7-113">Im folgenden Beispiel wird gezeigt, wie angegeben werden kann, dass der `SampleMethod`-Vorgang zu einem `GreetingFault` führt.</span><span class="sxs-lookup"><span data-stu-id="b30a7-113">The following example shows how to specify that the `SampleMethod` operation can result in a `GreetingFault`.</span></span>  
  
     [!code-csharp[FaultContractAttribute#4](../../../samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#4)]
     [!code-vb[FaultContractAttribute#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#4)]  
  
4.  <span data-ttu-id="b30a7-114">Wiederholen Sie die Schritte2 und 3 für alle Vorgänge des Vertrags, durch die Fehlerbedingungen an Clients weitergegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b30a7-114">Repeat steps 2 and 3 for all operations in the contract that communicate error conditions to clients.</span></span>  
  
## <a name="implementing-an-operation-to-return-a-specified-soap-fault"></a><span data-ttu-id="b30a7-115">Implementieren eines Vorgangs für das Zurückgeben eines angegebenen SOAP-Fehlers</span><span class="sxs-lookup"><span data-stu-id="b30a7-115">Implementing an Operation to Return a Specified SOAP Fault</span></span>  
 <span data-ttu-id="b30a7-116">Nachdem für einen Vorgang angegeben wurde, dass ein bestimmter SOAP-Fehler zurückgegeben werden kann, um eine Fehlerbedingung an eine aufrufende Anwendung weiterzugeben (wie beispielsweise in der vorangehenden Prozedur beschrieben), besteht der nächste Schritt in der Implementierung dieser Angabe.</span><span class="sxs-lookup"><span data-stu-id="b30a7-116">Once an operation has specified that a specific SOAP fault can be returned (such as in the preceding procedure) to communicate an error condition to a calling application, the next step is to implement that specification.</span></span>  
  
#### <a name="throw-the-specified-soap-fault-in-the-operation"></a><span data-ttu-id="b30a7-117">Auslösen des angegebenen SOAP-Fehlers im Vorgang</span><span class="sxs-lookup"><span data-stu-id="b30a7-117">Throw the specified SOAP fault in the operation</span></span>  
  
1.  <span data-ttu-id="b30a7-118">Tritt in einem Vorgang eine durch <xref:System.ServiceModel.FaultContractAttribute> angegebene Fehlerbedingung auf, lösen Sie eine neue <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType> aus. Der angegebene SOAP-Fehler fungiert hierbei als Typparameter.</span><span class="sxs-lookup"><span data-stu-id="b30a7-118">When a <xref:System.ServiceModel.FaultContractAttribute>-specified error condition occurs in an operation, throw a new <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType> where the specified SOAP fault is the type parameter.</span></span> <span data-ttu-id="b30a7-119">Im folgenden Beispiel wird gezeigt, wie der `GreetingFault` in der im vorherigen Abschnitt gezeigten `SampleMethod` sowie im folgenden Codeabschnitt ausgelöst werden kann.</span><span class="sxs-lookup"><span data-stu-id="b30a7-119">The following example shows how to throw the `GreetingFault` in the `SampleMethod` shown in the preceding procedure and in the following Code section.</span></span>  
  
     [!code-csharp[FaultContractAttribute#5](../../../samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#5)]
     [!code-vb[FaultContractAttribute#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="b30a7-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b30a7-120">Example</span></span>  
 <span data-ttu-id="b30a7-121">Das folgende Codebeispiel zeigt die Implementierung eines Einzelvorgangs, durch den ein `GreetingFault` für den `SampleMethod`-Vorgang angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="b30a7-121">The following code example shows an implementation of a single operation that specifies a `GreetingFault` for the `SampleMethod` operation.</span></span>  
  
 [!code-csharp[FaultContractAttribute#1](../../../samples/snippets/csharp/VS_Snippets_CFX/faultcontractattribute/cs/services.cs#1)]
 [!code-vb[FaultContractAttribute#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/faultcontractattribute/vb/services.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="b30a7-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b30a7-122">See also</span></span>

- <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType>
