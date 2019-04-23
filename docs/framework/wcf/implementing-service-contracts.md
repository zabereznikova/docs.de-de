---
title: Implementieren von Dienstverträgen
ms.date: 03/30/2017
helpviewer_keywords:
- implementing service contracts [WCF]
ms.assetid: aefb6f56-47e3-4f24-ab0a-9bc07bf9885f
ms.openlocfilehash: 766e0c4d30a4fa0eed9ce154ca932f5371a43211
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59196319"
---
# <a name="implementing-service-contracts"></a><span data-ttu-id="dbfca-102">Implementieren von Dienstverträgen</span><span class="sxs-lookup"><span data-stu-id="dbfca-102">Implementing Service Contracts</span></span>
<span data-ttu-id="dbfca-103">Ein Dienst ist eine Klasse, die die an einem oder mehreren Endpunkten für den Client bereitstehenden Funktionen verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="dbfca-103">A service is a class that exposes functionality available to clients at one or more endpoints.</span></span> <span data-ttu-id="dbfca-104">Um einen Dienst erstellen, Schreiben Sie eine Klasse, die einen Windows Communication Foundation (WCF)-Vertrag implementiert.</span><span class="sxs-lookup"><span data-stu-id="dbfca-104">To create a service, write a class that implements a Windows Communication Foundation (WCF) contract.</span></span> <span data-ttu-id="dbfca-105">Dazu haben Sie zwei Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="dbfca-105">You can do this in one of two ways.</span></span> <span data-ttu-id="dbfca-106">Sie können den Vertrag gesondert als Schnittstelle definieren und dann eine Klasse erstellen, die die Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="dbfca-106">You can define the contract separately as an interface and then create a class that implements that interface.</span></span> <span data-ttu-id="dbfca-107">Alternativ können Sie die Klasse und den Vertrag direkt erstellen, indem Sie das <xref:System.ServiceModel.ServiceContractAttribute>-Attribut direkt für die Klasse und das <xref:System.ServiceModel.OperationContractAttribute>-Attribut für die Methoden festlegen, die für die Clients des Dienstes verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="dbfca-107">Alternatively, you can create the class and contract directly by placing the <xref:System.ServiceModel.ServiceContractAttribute> attribute on the class itself and the <xref:System.ServiceModel.OperationContractAttribute> attribute on the methods available to the clients of the service.</span></span>  
  
## <a name="creating-a-service-class"></a><span data-ttu-id="dbfca-108">Erstellen einer Dienstklasse</span><span class="sxs-lookup"><span data-stu-id="dbfca-108">Creating a service class</span></span>  
 <span data-ttu-id="dbfca-109">Im folgende Beispiel implementiert ein Dienst einen  `IMath`-Vertrag, der gesondert definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="dbfca-109">The following is an example of a service that implements an `IMath` contract that has been defined separately.</span></span>  
  
```csharp  
// Define the IMath contract.  
[ServiceContract]  
public interface IMath  
{  
    [OperationContract]   
    double Add(double A, double B);  
  
    [OperationContract]  
    double Multiply (double A, double B);  
}  
  
// Implement the IMath contract in the MathService class.  
public class MathService : IMath  
{  
    public double Add (double A, double B) { return A + B; }  
    public double Multiply (double A, double B) { return A * B; }  
}  
```  
  
 <span data-ttu-id="dbfca-110">Ein Dienst kann stattdessen einen Vertrag auch direkt verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="dbfca-110">Alternatively, a service can expose a contract directly.</span></span> <span data-ttu-id="dbfca-111">Im folgende Beispiel definiert und implementiert eine Dienstklasse einen `MathService`-Vertrag.</span><span class="sxs-lookup"><span data-stu-id="dbfca-111">The following is an example of a service class that defines and implements a `MathService` contract.</span></span>  
  
```csharp  
// Define the MathService contract directly on the service class.  
[ServiceContract]  
class MathService  
{  
    [OperationContract]  
    public double Add(double A, double B) { return A + B; }  
    [OperationContract]  
    private double Multiply (double A, double B) { return A * B; }  
}  
```  
  
 <span data-ttu-id="dbfca-112">Die vorhergehenden Dienste machen hierbei verschiedene Verträge verfügbar, da sich die Vertragsnamen unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="dbfca-112">Note that the preceding services expose different contracts because the contract names are different.</span></span> <span data-ttu-id="dbfca-113">Im ersten Fall wird der verfügbar gemachte Vertrag "`IMath`" genannt und im zweiten Fall lautet der Name des Vertrags `MathService`".</span><span class="sxs-lookup"><span data-stu-id="dbfca-113">In the first case, the exposed contract is named "`IMath`" while in the second case the contract is named "`MathService`".</span></span>  
  
 <span data-ttu-id="dbfca-114">Sie können auf den Ebenen der Dienst- und Vorgangsimplementierung Verschiedenes festlegen, z.&amp;#160;B. die Parallelität und Instanziierung.</span><span class="sxs-lookup"><span data-stu-id="dbfca-114">You can set a few things at the service and operation implementation levels, such as concurrency and instancing.</span></span> <span data-ttu-id="dbfca-115">Weitere Informationen finden Sie unter [entwerfen und Implementieren von Diensten](../../../docs/framework/wcf/designing-and-implementing-services.md).</span><span class="sxs-lookup"><span data-stu-id="dbfca-115">For more information, see [Designing and Implementing Services](../../../docs/framework/wcf/designing-and-implementing-services.md).</span></span>  
  
 <span data-ttu-id="dbfca-116">Nach der Implementierung eines Dienstvertrags müssen Sie einen oder mehrere Endpunkte für den Dienst erstellen.</span><span class="sxs-lookup"><span data-stu-id="dbfca-116">After implementing a service contract, you must create one or more endpoints for the service.</span></span> <span data-ttu-id="dbfca-117">Weitere Informationen finden Sie unter [Übersicht über die Endpunkterstellung](../../../docs/framework/wcf/endpoint-creation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="dbfca-117">For more information, see [Endpoint Creation Overview](../../../docs/framework/wcf/endpoint-creation-overview.md).</span></span> <span data-ttu-id="dbfca-118">Weitere Informationen dazu, wie Sie einen Dienst ausführen, finden Sie unter [Hostingdienste](../../../docs/framework/wcf/hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="dbfca-118">For more information about how to run a service, see [Hosting Services](../../../docs/framework/wcf/hosting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbfca-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dbfca-119">See also</span></span>

- [<span data-ttu-id="dbfca-120">Entwerfen und Implementieren von Diensten</span><span class="sxs-lookup"><span data-stu-id="dbfca-120">Designing and Implementing Services</span></span>](../../../docs/framework/wcf/designing-and-implementing-services.md)
- [<span data-ttu-id="dbfca-121">Vorgehensweise: Erstellen Sie einen Dienst mit einer Vertragsklasse</span><span class="sxs-lookup"><span data-stu-id="dbfca-121">How to: Create a Service with a Contract Class</span></span>](../../../docs/framework/wcf/feature-details/how-to-create-a-wcf-contract-with-a-class.md)
- [<span data-ttu-id="dbfca-122">Vorgehensweise: Erstellen Sie einen Dienst mit einer Vertragsschnittstelle</span><span class="sxs-lookup"><span data-stu-id="dbfca-122">How to: Create a Service with a Contract Interface</span></span>](../../../docs/framework/wcf/feature-details/how-to-create-a-service-with-a-contract-interface.md)
- [<span data-ttu-id="dbfca-123">Angeben des Dienstlaufzeitverhaltens</span><span class="sxs-lookup"><span data-stu-id="dbfca-123">Specifying Service Run-Time Behavior</span></span>](../../../docs/framework/wcf/specifying-service-run-time-behavior.md)
