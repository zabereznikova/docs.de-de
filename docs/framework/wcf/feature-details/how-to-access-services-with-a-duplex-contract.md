---
title: 'Vorgehensweise: Zugreifen auf Dienste mit einem Duplexvertrag'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- duplex contracts [WCF]
ms.assetid: 746a9d64-f21c-426c-b85d-972e916ec6c5
ms.openlocfilehash: c0022e6ce3a63c1f497eeee82ca959cec1046cec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33490151"
---
# <a name="how-to-access-services-with-a-duplex-contract"></a><span data-ttu-id="70481-102">Vorgehensweise: Zugreifen auf Dienste mit einem Duplexvertrag</span><span class="sxs-lookup"><span data-stu-id="70481-102">How to: Access Services with a Duplex Contract</span></span>
<span data-ttu-id="70481-103">Eine Funktion von Windows Communication Foundation (WCF), ist die Fähigkeit zum Erstellen eines Diensts, das ein duplexnachrichtenmuster verwendet.</span><span class="sxs-lookup"><span data-stu-id="70481-103">One feature of Windows Communication Foundation (WCF) is the ability to create a service that uses a duplex messaging pattern.</span></span> <span data-ttu-id="70481-104">Anhand dieses Musters kann ein Dienst mit dem Client über einen Rückruf kommunizieren</span><span class="sxs-lookup"><span data-stu-id="70481-104">This pattern allows a service to communicate with the client through a callback.</span></span> <span data-ttu-id="70481-105">In diesem Thema wird gezeigt, die Schritte zum Erstellen von eines WCF-Clients in einer Clientklasse, die die Rückrufschnittstelle implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="70481-105">This topic shows the steps to create a WCF client in a client class that implements the callback interface.</span></span>  
  
 <span data-ttu-id="70481-106">Eine Dualbindung macht die IP-Adresse des Clients für den Dienst verfügbar.</span><span class="sxs-lookup"><span data-stu-id="70481-106">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="70481-107">Der Client sollte Sicherheit eingestellt haben, um sicherzustellen, dass nur Verbindungen zu vertrauensvollen Diensten hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="70481-107">The client should use security to ensure that it connects only to services it trusts.</span></span>  
  
 <span data-ttu-id="70481-108">Ein Lernprogramm zum Erstellen einer grundlegenden WCF-Dienst und Client finden Sie unter [Lernprogramm für erste Schritte](../../../../docs/framework/wcf/getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="70481-108">For a tutorial on creating a basic WCF service and client, see [Getting Started Tutorial](../../../../docs/framework/wcf/getting-started-tutorial.md).</span></span>  
  
### <a name="to-access-a-duplex-service"></a><span data-ttu-id="70481-109">So greifen Sie auf einen Duplexdienst zu</span><span class="sxs-lookup"><span data-stu-id="70481-109">To access a duplex service</span></span>  
  
1.  <span data-ttu-id="70481-110">Erstellen Sie einen Dienst, der zwei Schnittstellen enthält.</span><span class="sxs-lookup"><span data-stu-id="70481-110">Create a service that contains two interfaces.</span></span> <span data-ttu-id="70481-111">Die erste Schnittstelle ist dem Dienst vorbehalten, die zweite Schnittstelle wird für den Rückruf verwendet.</span><span class="sxs-lookup"><span data-stu-id="70481-111">The first interface is for the service, the second is for the callback.</span></span> <span data-ttu-id="70481-112">Weitere Informationen zu einen Duplexdienst zu erstellen, finden Sie unter [Vorgehensweise: Erstellen eines Duplexvertrags](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="70481-112">For more information about creating a duplex service, see [How to: Create a Duplex Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
2.  <span data-ttu-id="70481-113">Führen Sie den Dienst aus.</span><span class="sxs-lookup"><span data-stu-id="70481-113">Run the service.</span></span>  
  
3.  <span data-ttu-id="70481-114">Verwenden der [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) Generieren von Datenverträgen (Schnittstellen) für den Client.</span><span class="sxs-lookup"><span data-stu-id="70481-114">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to generate contracts (interfaces) for the client.</span></span> <span data-ttu-id="70481-115">Informationen hierzu finden Sie unter [Vorgehensweise: Erstellen eines Clients](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="70481-115">For information about how to do this, see  [How to: Create a Client](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span></span>  
  
4.  <span data-ttu-id="70481-116">Implementieren Sie die Rückrufschnittstelle in der Client-Klasse, wie im nachfolgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="70481-116">Implement the callback interface in the client class, as shown in the following example.</span></span>  
  
    ```csharp  
    public class CallbackHandler : ICalculatorDuplexCallback  
    {  
        public void Result(double result)  
        {  
            Console.WriteLine("Result ({0})", result);  
        }  
        public void Equation(string equation)  
        {  
            Console.WriteLine("Equation({0})", equation);  
        }  
    }  
    ```  
  
    ```vb  
    Public Class CallbackHandler   
    Implements ICalculatorDuplexCallback  
       Public Sub Result (ByVal result As Double)  
          Console.WriteLine("Result ({0})", result)  
       End Sub  
        Public Sub Equation(ByVal equation As String)  
            Console.Writeline("Equation({0})", equation)  
        End Sub  
    End Class  
    ```  
  
5.  <span data-ttu-id="70481-117">Erstellen Sie eine Instanz der <xref:System.ServiceModel.InstanceContext>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="70481-117">Create an instance of the <xref:System.ServiceModel.InstanceContext> class.</span></span> <span data-ttu-id="70481-118">Der Konstruktor benötigt eine Instanz der Client-Klasse.</span><span class="sxs-lookup"><span data-stu-id="70481-118">The constructor requires an instance of the client class.</span></span>  
  
    ```csharp  
    InstanceContext site = new InstanceContext(new CallbackHandler());  
    ```  
  
    ```vb  
    Dim site As InstanceContext = New InstanceContext(new CallbackHandler())  
    ```  
  
6.  <span data-ttu-id="70481-119">Erstellen Sie eine Instanz des WCF-Clients mithilfe des Konstruktors, der erfordert ein <xref:System.ServiceModel.InstanceContext> Objekt.</span><span class="sxs-lookup"><span data-stu-id="70481-119">Create an instance of the WCF client using the constructor that requires an <xref:System.ServiceModel.InstanceContext> object.</span></span> <span data-ttu-id="70481-120">Der zweite Parameter des Konstruktors ist der Name eines Endpunkts in der Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="70481-120">The second parameter of the constructor is the name of an endpoint found in the configuration file.</span></span>  
  
    ```csharp  
    CalculatorDuplexClient wcfClient =   
    new CalculatorDuplexClient(site, "default")  
    ```  
  
    ```vb  
    Dim wcfClient As New CalculatorDuplexClient(site, "default")  
    ```  
  
7.  <span data-ttu-id="70481-121">Rufen Sie die Methoden des WCF-Clients als erforderlich.</span><span class="sxs-lookup"><span data-stu-id="70481-121">Call the methods of the WCF client as required.</span></span>  
  
## <a name="example"></a><span data-ttu-id="70481-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="70481-122">Example</span></span>  
 <span data-ttu-id="70481-123">Im folgenden Codebeispiel wird das Erstellen einer Client-Klasse veranschaulicht, die auf einen Duplexvertrag zugreift.</span><span class="sxs-lookup"><span data-stu-id="70481-123">The following code example demonstrates how to create a client class that accesses a duplex contract.</span></span>  
  
 [!code-csharp[S_DuplexClients#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_duplexclients/cs/client.cs#1)]
 [!code-vb[S_DuplexClients#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_duplexclients/vb/client.vb#1)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="70481-124">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="70481-124">.NET Framework Security</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70481-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="70481-125">See Also</span></span>  
 [<span data-ttu-id="70481-126">Tutorial mit ersten Schritten</span><span class="sxs-lookup"><span data-stu-id="70481-126">Getting Started Tutorial</span></span>](../../../../docs/framework/wcf/getting-started-tutorial.md)  
 [<span data-ttu-id="70481-127">Vorgehensweise: Erstellen eines Duplexvertrags</span><span class="sxs-lookup"><span data-stu-id="70481-127">How to: Create a Duplex Contract</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)  
 [<span data-ttu-id="70481-128">ServiceModel Metadata Utility-Tool (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="70481-128">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)  
 [<span data-ttu-id="70481-129">Vorgehensweise: Erstellen eines Clients</span><span class="sxs-lookup"><span data-stu-id="70481-129">How to: Create a Client</span></span>](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md)  
 [<span data-ttu-id="70481-130">Vorgehensweise: Verwenden von ChannelFactory</span><span class="sxs-lookup"><span data-stu-id="70481-130">How to: Use the ChannelFactory</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-channelfactory.md)
