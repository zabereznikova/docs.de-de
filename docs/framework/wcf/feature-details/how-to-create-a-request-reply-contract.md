---
title: 'Gewusst wie: Erstellen eines Anforderung-Antwort-Vertrags'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 801d90da-3d45-4284-9c9f-56c8aadb4060
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2a272eaa88a53814daea9d515550a37f7991ecb8
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-create-a-request-reply-contract"></a><span data-ttu-id="f5500-102">Gewusst wie: Erstellen eines Anforderung-Antwort-Vertrags</span><span class="sxs-lookup"><span data-stu-id="f5500-102">How to: Create a Request-Reply Contract</span></span>
<span data-ttu-id="f5500-103">Ein Anforderung-Antwort-Vertrag gibt eine Methode an, die eine Antwort zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="f5500-103">A request-reply contract specifies a method that returns a reply.</span></span> <span data-ttu-id="f5500-104">Die Antwort muss gesendet und unter den Bedingungen dieses Vertrags mit der Anforderung in Beziehung gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="f5500-104">The reply must be sent and correlated to the request under the terms of this contract.</span></span> <span data-ttu-id="f5500-105">Selbst wenn die Methode keine Antwort (`void` in C# oder `Sub` in Visual Basic) zurückgibt, wird von der Infrastruktur eine leere Nachricht erstellt und gesendet, um dem Aufrufer mitzuteilen, dass die Methode einen Wert zurückgegeben hat.</span><span class="sxs-lookup"><span data-stu-id="f5500-105">Even if the method returns no reply (`void` in C#, or a `Sub` in Visual Basic), the infrastructure creates and sends an empty message to the caller.</span></span> <span data-ttu-id="f5500-106">Verwenden Sie einen unidirektionalen Vertrag für die Operation, um das Senden einer leeren Mitteilung zu unterbinden.</span><span class="sxs-lookup"><span data-stu-id="f5500-106">To prevent the sending of an empty reply message, use a one-way contract for the operation.</span></span>  
  
### <a name="to-create-a-request-reply-contract"></a><span data-ttu-id="f5500-107">So erstellen Sie einen Anforderung-Antwort-Vertrag</span><span class="sxs-lookup"><span data-stu-id="f5500-107">To create a request-reply contract</span></span>  
  
1.  <span data-ttu-id="f5500-108">Erstellen Sie in der Programmiersprache Ihrer Wahl eine Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="f5500-108">Create an interface in the programming language of your choice.</span></span>  
  
2.  <span data-ttu-id="f5500-109">Fügen Sie das <xref:System.ServiceModel.ServiceContractAttribute>-Attribut der Schnittstelle hinzu.</span><span class="sxs-lookup"><span data-stu-id="f5500-109">Apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute to the interface.</span></span>  
  
3.  <span data-ttu-id="f5500-110">Fügen Sie das <xref:System.ServiceModel.OperationContractAttribute>-Attribut jeder von Clients aufrufbaren Methode hinzu.</span><span class="sxs-lookup"><span data-stu-id="f5500-110">Apply the <xref:System.ServiceModel.OperationContractAttribute> attribute to each method that clients can invoke.</span></span>  
  
4.  <span data-ttu-id="f5500-111">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="f5500-111">Optional.</span></span> <span data-ttu-id="f5500-112">Legen Sie den Wert der <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A>-Eigenschaft auf `true` fest, um das Senden einer leeren Mitteilung zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="f5500-112">Set the value of the <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> property to `true` to prevent the sending of an empty reply message.</span></span> <span data-ttu-id="f5500-113">Standardmäßig sind alle Operationen Anforderung-Antwort-Verträge.</span><span class="sxs-lookup"><span data-stu-id="f5500-113">By default, all operations are request-reply contracts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f5500-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f5500-114">Example</span></span>  
 <span data-ttu-id="f5500-115">Im folgenden Beispiel wird ein Vertrag für einen Rechnerdienst definiert, der die `Add`-Methode und die `Subtract`-Methode bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="f5500-115">The following sample defines a contract for a calculator service that provides `Add` and `Subtract` methods.</span></span> <span data-ttu-id="f5500-116">Die `Multiply`-Methode ist nicht Teil des Vertrags, weil sie von der <xref:System.ServiceModel.OperationContractAttribute>-Klasse nicht gekennzeichnet wurde und somit nicht für Clients verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="f5500-116">The `Multiply` method is not part of the contract because it is not marked by the <xref:System.ServiceModel.OperationContractAttribute> class and so it is not accessible to clients.</span></span>  
  
```
using System.ServiceModel;

[ServiceContract]
public interface ICalculator
{
    [OperationContract]
    // It would be equivalent to write explicitly:
    // [OperationContract(IsOneWay=false)]
    int Add(int a, int b);
    
    [OperationContract]
    int Subtract(int a, int b);
    
    int Multiply(int a, int b)
}
```
  
-   <span data-ttu-id="f5500-117">Weitere Informationen zum Angeben von vorgangsverträgen finden Sie unter der <xref:System.ServiceModel.OperationContractAttribute> Klasse und die <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="f5500-117">For more information about how to specify operation contracts, see the <xref:System.ServiceModel.OperationContractAttribute> class and the <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> property.</span></span>  
  
-   <span data-ttu-id="f5500-118">Durch Anwenden des <xref:System.ServiceModel.ServiceContractAttribute>-Attributs und des <xref:System.ServiceModel.OperationContractAttribute>-Attributs wird die automatische Generierung von Dienstvertragsdefinitionen in einem WSDL (Web Services Description Language)-Dokument ermöglicht, sobald der Dienst bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="f5500-118">Applying the <xref:System.ServiceModel.ServiceContractAttribute> and <xref:System.ServiceModel.OperationContractAttribute> attributes causes the automatic generation of service contract definitions in a Web Services Description Language (WSDL) document once the service is deployed.</span></span> <span data-ttu-id="f5500-119">Das Dokument wird durch Anfügen von `?wsdl` an die HTTP-Basisadresse des Diensts heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="f5500-119">The document is downloaded by appending `?wsdl` to the HTTP base address for the service.</span></span> <span data-ttu-id="f5500-120">Beispiel: `http://microsoft/CalculatorService?wsdl`</span><span class="sxs-lookup"><span data-stu-id="f5500-120">For example, `http://microsoft/CalculatorService?wsdl`</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5500-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f5500-121">See Also</span></span>  
 <xref:System.ServiceModel.OperationContractAttribute>  
 [<span data-ttu-id="f5500-122">Entwerfen von Dienstverträgen</span><span class="sxs-lookup"><span data-stu-id="f5500-122">Designing Service Contracts</span></span>](../../../../docs/framework/wcf/designing-service-contracts.md)  
 [<span data-ttu-id="f5500-123">Vorgehensweise: Erstellen eines Duplexvertrags</span><span class="sxs-lookup"><span data-stu-id="f5500-123">How to: Create a Duplex Contract</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)
